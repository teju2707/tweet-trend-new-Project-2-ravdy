pipeline {
    agent {
        node{
            label 'maven'
        
        }
    }
    environment {
        MAVEN_HOME = tool 'maven-3.9.2'
        PATH = "/opt/apache-maven-3.9.2/bin:PATH"
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean deploy '
            }
        }
    }
}


