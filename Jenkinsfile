pipeline {
    agent any

    environment {
        WEB_SERVER_IP = "34.201.24.13"          // Replace with your Web Server EC2 IP
        REMOTE_USER = "ec2-user"              // or 'ubuntu' based on AMI
        SSH_KEY_ID = "Resume"
    }

    triggers {
        githubPush()
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Vinayak-99010/Resume.git'
            }
        }

        stage('Deploy to Web Server') {
            steps {
                sshagent (credentials: ["${SSH_KEY_ID}"]) {
                    sh """
                        scp -o StrictHostKeyChecking=no -r * ${REMOTE_USER}@${WEB_SERVER_IP}:/var/www/html/
                    """
                }
            }
        }
    }
}
