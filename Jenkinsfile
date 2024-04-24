pipeline {
    agent any

    options {
        timeout(time: 1, unit: 'HOURS') 
    }

    parameters {
        string(name: 'AUTHOR', defaultValue: 'R. Farizd', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    
    stages {
        stage('Build') {
            options {
                timeout(time: 3, unit: 'MINUTES') 
            }
            steps {
                echo('Start Build')
                echo "Hello ${params.AUTHOR}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"
                sleep(3)
                sh './mvnw clean'
                sh './mvnw compile test-compile'
                echo('Finish Build')
            }
        }
        stage('Test') {
            options {
                timeout(time: 3, unit: 'MINUTES') 
            }
            steps {
                echo('Start Test')
                sleep(3)
                sh './mvnw test'
                echo('Finish Test')
            }
        }
        stage('Deploy') {
            options {
                timeout(time: 3, unit: 'MINUTES') 
            }
            steps {
                echo('Start Deploy')
                sleep(3)
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
