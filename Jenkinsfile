pipeline {
    agent any

    tools {
        nodejs 'NodeJS-18'
    }

    stages {
        stage('Clone Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/giga-R/untitled-d.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                dir('welcome.react') {
                    sh 'npm install'
                } // Closes 'dir'
            } // Closes 'steps'
        } // <--- THIS WAS MISSING (Closes 'stage')

        stage('Build React App') {
            steps {
                dir('welcome.react') {
                    sh 'npm run build'
                } // Closes 'dir'
            } // Closes 'steps'
        } // <--- THIS WAS MISSING (Closes 'stage')
    }

    post {
        success {
            echo 'React build successful 🎉'
        }
        failure {
            echo 'Build failed ❌'
        }
    }
}