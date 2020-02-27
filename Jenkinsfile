pipeline {
    agent any
    tools {
        maven 'Maven 3.6.1'
        jdk 'jdk1.8.0_211'
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${C:\Program Files\Java\jdk1.8.0_211}"
                    echo "M2_HOME = ${C:\Program Files\apache-maven}"
                '''
            }
        }

        stage ('Build') {
            steps {
                sh 'mvn package' 
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
    }
}
