pipeline {
    agent { label 'jdk-17' }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/ksp99/spring-petclinic.git', branch: 'main' 
            }
        }
        stage('build') {
            steps {
                sh 'mvn package'
            }
        }
        stage('post build') {
            steps {
                junit  testResults: '**/surefire-reports/*.xml'
            }
        }    
    }
}

    
