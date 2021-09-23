# PGDO_CM_Project_1
<h1>CI/CD Deployment Using Ansible CM Tool</h1>

<h2>Objective:</h2> 

Solution build should demonstrate below capabilities:
1.	Configure Jenkins server as Ansible provisioning machine
2.	Install Ansible plugins in Jenkins CI server
3.	Prepare Ansible playbook to run Maven build on Jenkins CI server
4.	Prepare Ansible playbook to execute deployment steps on the remote web container with restart of the web container post deployment

Project goal is to Automate Ansible integration with Jenkins CI server so that we can run and execute playbooks to deploy custom WAR files to a web container and then perform restart for the web container.


<h3>Tools required:</h3> Ansible, GitHub, Git, Linux (Ubuntu), Jenkins</br>

<h2>Important Artifacts in the project</h2>
1) maven playbook file (/maven.yaml) is used to install maven and do maven build in the CI server </br>
2) Main playbook (/main.yml) , tomcat ansible-role folders (/roles/tomcat/) and inventory folders (/inventories/) are important to deploy the java application in managed nodes</br>
3) Jenkinsfile (/Jenkinsfile) is the jenkins pipeline script written to exeute the CI/CD in stages to do the code build and deploy the changes to the managed nodes </br>
4) Java Web App (/src/main/webapp/) contains a simple login page webapp created with Servlets </br>
5) POM file (/pom.xml) to do build and package the application into a WAR file
6) Shell Script (/roles/tomcat/files/tomcat-initscript.sh) to start and stop tomcat server

<h2>System Requirements</h2>
1 Master Node - With Ubantu OS and 4 GB RAM minimum - Installed with Python3, Java8, Ansible, Jenkins and Git</br>
1..N Managed Nodes - with Ubantu OS and 4 GB RAM minimum - Python 3 installed</br>

<h2>Changes to be done while reusing the project</h2>
1) change the hosts in the inventory file (inventories/dev/hosts) </br>
2) In the Jenkins pipeline script file (/Jenkinsfile) , checkout stage related git clone url and branch has to be changed according to your github links.This stage in Jenkinsfile    is just used for displaying the Git repository fetch. </br>

<h2>Steps to Execute the Project:</h2>
<h4>Step 1:</h4> Master Node should have a user called 'jenkins' after the Jenkisn Installation, this user should be configured to connect to localhost with SSH.
<h4>Step 2:</h4> In every managed node, 'jenkins' user has to be created with root user privilege and a SSH connectivity has to be establised from master node jenkins user to managed node jenkins user
<h4>Step 3:</h4> Install Git and Ansible addin in the Jenkins server
<h4>Step 4:</h4> Create a Jenkins pipeline Job which is using the Jenkinsfile form this project repository, set the job trigger as Poll SCM pointing to this gihub repository
<h4>Step 5:</h4> Test the sample login web app java application runing in the managed nodes by accessing the url http://<Managed_node_ip>:8080/LoginWebApp-1/







