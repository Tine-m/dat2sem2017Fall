# Integrations test - database
This note will explain how to test the database mappers. Much of the system stands on top of the database working correctly, so it is nice to be certain this works. And it is nice to be able to develop this layer independent of the other layers.

### Principle of database testing
Normally the mapper methods start out by requesting a database connection. The connection specify which database to use.

The idea is to make a test database, and and give the mapper a connection which is the test database during testing. 

We need to do the following steps:
1. Make a test database
2. Make it possible to trick the mappers to use an other connection
3. Make test methods

## Sample code
The [Login project](https://github.com/DAT2Sem2017E/Modul3LogInSample) has been extended with a test section which tests the UserMapper.

### Making a test database
We need a copy of the database. In the test database there will be two tables for each table in the original database. One which is used for safekeeping of the test data, and one to be used during the tests.

We will user the user login as the sample. The schema there is named `useradmin`, we will call the test schema `useradminTest`. I will create the test database on the same MySQLServer, but you could (and maybe should) use a different server.

This is the *one time setup* script:

```sql
-- There is a schema named "useradmin" with one table: "Users"
-- The test schema is named "useradminTest"
-- make a copy of the table
CREATE TABLE useradminTest.Users LIKE useradmin.Users;
-- make an other copy, this time naming it UsersTest
CREATE TABLE UsersTest LIKE useradminTest.Users;
INSERT INTO `UsersTest` VALUES 
    (1,'jens@somewhere.com','jensen','customer'),
    (2,'ken@somewhere.com','kensen','customer'),
    (3,'robin@somewhere.com','batman','employee'),
    (4,'someone@nowhere.com','sesam','customer');
-- make a new user for the test database
CREATE USER 'testinguser' IDENTIFIED BY 'try1try2tryAgain';
GRANT ALL PRIVILEGES ON useradminTest.* TO 'testinguser';
```

### Making the mappers use a different connection
Often there is a connection class which is somewhat similar to this (using a singleton)

```java
public class Connector {
    private static final String url = "jdbc:mysql://46.101.253.149:3306/useradmin";
    private static final String username = "...";
    private static final String password = "...";

    private static Connection singleton;

    public static Connection connection() throws ClassNotFoundException, SQLException  {
        if ( singleton == null ) {
            Class.forName( "com.mysql.jdbc.Driver" );
            singleton = DriverManager.getConnection( url, username, password );
        }
        return singleton;
    }

}
```

We can simply make a setter method which allow us to set the connection singleton, like this:

```java
public static void setConnection(Connection con){
	singleton = con;
}
```

In the tests we will make a new connector which connects to the test database. 
Then when the mapper requests the connection `Connection con = Connector.connection();` it will get the test database.

### Initial test setup
There is a special method annotation named `@Before` which can be used in connection with JUnit. That method is run just before any test method. Here we use it to reset the database table at each test.

As usual, one should be careful not to make a new connection at each call, so we use the singular pattern to make sure we only open one connection.

```java
public class UserMapperTest {
    
	private static Connection testConnection;
   	private static String USER = "testinguser";
	private static String USERPW = "try1try2tryAgain";
	private static String DBNAME = "useradminTest";
	private static String HOST = "46.101.253.149";

    @Before
    public void setUp() {
        try {
            // awoid making a new connection for each test
            if ( testConnection == null ) {
                String url = String.format( "jdbc:mysql://%s:3306/%s", HOST, DBNAME );
                Class.forName( "com.mysql.jdbc.Driver" );

                testConnection = DriverManager.getConnection( url, USER, USERPW );
                // Make mappers use test 
                Connector.setConnection( testConnection );
            }
            // reset test database
            try ( Statement stmt = testConnection.createStatement() ) {
                stmt.execute( "drop table if exists Users" );
                stmt.execute( "create table Users like UsersTest" );
                stmt.execute( "insert into Users select * from UsersTest" );
            }

        } catch ( ClassNotFoundException | SQLException ex ) {
            testConnection = null;
            System.out.println( "Could not open connection to database: " + ex.getMessage() );
        }
    }    
     
    
}

### Some test examples
There are some test examples in [the code on github](https://github.com/DAT2Sem2017E/Modul3LogInSample).
