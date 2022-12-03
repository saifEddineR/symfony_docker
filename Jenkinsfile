pipeline{
    agent any
    stages{
        stage('test'){
            steps{
                echo 'hello test'
            }
        }
        stage('build'){
            steps{
                 script{
                    echo "hello"
                    dockerImage = docker.build("saifromdhane/sf_gomycode")
                    echo "hello1"
                    docker.withRegistry( '', "docker_credentials" ) {
                        echo "hello2"
                        dockerImage.push("$BUILD_NUMBER")
                     }
                 }
            }
        }
        stage('deliver'){
            steps{
                echo 'hello deliver'
            }
        }
    }
}
Footer
