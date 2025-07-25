pipeline{
    stages{

    
        stage('Checkout'){
            seps{
                git branch: 'main', url: 'https://github.com/dessyland-cyber/StudentRegistryAppDemo'
            }
        }

        stage("Install dependancies"){
            steps{
                script{
                    
                        bat 'npm install'
                    }
                }
            }

        }
        stage("Start application and run tests"){
            steps{
                script{
                    bat 'start /b npm start'
                   
                }
            }
        }
        stage("run tests"){
            steps{
                script{
                    bat 'npm test'
                   
                }
            }
        }
    }
    post {
        always{
            echo "CI pipeline completed"
        }
    }
}