pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Application is in Building Phase'
                bat 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                echo 'Application is in Testing Phase'
                bat 'mvn test'
            }
        }
        stage('Deploy to Cloudhub') { 
            environment {
                ANYPOINT_CREDENTIALS = credentials('platform.credentials')
            }
            steps {
                bat 'mvn deploy -DmuleDeploy -DmuleVersion=4.5.4 -Dusername=Chaithanya1 -Dpassword=Chaithu@516 -DworkerType=MICRO -Dworkers=1 -Dregion=us-west-2'
            }
        }
    }
}
