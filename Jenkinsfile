pipeline {
   agent any

   stages {
      stage('Verify Branch') {
         steps {
            echo "$GIT_BRANCH"
         }
      }
  stage('Docker Build') {
         steps {
            sh(script: """
               cd simple_api/
               docker build -t ihssane1/studentlistimage .
               cd ..
            """)
         }
      }
   stage('Push Docker Image') {
     steps{
        sh "docker login -u ihssane1 -p INPT1967!"
          }
        sh 'docker push ihssane1/studentlistimage'
   }   

   }
}