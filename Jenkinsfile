pipeline{
    agent any
    stages{
        stage("Checkout"){
            steps{
                git branch: "main",
                    url: "https://github.com/kunwarabhi7/todo-react.git"
                
            }
        }
        stage("Install dependencies"){
            steps{
                sh "npm install"
            }
        }
        stage("Build App"){
            steps{
                sh "npm run build"
            }
        }
        stage("docker build"){
            steps{
                sh "docker build -t react-app ."

            }
        }
        stage("docker run"){
            steps{
                sh "docker run -d -p 3000:3000 --name react-todo react-app"
            }
        }
        
    }
}


