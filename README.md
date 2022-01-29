# EdurekaDevOpsTestServer


Devops - Test Server deployment automation - Edureka Project

 
Procedure: 

 1. In AWS management console, create 2 CentOS 7 VMS, Jenkins Master and Test server with free tiers and default seteings.
 2. Install Git, Ansible , Jenkins and Docker on Master Server(Jenkins Server) and do the needed settings.
 3. Git Settings - for source code version control
    a. Create a github account and master branch as main. Push the local code from working directory to git.
    b. Files to be created are Readme, Jenkinsfile, ansible playbook, server details for ansible configuration, docker file and PHP website.
 4. Ansible Settings - server configuration managemnet
    a. Install Ansible jenkins plugin and configure it on global tool configuration. This is for server configurations in bulk servers.
    b. Change your test server ip in servers.inv. Here we are provisioning one test server, but can be automated for many.
 5. Docker Settings - for containerization and storage of images
    a. Create a Docker File to assemble an image of php website and automate a build. Store it in Docker Hub repo.
    b. Configure Docker Hub credentials in Jenkins pipeline for Docker python image build and Docker push.
 6. Jenkins Settings - for  continuouse integration
    a. Login to Jenkins console and do the needed configurations for Git, Jenkins, Docker, Ansible.
    b. Do necessary configuration in pipeline ex: poll scm etc.
    c. Create a pipeline job using Generate Pipeline Script option in Jenkins console and use default name Jenkinsfile.
    d. Add jenkins user to docker for automation.
 7. Once all the configurations an pipeline is successfully built, for every new commit in Github main branch, a job will be created in Jenkins and the Test server provisioning will be automatically triggered
 
