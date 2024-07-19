pipeline {
    agent any

    tools {
        maven 'M3'
    }
    
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }
        stage('Poll SCM Complete') {
            steps {
                echo "Poll SCM Succesfull"
            }
        }
    }
}
