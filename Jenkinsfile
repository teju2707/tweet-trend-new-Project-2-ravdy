pipeline {
    agent {
        node {
            label 'MAVEN'
        }
    }

    environment {
        MAVEN_PATH = '/opt/maven/bin:$PATH'
    }
    stages {
        stage(Build) {
            steps {
                script {
                    sh 'mvn clean deploy -DskipTests'
                }
            }
        }
    }
}