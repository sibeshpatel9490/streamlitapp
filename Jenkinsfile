pipeline {
    agent any
    stages {
        stage("checkout Code") {
            steps {
                git url:'https://github.com/sibeshpatel9490/streamlitapp.git', branch:'main'
            }
        }
        stage("Cleanup Stage") {
            steps {
                bat 'docker rm -f myapp'
            }
        }
        stage("Build Docker image") {
            steps {
                bat 'docker build -t myimage .'
            }
        }
        stage("Create Container") {
            steps {
                bat 'docker run --name=myapp -d -p 8501:8501 myimage'
            }
        }
    }
}