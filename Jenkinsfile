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
                    sh 'mvn test'
            }
        }

    }
    post {
        always{
            sh 'body="{\"text\": \"Falha na pipeline - Datahub - Schema\"}"'
            sh	'curl -H "Content-Type: application/json" \
            	  -X POST \
            	  -d "$body" \
            	  -s "https://chat.googleapis.com/v1/spaces/AAAA51XHaso/messages?key=AIzaSyDdI0hCZtE6vySjMm-WEfRq3CPzqKqqsHI&token=XySqcJ720zTEkWFv-FVdpgCj1HCpswuXrJW1lRxBMPw%3D"'
        }
    }
}