pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                echo 'Hello world'
                sh 'go build'
            }
        }
        stage('Test') {
            steps {
                sh 'go test -v'
            }
        }
        stage('Release') {
            environment {
                GITHUB_TOKEN = credentials('github-token')
            }
            steps {
                sh 'curl -sL https://git.io/goreleaser | sh'
            }
        }
    }
}