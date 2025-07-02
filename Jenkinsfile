pipeline {
    agent {
        node {
            label 'maven'
        }
    }

    environment {
        PATH = "/opt/apache-maven-3.9.2/bin:$PATH"
        SONAR_TOKEN = credentials('sonar-token')
    }

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the project...'
                    sh 'mvn clean package -DskipTests'
                }
            }
        }
        stage('SonarQube Analysis') {
            environment {
                scannerHome = tool name: 'TEJU-SonarQube-Scanner', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
            }
            steps {
                script {
                    echo 'Running SonarQube analysis...'
                    withSonarQubeEnv('TEJU-sonarqube-server') {
                        sh """
                            ${scannerHome}/bin/sonar-scanner \
                            -Dsonar.projectKey=teju2707_tweet-trend-new-Project-2-ravdy \
                            -Dsonar.organization=teju2707 \
                            -Dsonar.host.url=https://sonarcloud.io \
                            -Dsonar.login=${SONAR_TOKEN}
                        """
                    }
                }
            }
        }
    }

   
