pipeline {
    agent any

    stages {
        stage('Start Website') {
            steps {
                sh '''
                echo "Stopping old server"
                pkill -f "http.server 9000" || true

                echo "Starting server"
                cd $WORKSPACE
               /usr/local/bin/python3 -m http.server 9000 &
                '''
            }
        }
    }
}
