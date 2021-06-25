node {
    try{
        stage ('Compile Stage') {


                    sh  'mvn clean compile'

        }

        stage ('Testing Stage') {


                    sh 'mvn test'

        }
    }catch(err){
        stage ('Failure Notification') {
           sh """curl -X POST -d '{"text": " ${env.JOB_NAME} build status is FAILURE"}' -H "Content-Type:application/json" -s 'https://chat.googleapis.com/v1/spaces/AAAA51XHaso/messages?key=AIzaSyDdI0hCZtE6vySjMm-WEfRq3CPzqKqqsHI&token=XySqcJ720zTEkWFv-FVdpgCj1HCpswuXrJW1lRxBMPw%3D'"""
        }
        throw err
    }
}

