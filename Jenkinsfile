pipeline {
    agent any
    tools {
        maven 'Maven'
        jdk 'JDK'
    }
    stages {
        stage ('Initialize') {
            steps {
		        echo "PATH = ${PATH}"
                echo "M2_HOME = ${M2_HOME}"
            }
        }

        stage ('Build') {
            steps {
		        withMaven(maven : 'M2_HOME')
                sh 'mvn clean compie' 
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
    }
}
