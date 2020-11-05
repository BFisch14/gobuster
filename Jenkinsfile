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
                GITHUB_TOKEN = credentials('go-release-sample')
            }
            steps {
                sh 'curl -sL https://git.io/goreleaser  | sh --rm-dist'
            }
        }
    }
}