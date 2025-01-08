pipeline {
    agent any
    stages {
        stage('pull'){
            steps {
                git branch: 'dev', url: 'https://github.com/SJ8688/frontend-project.git'
            }
        }
        stage('build'){
            steps {
                sh '''npm install
                    ng build 
                    cd dist/angular-frontend
                    aws s3 cp /frontend-project/dist/angular-frontend/ s3://cbz-frontend-project-b12/ --recursive '''

            }
        }
    }
}