pipeline code for win:

pipeline {
    agent {
        label 'windows'
    }
    stages {
        stage('Git-checkout') {
            steps {
                echo 'Checking out git repo'
                git branch: 'main', url: 'https://github.com/evsagar0005/jenkin_pipelinetest'

            }
        }
        stage('Stage 1') {
            steps {
                bat '''whoami'''
                bat 'winstage1.bat'
            }
        }
        stage('Stage 2') {
            steps {
               bat 'winstage2.bat'
            }
        }
        stage('Stage 3') {
            steps {
                bat 'winstage3.bat'
            }
        }
        stage('Stage 4') {
            steps {
                bat 'winstage4.bat'
            }
        }
    }
}







pipeline code for lin:

pipeline {
    agent {
        label 'linux'
    }
    stages {
        stage('Git-checkout') {
            steps {
                echo 'Checking out git repo'
                git branch: 'main', url: 'https://github.com/evsagar0005/jenkin_pipelinetest'
            }
        }
        stage('Stage 1') {
            steps {
                sh 'whoami'
                sh 'chmod +x linstage1.sh'
                sh './linstage1.sh'
            }
        }
        stage('Stage 2') {
            steps {
                sh 'chmod +x linstage2.sh'
                sh './linstage2.sh'
            }
        }
        stage('Stage 3') {
            steps {
                sh 'chmod +x linstage3.sh'
                sh './linstage3.sh'
            }
        }
        stage('Stage 4') {
            steps {
                sh 'chmod +x linstage4.sh'
                sh './linstage4.sh'
            }
        }
    }
}
