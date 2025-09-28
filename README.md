
1.	Create an EC2
1.1	Use “instance type” as “t2.micro”.
1.2	Enable inbound rule for port 8080.
1.3	Allocate Elastic IP.
2.	Connect to EC2 via SSH.
2.1	Use Command “ssh -I ‘Path-to-keyFile.pem’ ubuntu@publicIP”
3.	Run below command to update and upgrade EC2.
3.1	sudo apt update
3.2	sudo apt upgrade
4.	Install “Open jdk Java Jre”
4.1	use command “sudo apt install fontconfig openjdk-21-jre”
4.2	Run “java -version” to verify if its installed
 

5.	Follow below steps to install Jenkins.
5.1	Run “sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \ https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key”
 
5.2	Run “echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null”
 
5.3	Run “sudo apt update”
 
5.4	Run “sudo apt install jenkins”
 

6.	Check status of “Jenkins”
6.1	Run “sudo systemctl status jenkins”
 

Since it is already running, we don’t have to start Jenkins, if it was not running, we need to start “jenkins” by running “sudo systemctl start jenkins”

7.	To setup and configure Jenkins, follow below steps.
7.1	 Navigate to “PublicIPAddress:8080” 
Enter “administrator Password” by reading the file located at “/var/lib/Jenkins/secrets/initialAdminPassword”.
Run “sudo cat /var/lib/Jenkins/secrets/initialAdminPassword” to read the file
7.2	Click on “Install Suggested Plugins”
 

7.3	Enter details and click on “Save and Continue”
 

7.4	Click on “Save and finish”
 

7.5	Jenkins set up is completed. Click on “Start using Jenkins”
 

8.	Configure Jenkins with Python and necessary plugins
8.1	Go to “Manage Jenkins” and click on “Plugins”
 
8.2	Search for “Python” and install the required plugins.
 
8.3	Once all the plugins are installed, return to the Jenkins Dashboard.
9.	Fork the provided Python web application repository on GitHub (provide a link to a sample Python web application repository).
9.1	Navigate to https://github.com/UnpredictablePrashant/FlaskTest.git and fork the repository.
 

10.	 Clone the forked repository into your Jenkins server.
10.1	From Jenkins Dashboard, click on “New Item” > Freestyle Project.     
10.2	Provide the Repository URL and Branch. Click on Apply and then Save.
   	 
11.	Jenkins Pipeline
11.1	Create a Jenkinsfile in the root of Python application repository and Commit Changes.
 

11.2	Go to Jenkins Dashboard and then navigate to the item which has been forked. Click on “Build Now”
 

11.3	Finished:SUCCESS is observed in the output
