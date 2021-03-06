# Linux, Webserver og MySQL i skyen.

## Linux på Digital Ocean
Vi vil kigge på hvordan man opsætter en Linux server på Digital Ocean, hvordan vi håndterer flere brugere på linux og hvordan vi kan tale med serveren via et commandline værktøj (git bash)
Emnerne for ugen bliver:

### Oversigt over ugen:

| Dag     | Emne                                     |
| ------- | ---------------------------------------- |
| Mandag  | Undervisning i klassen                   |
| Tirsdag | Individuelt arbejde med opsætning af linux server (Tutorhjælp i klassen) |
| Onsdag  | Arbejde med opsætning af MySql database og connections (Kasper er i klassen til hjælp) |
| Torsdag | Arbejde med opsætning af Tomcat og Deployment af egen web applikation |
| Fredag  | Review med Kasper og Thomas - Vis hvad i har lavet i ugens løb |

### Resultatet

Når ugen er omme og i har lavet øvelserne skulle hver af jer gerne have en 'live' web server i skyen med database server. Desuden vil i have deployet et eller flere web projecter som kan tilgås via IP-adressen til jeres Linux Server.

Ugen bliver lidt anderledes end de fleste uger på 2. semester. Mandag er der undervisning som normalt, men tirsdag-torsdag er der arbejdsopgaver der skal løses og først fredag er der review af arbejdet. Der bliver altså kun 1 review i Linux ugen.

I denne første uge af web modulet skal i alle oprette en server på Digital Ocean. Prisen for en Droplet på Digital Ocean er minimum 5$ pr. måned. Dette beløb forventer vi at i selv betaler (Det er trods alt en lille investering i forhold til flere af jeres medstuderende fra de andre uddannelser, der bliver bedt om at købe bøger for mange hundrede kroner, hvert semester). Grunden til at vi gerne vil have at alle opretter deres egen linux server er at:

- Vi håber at serveren sammen med jeres github konto bliver et portfolio, hvor i kan lægge alle jeres skoleprojekter, så andre kan se dem (praktikværter, jobudbydere, mor og far m.fl)
- Vi kommer til at bruge disse droplets rigtig meget på de efterfølgende semestre også

#### Læringsmål

Efter denne uge er det meningen at:

