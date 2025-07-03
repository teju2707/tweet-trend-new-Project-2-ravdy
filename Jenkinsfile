pipeline {
    agent {
        node {
            label 'MAVEN'
        }
    }
}

  stages {
    stage ('clone-code') {
        steps {
            git branch: 'main', url: 'https://github.com/teju2707/tweet-trend-new-Project-2-ravdy.git'
        }
    }
  }

}
