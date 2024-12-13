# CI/CD Pipeline with Jenkins, SonarQube, Nexus, Ansible, and AWS

![jenkins ansible project architecture](https://github.com/Ahmed-Daoudi/jenkins-ansible-project/blob/master/jenkins-ansible-architecture.png)

## Project Overview
This project implements a fully automated CI/CD pipeline integrating Jenkins, SonarQube, Nexus Repository, and Ansible for efficient code deployment and quality assurance. The pipeline handles the complete lifecycle of application development, from fetching code to deployment on AWS infrastructure.

### Key Components
1. **Jenkins**: Orchestrates the CI/CD pipeline by automating code fetching, testing, building, and deployment.
2. **SonarQube**: Ensures code quality by performing static code analysis and generating quality reports.
3. **Nexus Repository**: Acts as a central repository for managing build artifacts.
4. **Ansible**: Automates the deployment of build artifacts to Tomcat servers.
5. **AWS**: Hosts the infrastructure for the pipeline, including Jenkins, SonarQube, Nexus, and Tomcat servers.
6. **Slack**: Provides real-time notifications for pipeline status and events.

---

## Prerequisites
The project requires the following tools and configurations:
- **AWS Infrastructure**: Instances for Jenkins, SonarQube, Nexus, Ansible, and Tomcat servers.
- **Git Repository**: A source repository for the application code.
- **Jenkins Plugins**: Plugins for Git, Maven, Slack notifications, and SonarQube integration.
- **SonarQube Configuration**: Integrated with Jenkins for automated code quality analysis.
- **Nexus Repository Setup**: Configured to host build artifacts.
- **Ansible Playbooks**: Configured for automated artifact deployment and server configuration.
- **Slack Webhook**: Configured for notifications.

---

## Setup Instructions

### AWS Infrastructure Setup
1. **Launch EC2 Instances**:
   - Create separate EC2 instances for Jenkins, SonarQube, Nexus, Ansible, and Tomcat.
   - Assign appropriate IAM roles and security groups for communication between instances.

2. **Install Required Tools**:
   - On each instance, install necessary tools like Java, Git, Maven, and Docker (if applicable).

### Jenkins Setup
1. **Install Jenkins**:
   - Install Jenkins on the designated EC2 instance.
   - Configure Jenkins by installing required plugins (Git, Maven Integration, SonarQube, Slack).

2. **Pipeline Configuration**:
   - Create a new pipeline job in Jenkins.
   - Configure the job to fetch code from the Git repository and execute the pipeline steps.

### SonarQube Setup
1. **Install SonarQube**:
   - Install and configure SonarQube on its EC2 instance.
   - Set up quality gates and integrate SonarQube with Jenkins.

2. **SonarQube Scanner**:
   - Install and configure the SonarQube Scanner on the Jenkins instance.

### Nexus Repository Setup
1. **Install Nexus**:
   - Install Nexus Repository Manager on the designated EC2 instance.
   - Configure a hosted repository for storing build artifacts.

2. **Integration with Jenkins**:
   - Add Nexus credentials and repository details in Jenkins.

### Ansible Setup
1. **Install Ansible**:
   - Install Ansible on the designated EC2 instance.

2. **Configure Playbooks**:
   - Create Ansible playbooks for deploying artifacts and configuring Tomcat servers.

3. **Run Playbooks**:
   - Use the command:
     ```bash
     ansible-playbook -i inventory_file playbook.yml
     ```

### Tomcat Server Setup
1. **Install Tomcat**:
   - Install Apache Tomcat on the designated EC2 instance.
   - Configure Tomcat to host the deployed application.

2. **Basic Commands**:
   - Start Tomcat:
     ```bash
     sudo systemctl start tomcat
     ```
   - Stop Tomcat:
     ```bash
     sudo systemctl stop tomcat
     ```
   - Restart Tomcat:
     ```bash
     sudo systemctl restart tomcat
     ```

### Slack Integration
1. **Create a Slack Webhook**:
   - Create an incoming webhook in your Slack workspace.

2. **Configure Jenkins**:
   - Add the Slack webhook URL in Jenkins and configure notifications for pipeline events.

---

## Pipeline Workflow
1. **Code Fetching**: Jenkins fetches the latest code from the Git repository.
2. **Code Testing**: Automated tests are executed to validate the code.
3. **Static Code Analysis**: SonarQube analyzes the code and enforces quality gates.
4. **Build and Artifact Management**: Maven builds the application, and the artifacts are stored in Nexus Repository.
5. **Automated Deployment**: Ansible deploys the artifacts to Tomcat servers and configures the environment.
6. **Notifications**: Slack updates stakeholders with pipeline status and outcomes.

---

## Conclusion
This project showcases a robust CI/CD pipeline that automates the entire application lifecycle, from code testing to deployment. By integrating Jenkins, SonarQube, Nexus, and Ansible, the pipeline ensures high-quality code, efficient artifact management, and seamless deployment. AWS provides a scalable and secure environment for hosting the infrastructure, making the solution highly reliable and production-ready.

For contributions or queries, feel free to reach out through the repository issues section.

