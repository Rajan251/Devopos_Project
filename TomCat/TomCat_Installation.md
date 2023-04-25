Tomcat installation on Windows 10.


Pre-requisites
1.Java 11


Step 1: Install Apache Tomcat
    Download tomcat packages from https://tomcat.apache.org/download-10.cgi onto /opt on EC2 instance
    Note: Make sure you change <version> with the tomcat version which you download.


    On the Download page, scroll down and locate the Binary Distributions area.

    In the Core list, depending on the installation type you prefer, click the download link for the Windows Service Installer or the 32bit/64bit Windows zip file.

Step 2: Install Tomcat
    Install Tomcat via the Windows Service Installer for an automated and wizard-guided experience. The service installer installs the Tomcat service and runs it automatically when the system boots.

Method 1: Install Tomcat Using the Windows Service Installer
    Follow the steps below to install Tomcat using the Windows Service Installer.

    1. Open the downloaded Windows Service Installer file to start the installation process.

    2. In the Tomcat Setup welcome screen, click Next to proceed.

    3. Read the License Agreement and if you agree to the terms, click I Agree to proceed to the next step.

    4. In the Tomcat component selection screen, choose Full in the dropdown menu to ensure the wizard installs the Tomcat Host Manager and Servlet and JSP examples web applications. Alternatively, keep the default Normal installation type and click Next.

    5. The next step configures the Tomcat server. For instance, enter the Administrator login credentials or choose a different connection port. When finished, click Next to proceed to the next step.

    6. The next step requires you to enter the full path to the JRE directory on your system. The wizard auto-completes this if you have previously set up the Java environment variables. Click Next to proceed to the next step.

    7. Choose the Tomcat server install location or keep the default one and click Install.

    8. Check the Run Apache Tomcat box to start the service after the installation finishes. Optionally, check the Show Readme box to see the Readme file. To complete the installation, click Finish.

    9. A popup window appears that starts the Tomcat service. After the process completes, the window closes automatically. The Apache Tomcat web server is now successfully installed .

    4. The default connection port is 8080. To choose a different port, edit the server.xml file with a text editor, such as Notepad++, and locate the following lines:

<Connector port="8080" protocol="HTTP/1.1"
           connectionTimeout="20000"
           redirectPort="8443" />

    Change the connector port number to any number between 1024 and 65535.

Access the server using a browser as an HTTP client. Browse to http://localhost:8080 and access the Tomcat welcome page to ensure the server works.

In addition, use the Developer Quick Start links to see more information about the server and start using and configuring the server.