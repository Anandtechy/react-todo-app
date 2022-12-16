pipeline {
    agent any
    
    stages {
        stage ('SCM') {
            steps {
                git branch: 'main', url: 'https://github.com/Anandtechy/react-todo-app.git'
            }
        }
     stage ('npm install') {
            steps {
                sh 'npm install'
            }
        }
        stage ('build') {
            steps {
                sh 'npm run build'
    }
     }
    stage('deploy to apache2') {
            steps {
                sh 'sudo cp -rv build/* /var/www/html/'
       }
    }
     stage ('Archive Artifacts') {
        steps {
            sh 'sudo zip archive.zip build/*'
        }
    }
    }
}
