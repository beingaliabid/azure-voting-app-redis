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
        }
    }
}
 