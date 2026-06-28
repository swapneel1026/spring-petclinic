pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Junit Reports'){
            steps{
                junit 'target/surefire-reports/*.xml'
            }
        }
        
    }
        post{
            always{
                echo 'Pipeline ran succesfully'
            }
        }
}