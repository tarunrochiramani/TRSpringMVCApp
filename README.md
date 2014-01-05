This is a sample Spring MVC app created with the following steps
1) Create a maven repo: mvn archetype:generate -DgroupId=com.tarun -DartifactId=TRSpringMVCApp -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false

2) Add following dependency
    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-webmvc</artifactId>
        <version>3.0.0.RELEASE</version>
    </dependency>

3) Change the web.xml contents with
<web-app version="2.4"
         xmlns="http://java.sun.com/xml/ns/j2ee"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://java.sun.com/xml/ns/j2ee
         http://java.sun.com/xml/ns/j2ee/web-app_2_4.xsd">
    <welcome-file-list>
        <welcome-file>
            index.jsp
        </welcome-file>
    </welcome-file-list>
</web-app>

4) Run mvn clean package from the level where pom.xml exists
5) Install Tomcat. following are contents from http://wolfpaulus.com/jounal/mac/tomcat7/ 
* Download a binary distribution of the core module: apache-tomcat-7.0.47.tar.gz from here. I picked the tar.gz in Binary Distributions / Core section.
* Opening/unarchiving the archive will create a folder structure in your Downloads folder: (btw, this free Unarchiver app is perfect for all kinds of compressed files and superior to the built-in Archive Utility.app)
~/Downloads/apache-tomcat-7.0.47
* Open to Terminal app to move the unarchived distribution to /usr/local
sudo mkdir -p /usr/local
sudo mv ~/Downloads/apache-tomcat-7.0.47 /usr/local
* To make it easy to replace this release with future releases, we are going to create a symbolic link that we are going to use when referring to Tomcat (after removing the old link, you might have from installing a previous version):
sudo rm -f /Library/Tomcat
sudo ln -s /usr/local/apache-tomcat-7.0.47 /Library/Tomcat
* Change ownership of the /Library/Tomcat folder hierarchy:
sudo chown -R <your_username> /Library/Tomcat
* Make all scripts executable:
sudo chmod +x /Library/Tomcat/bin/*.sh


