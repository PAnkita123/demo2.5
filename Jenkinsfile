pipeline{
    agent any
     environment{
        RELEASE = '20.4'
    }
    stages{
        stage('build'){
            environment{
                LOG_LEVEL = 'INFO'
            }
            steps{
                echo "This is build release {$RELEASE} of log level {$LOG_LEVEL}"

            }
        }
        stage('Test'){
            steps{
                echo "This is Test release {$RELEASE}"
                writeFile file:'test-result.txt', text:'passed'
            }
        }
    }
        
    post{
        success{
            archiveArtifacts 'test-result.txt'
        }
    }


}
