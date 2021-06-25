node {
    try{
        stage ('Compile Stage') {


                    sh  'mvn clean compile'

        }

        stage ('Testing Stage') {


                    sh 'mvn teste'

        }
    }catch(e){
        stage ('Failure Notification') {
           echo 'echo ${e}'
           sh """curl -X POST -d '{"text": " ${env.JOB_NAME} build status is ${currentBuild.currentResult}"}' -H "Content-Type:application/json" -s 'https://chat.googleapis.com/v1/spaces/AAAA51XHaso/messages?key=AIzaSyDdI0hCZtE6vySjMm-WEfRq3CPzqKqqsHI&token=XySqcJ720zTEkWFv-FVdpgCj1HCpswuXrJW1lRxBMPw%3D'"""
        }
    }
}

