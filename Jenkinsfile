 pipeline {

  agent any

   environment {
     
        AWS_SAM_STACK_NAME = "my-lambda-stack"
        AWS_DEFAULT_REGION = "ap-south-1"
        AWS_ACCESS_KEY_ID = credentials('aws-access-key')
        AWS_SECRET_ACCESS_KEY = credentials('aws-secret-key')

   }

     stages{

       stage('Setup'){

        steps {

          sh '''
          pip3 install --break-system-package -r tests/requirements.txt
          '''

        }

       }

    stage('Build'){

      steps {

        sh "sam build -t template.yaml"

      }

     }

    stage('Deploy'){

     steps {

       sh "sam deploy -t template.yaml --no-confirm-changeset --no-fail-on-empty-changeset"

      }

    }
      stage ('Delete resources') {
       steps{

        sh "sam delete --no-prompts"
       }
      }


}
 }
