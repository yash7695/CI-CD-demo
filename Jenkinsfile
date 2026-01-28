pipeline {
    agent any

   stage('Clone Repo') {
    steps {
        git branch: 'main', url: 'https://github.com/yash7695/CI-CD-demo.git'
    }
}

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t python-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '''
                docker stop python-app || true
                docker rm python-app || true
                docker run -d -p 5000:5000 --name python-app python-app
                '''
            }
        }
    }
}

