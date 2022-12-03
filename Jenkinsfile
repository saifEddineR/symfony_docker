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
                    sh 'cd app/'
                    app = docker.build("saifromdhane/sf_gomycode")
                    docker.withRegistry('', 'docker_credentials') {
                        app.push("${BUILD_NUMBER}")
                        app.push("${GIT_COMMIT}")
                        app.push("latest")
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
