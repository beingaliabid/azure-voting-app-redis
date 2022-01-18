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
                sh "ssh noetic@192.168.126.199 '(cd /home;pwd;docker ps;cd /home/noetic/apps/gamification;  docker build -t gamify_img .; docker ps)'"
            }
          post {
            success {
               echo "App started successfully :)"
            }
            failure {
               echo "App failed to start :("
            }
         }
        }
     // stage('Start test app') {
       //  steps {
         //   pwsh(script: """
           //    docker-compose up -d
            //   ./scripts/test_container.ps1
           // """)
        // }
         
      //}
     // stage('Run Tests') {
       //  steps {
         //   pwsh(script: """
           //    pytest ./tests/test_sample.py
           // """)
        // }
     // }
     // stage('Stop test app') {
     //    steps {
     //       pwsh(script: """
     //          docker-compose down
     //       """)
        // }
     // }
   }
}