- Du kan oprette en droplet med en linux server på [Digital Ocean](https://www.digitalocean.com/)
- Du kan konfigurere brugere på linux server og sikre brugerkonti med SSH
- Du kan bruge git bash commandline tool til at navigere rundt på linux serveren.
- Du kan installere [MySQL](https://dev.mysql.com/downloads/installer/) server og oprette bruger konti med forskellige rettigheder.
- Du kan få forbindelse til din MySql server fra MySql [Workbench](https://www.mysql.com/products/workbench/).
- Du kan installere Tomcat på din linux server så den kan bruges som web server.
- Du kan deploye dit eget web projekt så det kan tilgås fra internettet.

#### Erhvervskompetencer

Når ugen er omme har du opnået følgende kompetencer:

- Du kan redegøre for de forskellige servere der kan indgå i en java web stack. 
- Du kan installere og konfigurere linux servere med Database server og web server.
- Du kan deploye et webprojekt til en webserver på internettet.

### Portfolie

Linux serveren på Digital Ocean kommer i også til at bruge meget på 3. semester (og sandsynligvis på 4. semester). Vi håber at i vil betragte denne server (sammen med jeres github konto) som et portfolio, hvor igennem i can 'show case' jeres arbejde/projekter til andre der måtte være interesserede (kommende praktikværter, arbejdsgivere, bedsteforældre m.fl. :-))

### Ressourcer til ugen  
[Book: Learn Linux in 5 days](https://linuxtrainingacademy.com/wp-content/uploads/2016/08/learn-linux-in-5-days.pdf?__s=uvrsr3eotoyvr3yvh2zk): Denne bog er en generel indføring i Linux som operativ system. I kan bruge den som baggrundsreference til at slå op i eller til at læse dele af, hvis i har noget tid i overskud.  

[Cheat sheet til de meste brugte linux commands](study/linuxcommands.pdf): Dette ensides ark kan i printe ud og have liggende ved siden af jer i begyndelsen indtil i bliver fortrolige med de meste brugte commands i linux.  

[Tutorial til opsætning af linux server](https://docs.google.com/document/d/1sm1ocmXylBiuXHQGt3Tue-FfgZwVFCBfXTmu6jXlN5A/edit?usp=sharing)   
[Tutorial til installation af MySql Server på Linux serveren](https://docs.google.com/document/d/18StF7PqyqXr7YQZnFJJIxAqoxMVgD2cEH_OiSDOJh_8/edit?usp=sharing)  
[Tutorial til installation af Tomcat på Linux serveren](https://docs.google.com/document/d/1NWLOk9GdU0auz9z3gjkAU5nuR7t1vyX2no84_eYqGRc/edit?usp=sharing)  
[Mandagens slidesæt](https://docs.google.com/presentation/d/1T-gVZ6zKHc61qF6XTyq_r44j39HjUcoC82UGdGQDwCI/edit?usp=sharing)    




### Dag 1:
1. Opsamling på modul 1 og kort gennemgang af quick-sort algoritmen fra i fredags ved Kasper  
2. Gennemgang af ugens emner samt øvelser ved Thomas  
   I klassen gennemgår vi 3 hovedemner  
   1. Network: IP, port, database server, webserver på netværk  
   2. SSH: hvordan virker det, nøgler, opsætning på D.O.  
   3. User accounts tomcat, mysql, linux   




### Dag 2: Linux server og SSH
At bruge password beskyttelse på sin brugerkonto på en server der er forbundet til internettet er ikke tilstrækkeligt sikkert. I stedet bruger vi kun SSH til at forbinde med serveren.
Brug denne dag til at få noget rutine i at opsætte en Linux server på en droplet på Digital Ocean. Nedlæg gerne dropletten flere gange og opret den igen for at blive fortrolige med processen.   
Opsæt SSH og sørg for at lukke for adgang via password så maskinen ikke bliver hakket og dermed lukket ned af Digital Ocean.

### Udtræk af commands fra tutorial til installation af linux server:
```
ssh root@SERVER_IP_ADDRESS  
adduser <user>  
usermod -aG sudo <user>  
su <user>  
cd ~/  
mkdir ~/.ssh  
chmod 700 ~/.ssh  
nano ~/.ssh/authorized_keys  
```
Insert your ssh public key here.  

Check this file: `sudo nano /etc/ssh/sshd_config` to see if `PasswordAuthentication no` is there  
```
chmod 600 ~/.ssh/authorized_keys  
exit  
sudo systemctl reload sshd  
```
Now check if you can log in with `<user>` from a terminal.  


[Skridt for skridt: Linux installation](study/ex1ssh_basic_linux.md)   

[Ekstra øvelser omkring bash scripting](study/ex2bash.md)   

##### Extra: Løbende vil der være opdateringer at installere:

```
sudo apt-get update        # Fetches the list of available updates
sudo apt-get upgrade       # Strictly upgrades the current packages
sudo apt-get dist-upgrade  # Installs updates (new ones)
```

#### Ekstra ressourcer:
[Shell Scripting](http://ryanstutorials.net/linuxtutorial/scripting.php)  
[Bash on Lynda.com ](https://www.lynda.com/Bash-tutorials/Up-Running-Bash-Scripting/142989-2.html)  
[SSH on Lynda.com:](https://www.lynda.com/Developer-Network-Administration-tutorials/Welcome/189066/365610-4.html)   
[SSH video on youtube:](https://www.youtube.com/watch?v=svRWcx7dT8g)   
[Public/private key concept article](http://blakesmith.me/2010/02/08/understanding-public-key-private-key-concepts.html)  
[D.O. tutorial: SSH & connecting to ubuntu](https://www.digitalocean.com/community/tutorials/understanding-the-ssh-encryption-and-connection-process)  


### Dag 3: MySQL installationen  
Brug denne dag på at installere MySql server på din Ubuntu (Linux) server. Opsæt brugere og giv brugerkonti adgang til forskellige ting på databasen. 
Opret forbindelse til MySql serveren med en brugerkonto, der kan tilgås udefra (fra internettet) og dermed kan bruges til at logge på og bruge databasen fra både netbeans og MySql Workbench.

[Skridt for skridt MySql](study/ex3mysql.md)


#### De nødvendige commands er skrevet her:  
Dette er et sammendrag af de kommandoer der skal bruges, som de er beskrevet i den linkede tutorial. Her er de blot samlet for at gøre det lettere at copy/paste dem, når man allerede har en forståelse for hvad de gør (Fordi man har læst tutorialen:-) )
```
sudo apt-get update
sudo apt-get install mysql-server
sudo mysql_secure_installation
mysql -u root -p
CREATE DATABASE test;
exit
```
Lav ændringer i denne fil:  
“sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf”
ved at udkommentere bind-address linjen som vist her:

```
bind-address = localhost
```

Opret nu en MySql bruger for at give adgang til en given database udefra (internettet). testuser@'%' refererer til en bruger der kan komme fra en hvilken som helst IP-adresse.

```
mysql -u root –p 
CREATE USER 'testuser'@'localhost' IDENTIFIED BY 'password123'; 
CREATE USER 'testuser'@'%' IDENTIFIED BY 'password123'; 
GRANT ALL ON test.* TO 'testuser'@'localhost'; 
GRANT ALL ON test.* TO 'testuser'@'%';
exit
service mysql restart
```
Prøv at oprette en sql script fil og send den op på serveren med SCP (secure copy)  
` scp demo.sql <username>@<server IP>:/home/<username>/tmp/demo.sql` (hint: opret først tmp folderen i den bruges home directory).  
Nu kan du fra linux serveren gøre følgende:  
``` 
mysql -u root -p  
source /home/<username>/tmp/demo.sql; 
```

### Ekstra ressourcer:

[D.O. Tutorial: Installing MySQL](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-14-04)   

[Use ssh tunneling to access mysql server from workbench locally](https://dev.mysql.com/doc/workbench/en/wb-mysql-connections-methods-ssh.html)  

 

## Dag 4 - Tomcat installation og deployment
På denne dag kan i installere Tomcat på jeres Ubuntumaskine (hvis i ikke allerede har gjort det). Følg den linkede tutorial. Vi vil derefter deploye en lille webapplikation ved at bruge både Tomcat og MySql.   

[Skridt for skridt: Tomcat](study/ex4tomcat.md)

Nedenfor er listet de nødvendige commands for at klare opgaven:  
```
sudo apt-get install tomcat8 tomcat8-admin
sudo apt-get install haveged 
sudo nano /etc/tomcat8/tomcat-users.xml
```
Insert at the end: `<role rolename="manager-gui"/><user name="admin" password="changeThis" roles="manager-gui, manager-script"/>` and save the xml file.
```
service tomcat8 restart
sudo nano /etc/tomcat8/server.xml
```
Replace `Connector port="8080"` with `Connector port="80"` in line 71
```
sudo nano /etc/default/tomcat8
```
Change `#AUTHBIND=no` to `AUTHBIND=yes` (remember to remove the #-sign)
```
service tomcat8 restart
```

- Åben nu en browser på din lokale maskine og gå til: `<your ubuntu ip>/manager`  
- Log på med dine credentials fra filen: tomcat-users.xml.
- Deploy en webapplikation med en database så den kan tilgås via: `<your ubuntu ip>/<application name>`. Find guide/øvelse her: [Deployment exercise](study/ex5deploy.md)  
- Mangler du et web project at deploye ? så brug dette: [demoproject](https://github.com/DAT2Sem2017E/demoproject)


### Ressourcer:

[Tutorial: Tomcat on Digital Ocean](https://www.digitalocean.com/community/tutorials/how-to-install-apache-tomcat-8-on-ubuntu-16-04)
[General about tomcat](https://www.ntu.edu.sg/home/ehchua/programming/howto/tomcat_more.html)  

## Dag 5 - Review   

Hvis i ikke allerede har fået deployet et webprojekt med database så gør det nu :-)

### Review    

Når vi mødes fredag vil jeg gerne have en demo af jeres serverløsninger. Vi forventer at i kan logge på serveren med commandline tool (f.eks. git bash) vha. SSH. Vi vil gerne se at i kan oprette en bruger på MySql serveren samt oprette en ny database. Vi vil desuden gerne se at i kan tilgå denne nye database vha. MySql Workbench fra jeres lokale maskine.   
Sidst vil vi gerne se at i kan tage en .war fil og deploye den til tomcat serveren hvorefter vi kan tilgå applicationen fra en browser.  

Forventninger til fredag (Gul bygger videre på grøn og rød bygger videre på gul):  

| Niveau | Demo                                     |
| ------ | ---------------------------------------- |
| Grøn   | Det forventes at i alle har en droplet på digital ocean. På serveren forventer vi at i alle har installeret MySql server og Tomcat. Vi forventer desuden at du kan deploye et webprojekt (en .war fil) og at vi kan tilgå projektet fra en browser via IP adressen på din droplet. |
| Gul    | Vi forventer at du kan tilgå din database via MySql workbench. Du skal desuden kunne vise at du har tænkt over sikkerheden ved at isolere rettighederne til den konto der kan bruges via workbench. Vi forventer at du kan vise hvordan du har sikret din droplet med SSH på en anden bruger så det ikke er muligt at bruge root user. |
| Rød    | Vis hvordan du kan lave dit web projekt på en måde, så den MySql user der bruges til CRUD operationerne på databasen har begrænsede rettigheder til kun at kunne operere på den anvendte database. Vis også hvordan du kan tilgå din droplet fra forskellige computere ved at operere på forskellige SSH nøgler (Hvert medlem i et team har sin egen konto med SSH adgang til serveren). |


```

```