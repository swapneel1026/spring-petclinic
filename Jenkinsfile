pipeline {
    agent any

    stages {
        stage('Debug') {
    steps {
        sh 'java -version'
        sh 'mvn -version'
        sh 'echo JAVA_HOME=$JAVA_HOME'
        sh 'which java'
        sh 'which mvn'
    }
}
        stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }
        
    }
        post{
            always{
                echo 'Pipeline ran succesfully'
            }
        }
}