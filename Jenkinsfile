pipeline {
    agent any

    environment {
        SONAR_TOKEN = credentials('sonar-token')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'mvn clean package -DskipTests'
            }
        }
        stage('SonarQube Analysis') {
            environment {
                scannerHome = tool name: 'TEJU-SonarQube-Scanner'
            }
            steps {
                withSonarQubeEnv('TEJU-sonarqube-server') {
                    sh """
                        ${scannerHome}/bin/sonar-scanner \
                        -Dsonar.projectKey=teju2707_tweet-trend-new-Project-2-ravdy \
                        -Dsonar.host.url=http://34.227.142.236:9090 \
                        -Dsonar.login=${SONAR_TOKEN}
                    """
                }
            }
        }
    }
}
