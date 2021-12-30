pipeline {
    agent any

    stages {
        stage('git') {
            steps {
                git 'https://github.com/manoharej/easyio.git'
            }
        }
        stage('Make zip') {
            steps {
                
                sh 'npm install'
                sh 'tar czf nanogram-{$BUILD_NUMBER}.tar.gz node_modules main.js package.json public LICENSE'
            }
        }
        stage('archive artifact') {
            steps {
                archiveArtifacts artifacts: 'nanogram-*.tar.gz', followSymlinks: false
            }
        }
        
    }
}
