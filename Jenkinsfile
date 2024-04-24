pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo('Start Build')
                sleep(10)
                sh './mvnw clean'
                sh './mvnw compile test-compile'
                echo('Finish Build')
            }
        }
        stage('Test') {
            steps {
                echo('Start Test')
                sleep(5)
                sh './mvnw test'
                echo('Finish Test')
            }
        }
        stage('Deploy') {
            steps {
                echo('Start Deploy')
                sleep(5)
                echo('Finish Deploy')
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
