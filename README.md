## Jenkins Documentation

### What is Jenkins

An open-source automation server that enables developers around the world to reliably build, test, and deploy their software

### Jenkins Installation

    Cloud           - AWS
    Instance Type   - t2.medium
    CPU Cores       - 2
    Memory          - 4 GB
    Storage         - 10 GB
    OS              - Ubuntu 22.02 

Install Java

    sudo apt update && sudo apt install openjdk-11-jre

Check the Java version

    java -version

    openjdk version "11.0.12" 2021-07-20
    OpenJDK Runtime Environment (build 11.0.12+7-post-Debian-2)
    OpenJDK 64-Bit Server VM (build 11.0.12+7-post-Debian-2, mixed mode, sharing)

Install Jenkins

    curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
    /usr/share/keyrings/jenkins-keyring.asc > /dev/null

    echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
    https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null

    sudo apt-get update && sudo apt-get install jenkins

Start Jenkins 

    sudo systemctl start jenkins

Check Status of Jenkins

    sudo systemctl status jenkins

Enable Jenkins service to start at boot time

    sudo systemctl enable jenkins

Firewall Exception

    YOURPORT=8080
    PERM="--permanent"
    SERV="$PERM --service=jenkins"

    firewall-cmd $PERM --new-service=jenkins
    firewall-cmd $SERV --set-short="Jenkins ports"
    firewall-cmd $SERV --set-description="Jenkins port exceptions"
    firewall-cmd $SERV --add-port=$YOURPORT/tcp
    firewall-cmd $PERM --add-service=jenkins
    firewall-cmd --zone=public --add-service=http --permanent
    firewall-cmd --reload

Login into Jenkins Web Console

    Type https://localhost:8080 in your Browser if any exceptions accept them and proceed

Unlock Jenkins Password using the below command

    sudo cat /var/lib/jenkins/secrets/initialAdminPassword

### Jenkins plugins (DevOps)

1. Kubernetes
2. Swarm
3. Amazon Elastic Container Service
4. Azure Container Service
5. Dashboard View
6. View Job Filters
7. Folders
8. Jira
9. Performance
10. Performance Publisher
11. Job DSL
12. Build Pipeline
13. Multijob
14. Pipeline
15. Monitoring
16. Disk-usage
17. Metrics
18. Mailer
19. SCM API
20. Git
21. GitHub Integration
22. Subversion
23. Test Results Analyzer
24. bootstrapped-multi-test-results-report
25. JUnit
26. Publish Over SSH

### Jenkins Pipeline Stages

1. Build 
2. Test: Integration & Quality
3. Test: Functional
4. Test: Load & Security
5. Approval
6. Deploy: Prod

### Jenkins Descriptive Pipelines

1. [Pipeline](https://github.com/savanarohit/Jenkins/blob/main/Jenkins_Descriptive_Pipeline/1_pipeline/Jenkinsfile)
2. [Github](https://github.com/savanarohit/Jenkins/blob/main/Jenkins_Descriptive_Pipeline/2_github/Jenkinsfile)
3. [Github Poll SCM](https://github.com/savanarohit/Jenkins/blob/main/Jenkins_Descriptive_Pipeline/3_github_poll_scm/Jenkinsfile)
4. [MultiBranch](https://github.com/savanarohit/Jenkins/blob/main/Jenkins_Descriptive_Pipeline/4_multibranch/Jenkinsfile)
5. [Parameterized](https://github.com/savanarohit/Jenkins/tree/main/Jenkins_Descriptive_Pipeline/5_parameterized)
6. [Variable](https://github.com/savanarohit/Jenkins/tree/main/Jenkins_Descriptive_Pipeline/6_variable)
7. [Multiple_Jenkinsfile](https://github.com/savanarohit/Jenkins/tree/main/Jenkins_Descriptive_Pipeline/7_multiple_jenkinsfile)
8. [Delay](https://github.com/savanarohit/Jenkins/blob/main/Jenkins_Descriptive_Pipeline/8_delay/Jenkinsfile)
9. [Groovy](https://github.com/savanarohit/Jenkins/tree/main/Jenkins_Descriptive_Pipeline/9_groovy)
10. [Job_from_job](https://github.com/savanarohit/Jenkins/blob/main/Jenkins_Descriptive_Pipeline/10_job_from_job/Jenkinsfile)
11. [Pass_Parameter_between_Job](https://github.com/savanarohit/Jenkins/blob/main/Jenkins_Descriptive_Pipeline/11_pass_parameter_between_job/Jenkinsfile)
12. [Multiple_Bash_Command](https://github.com/savanarohit/Jenkins/blob/main/Jenkins_Descriptive_Pipeline/12_multiline_bash_command/Jenkinsfile)