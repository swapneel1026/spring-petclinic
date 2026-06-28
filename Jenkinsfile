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
        stage('Package'){
            steps{
                sh 'mvn package -DskipTests'
            }
        }
        stage('Artifact'){
            steps{
                archiveArtifacts artifacts: "target/*.jar"
            }
        }
        
    }
        post{
            always{
                echo 'Pipeline ran succesfully'
            }
        }
}