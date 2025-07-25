pipeline{
    agent any

    
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
                    bat 'npm start &'
                    bat 'wait-on http://localhost:8080'
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