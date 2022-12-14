pipeline {
    agent any

    stages {
        stage('clone code') {
            steps {
                git 'https://github.com/vamshi-psy/hello-world.git'
            }
        }   
        
        stage('build') {
            steps {
                bat 'mvn clean install package'
            }
        }
        
        stage('deploy') {
            steps {
                deploy adapters: [tomcat8(credentialsId: 'tomcat', path: '', url: 'http://localhost:8090/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
