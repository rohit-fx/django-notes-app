@Library("Shared") _

pipeline{
    agent {label "vinod"}
    stages{
        
         stage("Hello"){
            steps{
              script{
                  hello()
              }
            }
            
            
        }
        
        stage("Code"){
            steps{
                
                script {
                    clone("https://github.com/rohit-fx/django-notes-app.git","main")
                }
              
            }
            
            
        }
        
        stage("Build"){
             steps{
                 
                 script{
               docker_build("notes-app","latest","rohit0101rm")
                 }
            }
            
        }
        stage("Test"){
             steps{
                      echo "this is testing step"
            
            }
            
            
        }
        
        
            stage("Push to dockerhub"){
             steps{
                    script {
                        docker_push("notes-app","latest","rohit0101rm")
                    }
            
            }
            
            
        }
        
        stage("Deploy"){
             steps{
                      echo "this is deploying step"
                      sh "docker compose up -d"
            
            }
            
        }
        
    }
}
