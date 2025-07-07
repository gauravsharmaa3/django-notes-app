@Library("Shared") _
pipeline{
    agent {label "node1"}
    
    stages {
        stage("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage("Code"){
            steps{
                script{
                    clone("https://github.com/gauravsharmaa3/django-notes-app.git", "dev")
            }
        }
        }
        stage("build"){
            steps{
                script{
                    docker_build("notes-app","latest","gauravsharmaa3")
                }
            }
        }
        stage("push"){
            steps{
                script{
                    docker_push("notes-app","latest","gauravsharmaa3")
                }
                    }
            }
        stage("Test"){
            steps{
                echo "This is testing the code"
            }
        }
        stage("Deploy"){
            steps{
                script{
                    docker_compose()
                }
            }
        }
    }
}
