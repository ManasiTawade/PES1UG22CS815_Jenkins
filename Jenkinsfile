pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                
                    build 'PES1UG21CS191-1'
                    sh "g++ -o output hello.cpp"
                    echo 'pipeline build successful'
                
            }
            post {
                failure {
                    echo 'pipeline build failed'
                }
            }
        }       
        stage('Test') {
            steps {
                // Print output of the .cpp file
                
                    sh "./output"
                    echo 'pipeline test successful'
                
            }
            post {
                failure {
                    echo 'pipeline test failed'
                }
            }
        } 
        stage('Deploy') {
            steps {
                echo 'pipeline deployment successful'
            }
            post {
                failure {
                    echo 'pipeline deployment failed'
                }
            }
        }
    }
    post{
        failure{
            error 'Pipeline failed'
        }
    }
}
