# Install Maven 3.3

Make sure to use a 64-bit version, so you can run tests with enough memory.

1. Install a binary package manager if you don't have one, e.g., for windows use https://chocolatey.org/
2. Set `JAVA_HOME`. *e.g.*, in Admin command window:

    setx /M JAVA_HOME "C:\Program Files\Java\jre1.8.0_45"

3. Create a hello world maven project

    mvn -B archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes -DgroupId=altcode -DartifactId=devi

4. Create a project file that Eclipse can understand.

    mvn eclipse:eclipse

5. Get `m2e`, to help being able to build stuff in Eclipse. Add repo to site, install: http://download.eclipse.org/technology/m2e/releases/

6. Import existing maven project into eclipse.

7. Search maven central for "mysql jdbc driver".

8. Edit `pom.xml` file to add new dependancy.

9. Run `mvn test` to run unit tests. Notice that new dependency is downloaded.

# Errors

Set variable `M2_REPO` in Eclipse.

    mvn -Declipse.workspace="C:\Users\Chris\workspace" eclipse:configure-workspace
