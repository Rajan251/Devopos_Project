Install Jenkins on TomCat Server on windows

    Jenkins is a self-contained Java-based program, ready to run out-of-the-box, with packages for Windows, Mac OS X and other Unix-like operating systems. As an extensible automation server, Jenkins can be used as a simple CI server or turned into the continuous delivery hub for any project.


Prerequisites

    1.Java 11 should be installed


Install Jenkins

    Step 1 :- Download Java 8 or 11 as Jenkins supports that.

    Installing Java should not be problem. Visit JDK Download web page and download as per your operating system and processor. DO NOT FORGET to set JAVA_HOME path in your system as Environment variables. If you face any issue in installing Java and setting up path, let me know in comments or send me a mail.

    Verify Java installation:- >java -version

    Verify JAVA_HOME path setup:- >SET JAVA_HOME



Step 2 :- Download Apace Tomcat Server


Navigate to Apache Tomcat Server(https://tomcat.apache.org/) Website and select latest version. I will 
install Tomcat 9 as Tomcat 10 is an Alpha version.

Click on Tomcat 9 ( In my case) and go to Binary Distribution section and download appropriate as per your OS and processor. I will download for 64 bit Windows.


Step 3 – Download Jenkins.war file

    Download Jenkins.war file

Step 4:- Copy jenkins.war file in webapps folder of Apache Tomcat Server

    Copy jenkins.war file and go to extracted Apache tomcat folder. There you will find a folder named “webapps”.

Step 5:- Start Apache Tomcat Server

    Navigate to bin folder of Apache Tomcat Server. There you will find two window batch files:-

    startup – To start tomcat server. By default it starts at 8080 port.
    shutdown – To shutdown running tomcat server

    Note – To start tomcat server on other port, go to conf folder in Apache tomcat folder. You will find a server.xml file. Change port to whatever you want. This is optional step.

<Connector port="8080" Protocol="HTTP/1.1"
           coneectionTimeout="20000"
           redirectPort="8443"
<!-- A "Connector" Using the shared thread pool-->

    To start tomcat server, click on “startup” window batch file. It will open command prompt and start server. Notice that it will deploy war file as well.

    Since Jenkins is being installed first time, it will show that Jenkins initial setup is required and will generate an initial password which is required to unlock jenkins. No need to copy as it will be in jenkins installation file directory as wel. Path will be provided in consol.


    Now if you go to webapps folder, you will see a “jenkins” folder is created.



Step 6 – Hit Tomcat URL

    Apache tomcat will start at 8080 by default. We have not changed any port so type “localhost:8080” in a web browser. You will see below page and a message on successful installation of Tomcat.

Step 7 :- Launch Jenkins from Apache URL

    To access jenkins, just append /jenkins in above URL. You will be asked to unlock Jenkins by providing an initial admin password which is shown in Step 5 . You can copy it from file location to paste here. Submit password and click on Continue.

Step 8:- Install plugins

    It will ask you to Customize jenkins by installing a good number of plugins. You can manually choose or install all suggested plugins. I will recommend to go for “Install suggested plugins“.

    Plugin installation will take time. Let it be completed. Now it will ask you to create first admin user. You can skip it but better to create and click on “Save and Continue” button.

    Now it will ask you to configure Jenkins URL. If you are on network, you need to change it so that you can access from other machine as well. Let’s not to worry about that and click on “Save and Finish” button.

    You are done now. Click on “Start using Jenkins“.

Shutdown running Tomcat server

