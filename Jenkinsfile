pipeline {
    agent any
    stages {
        stage('git-code-download') {
            steps {
                echo "Downloading code from git"
                git branch: 'main', url: 'https://github.com/devopstechlab/jenkins2-maven.git'
            }
        } 
        stage('Build') {
            steps {
            	sh '''
            	docker build -t devopstechlab/myweb:${BUILD_NUMBER} .
				docker tag devopstechlab/myweb:${BUILD_NUMBER} devopstechlab/myweb:latest
				docker push devopstechlab/myweb:${BUILD_NUMBER}
				docker push devopstechlab/myweb:latest
				'''
            }
        } 
    }
}
