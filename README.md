# PGDO_CM_Project_1
<h1>CI/CD Deployment Using Ansible CM Tool</h1>

<h2>Objective:</h2> 

Solution build should demonstrate below capabilities:
1.	Configure Jenkins server as Ansible provisioning machine
2.	Install Ansible plugins in Jenkins CI server
3.	Prepare Ansible playbook to run Maven build on Jenkins CI server
4.	Prepare Ansible playbook to execute deployment steps on the remote web container with restart of the web container post deployment

Project goal is to Automate Ansible integration with Jenkins CI server so that we can run and execute playbooks to deploy custom WAR files to a web container and then perform restart for the web container.


<h3>Tools required:</h3> Ansible, GitHub, Git, Linux (Ubuntu), Jenkins

<h2>Changes to be done while reusing the project</h2>
1) change the hosts in the inventory file (inventories/dev/hosts) </br>
2) In the Jenkinsfile, checkout stage related git clone url and branch has to be changed according to your github links.This stage in Jenkinsfile is just used for      displaying the Git repository fetch. </br>

<h2>Important Artifacts in the project</h2>
1) maven.yaml file (playbook) is used to install maven and do maven build in the CI server </br>
2) main.yml , tomcat role folders and inventory files in the ansible role directory are important to deploy the java application in managed nodes </br>
3) Jenkinsfile is the jenkins pipeline script written to exeute the CI/CD in stages to do the code build and deploy the changes to manages nodes </br>




