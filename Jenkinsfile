pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                    sh 'mvn clean compile'
            }
        }

        stage ('Testing Stage') {

            steps {
                    sh 'mvn teste'
            }
        }

    }
    post {
        unsuccessful{
            sh """curl -X POST -d '{"text": "Build is ${currentBuild.currentResult} - ${env.JOB_NAME}"}' -H "Content-Type:application/json" -s 'https://chat.googleapis.com/v1/spaces/AAAA51XHaso/messages?key=AIzaSyDdI0hCZtE6vySjMm-WEfRq3CPzqKqqsHI&token=XySqcJ720zTEkWFv-FVdpgCj1HCpswuXrJW1lRxBMPw%3D'"""
        }
    }
}