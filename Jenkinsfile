pipeline {
    agent any

    stages {
        stage('Start Website') {
            steps {
                sh '''
                echo "Kill old server"
                pkill -f "http.server 9000" || true

                echo "Starting persistent server"
                cd $WORKSPACE

                nohup /usr/local/bin/python3 -m http.server 9000 > server.log 2>&1 &
                sleep 2
                '''
            }
        }
    }
}
