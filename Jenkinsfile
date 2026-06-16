pipeline {
    agent any

    stages {
        stage('Cloning GitHub Project') {
            steps {
                git 'https://github.com/jaganath-reddy/lion.git'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                sudo rm -rf /var/www/html/*
                sudo cp -r ./* /var/www/html/
                sudo systemctl reload nginx
                '''
            }
        }
    }

    post {
        success {
            mail bcc: '',
            body: 'sucess',
            cc: '',
            from: '',
            replyTo: '',
            subject: 'build successfull',
            to: 'jaganathreddy2003@gmail.com'
        }

        failure {
            mail bcc: '',
            body: 'failure',
            cc: '',
            from: '',
            replyTo: '',
            subject: 'build failure',
            to: 'jaganathreddy2003@gmail.com'
        }
    }
}
