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
        always{
            googlechatnotification url: 'https://chat.googleapis.com/v1/spaces/AAAA51XHaso/messages?key=AIzaSyDdI0hCZtE6vySjMm-WEfRq3CPzqKqqsHI&token=lFPWpu6VKNqMNBQy85PqrOv9Tn-AmXA91jrRGnYeh5A%3D', message: '@Lucas Andrade Build status is ${currentBuild.currentResult}', notifyAborted: 'true', notifyFailure: 'true', notifyNotBuilt: 'true', notifySuccess: 'false', notifyUnstable: 'true', notifyBackToNormal: 'true', suppressInfoLoggers: 'true', sameThreadNotification: 'true'
        }
    }
}