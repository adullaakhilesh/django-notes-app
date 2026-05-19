@Library('Shared')_
pipeline{
    agent { label 'ram'}
    
    stages{
        stage("Code clone"){
            steps{
                sh "whoami"
            clone("https://github.com/LondheShubham153/django-notes-app.git","main")
            }
        }
        stage("Code Build"){
            steps{
            docker_build("notes-app","latest","akhilesh3369")
            }
        }
        stage("Push to DockerHub"){
            steps{
                docker_push("notes-app","latest","akhilesh3369")
            }
        }
        stage("Deploy"){
            steps{
                sh "docker compose down && docker compose up -d "
            }
        }
        
    }
}
