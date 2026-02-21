pipeline {
    agent any

    stages {

        stage('Clone Repo') {
            steps {
                git 'https://github.com/Vasanth-vasya/git-practice.git'
            }
        }

        stage('Run Website') {
            steps {
                sh '''
                echo "Stopping old server if running..."
                pkill -f "http.server 9000" || true

                echo "Starting website..."
                cd $WORKSPACE
                nohup python3 -m http.server 9000 > server.log 2>&1 &
                '''
            }
        }
    }
}
