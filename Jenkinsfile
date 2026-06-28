pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }
        // stage('Test'){
        //     steps{
        //         sh 'mvn test'
        //     }
        // }
        stage('Package'){
            steps{
                sh 'mvn package'
            }
        }
        stage('Junit Reports'){
            steps{
                junit 'target/surefire-reports/*.xml'
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
                echo 'Pipeline ran succesfully... Congratulations'
            }
        }
}