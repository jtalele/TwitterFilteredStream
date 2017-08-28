# TwitterFilteredStream


Deployment On Anypoint Platform
1. Login to Anypoint platform
2. Runtime manager - deploy application 
3. Select appication zip file. Set number of workers and size.
4. Set the property to dev/prod
5. Deploy application.


Deployment on premise
1. Copy the zip file.
2. Paste the application’s zip file into the apps folder of Mule ESB Standalone
3. Apps then extracts and deploys it automatically



Using Jenkins
1. mavenize a project 
2. Create Maven project in Jenkins
3. Add git repo location and user/pass
4. In Build section pom.xml, Goal - clean package mule:deploy

Add Below plugin in pom.xml
<plugin>
    <groupId>org.mule.tools.maven</groupId>
    <artifactId>mule-maven-plugin</artifactId>
    <version>2.0</version>
    <configuration>
        <deploymentType>cloudhub</deploymentType>
        <muleVersion>3.8.3</muleVersion>               <!-- This is the runtime version as it appears on the CloudHub interface -->
        <username>jtalele_2</username>
        <password>LearnMu1e</password>
        <environment>Production</environment>
    </configuration>
    <executions>
        <execution>
            <id>deploy</id>
            <phase>deploy</phase>
            <goals>
                <goal>deploy</goal>
            </goals>
        </execution>
    </executions>
</plugin>
