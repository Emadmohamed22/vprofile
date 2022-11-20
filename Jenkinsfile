pipeline{
    agent{
        label "node"
        }
    tools {
        maven "maven3"
    }
    stages{
        stage('BUILD'){
            steps{
                sh 'mvn clean install -DskipTests'
            }
            post{
                success{
                    echo 'Now Archiving...'
                }
            }
        }
        stage("UNIT TEST"){
            steps{
                esh 'mvn test'
            }
        }
        stage("INTEGRATION TEST"){
            steps{
                sh 'mvn verify -DskipUnitTests'
            }
        }
    }
}
