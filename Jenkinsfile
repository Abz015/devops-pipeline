pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning the repository...'
                git branch: 'main', url: 'https://github.com/Abz015/devops-pipeline.git'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                echo 'Running Ansible Playbook...'
                sh '''
                ansible-playbook -i localhost, -c local deploy.yml
                '''
            }
        }
    }

    post {
        success {
            echo 'Deployment Successful!'
        }
        failure {
            echo 'Deployment Failed.'
        }
    }
}
