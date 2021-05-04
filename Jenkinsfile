pipeline {
    agent any

    stages {
        stage('preparation') {
            steps {
                git 'https://github.com/AhmedMamdouh996/Booster_CI_CD_Project'
            }
        }
        stage('CI') {
            steps {
                sh 'docker build . -t ahmedmamdouh96/django_cicd:1.0'
            }
        }
        stage('CD') {
            steps {
                sh 'docker run -d -p 8000:8000 ahmedmamdouh96/django_cicd:1.0'
            }
            
            post{
            	success{
            		slackSend (color:"#09c", message: "Done")
            	}
            }
        }
        
    }
}

