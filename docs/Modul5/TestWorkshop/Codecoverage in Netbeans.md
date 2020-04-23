# Codecoverage in Netbeans
The **jacocoverage** tool can be used to say how much of the code is covered by your tests.

The tool can be installed into netbeans by:

1. In the tools menu, last item is "Plugins".
2. This brings up a little dialog box.
	- Select "available plugins" at the top
	- In the search field type "cover"
	- That should bring up the tool: "TikiOne JaCoCoverage"
	- Select it and press install.
	- Netbeans will need to restart.
3. You need to add a this to the `pom.xml` file (in the `plugins` section under the `build` section).

```xml
<plugin>
    <groupId>org.jacoco</groupId>
    <artifactId>jacoco-maven-plugin</artifactId>
    <version>0.7.7.201606060606</version>
    <executions>
        <execution>
            <goals>
                <goal>prepare-agent</goal>
            </goals>
        </execution>
        <execution>
            <id>report</id>
            <phase>prepare-package</phase>
            <goals>
                <goal>report</goal>
            </goals>
        </execution>
    </executions>
</plugin>
```

The tools run as part of the build process (clean and build). To see the results, right click on the project and a new menu item is available:

<img src="CoverageMenu.jpg" width="250">

This should open a window which looks like this ([For the LoginSample project](https://github.com/DAT2Sem2017E/Modul3LogInSample)):

![](CoverageResult.jpg)

You can click on a filename, and get a line by line result of which aspects og your code was touched by your tests. In the figure above, I wanted to test the UserMapper class, but there are some sql exceptions which are not thrown, which I am OK with.
