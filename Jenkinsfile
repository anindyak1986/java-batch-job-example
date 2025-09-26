pipeline {
    agent none
    tools {
        jdk 'JDK21'
        maven 'Maven3'
    }
    stages {
        stage('Checkout') {
            steps {
                // write your logic here
                echo 'Checking out the code'
                git "https://github.com/anindyak1986/java-batch-job-example.git"
            }
        }
        stage('Build') {
            // write your logic here
            steps {
                echo 'Installing dependencies'
                bat "mvn clean install -DskipTests=true"
                bat "mvn clean compile"
            }
                
        }
        stage('Run Application') {
            // write your logic here
            steps {
                echo 'running'
            }
        }
        stage('Test') {
            // write your logic here
            steps {
                echo 'Running JUnit tests'
                bat "mvn test"
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Post Build Notification') {
            // write your logic here
            steps {
                echo 'post build'
            }
    }
    }
}
