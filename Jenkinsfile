pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }

    post {
        always {
            echo "I will always say Hello Aggain!"
        }
        success {
            echo "Yay, success!"
        }
        failure {
            echo "Oh no, failure"
        }
        cleanup {
            echo "Cleanup, don't care success of fail"
        }
    }
}
