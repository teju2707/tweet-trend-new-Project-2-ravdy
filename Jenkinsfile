pipeline {
    agent {
        node{
            label 'maven'
        
        }
    }
    environment {
        MAVEN_HOME = tool 'maven-3.6.3'
        PATH = "/opt/apache-maven-3.9.2/bin:${env.PATH}"
    }

    stages {
        stage('clone-code') {
            steps {
                git branch: 'main' , url: 'https://github.com/ravdy/tweet-trend-new.git'
            }
        }
    }
}


