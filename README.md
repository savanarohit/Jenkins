# Learn Jenkins from basic to advance

## Jenkins Installation on AWS EC2 Ubuntu 22.04 Instance

## Install Java

sudo apt update

sudo apt install openjdk-11-jre

## Check java version

java -version

openjdk version "11.0.12" 2021-07-20
OpenJDK Runtime Environment (build 11.0.12+7-post-Debian-2)
OpenJDK 64-Bit Server VM (build 11.0.12+7-post-Debian-2, mixed mode, sharing)

## Install Jennkins

curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
/usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
/etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt-get update

sudo apt-get install jenkins

## Start Jenkins 

sudo systemctl start jenkins

## Check Status of Jenkins

sudo systemctl status jenkins

## Enable Jenkins service to start at boot time

sudo systemctl enable jenkins

## Firewall Exception

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

## Login into Jenkins Web Console

Type https://localhost:8080 in your fav browser if any exception accept it and proceed

## Unlock Jenkins Password using below command

sudo cat /var/lib/jenkins/secrets/initialAdminPassword

## Jenkins plugins for DevOps

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

## Sample Jenkins Pipeline stages

1. Build 
2. Test: Integration & Quality
3. Test: Functional
4. Test: Loand & Security
5. Approval
6. Deploy: Prod
