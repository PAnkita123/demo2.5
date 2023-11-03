pipeline{
    agent any
     environment{
        RELEASE = '20.4'
    }
    stages{
        stage('Build'){
            environment{
                LOG_LEVEL = 'INFO'
            }
            steps{
                echo "This is build release {$RELEASE} of log level {$LOG_LEVEL}"

            }
        }
    }
        stage('Test'){
            steps{
                echo "This is Test release {$RELEASE} of log level {$LOG_LEVEL}"
                writeFile file = 'test-result.txt', text = 'passed'
            }
        }
    post{
        success{
            archiveArtifacts 'testresult.txt'
        }
    }


}
