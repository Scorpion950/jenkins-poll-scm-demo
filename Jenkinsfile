```groovy
pipeline {

    agent any

    options {
        timestamps()
        disableConcurrentBuilds()
    }

    stages {

        stage('Robot Activation') {
            steps {
                echo '''
                
        ======================================

              JENKINS ROBOT SYSTEM

                   [########]
                   [ O    O ]
                   [   --   ]
                   [########]

              SYSTEM ACTIVATED!
              READY FOR AUTOMATION!

        ======================================

                '''

                echo "Pipeline Version: 2.0"
                echo "Build Number: ${BUILD_NUMBER}"
            }
        }

        stage('GitHub Checkout') {
            steps {
                echo 'Connecting to GitHub repository...'

                checkout scm

                echo 'GitHub repository downloaded successfully!'
            }
        }

        stage('System Information') {
            steps {
                echo 'Collecting system information...'

                sh '''
                    echo "Operating System:"
                    uname -s

                    echo "Current User:"
                    whoami

                    echo "Current Date:"
                    date

                    echo "Current Directory:"
                    pwd
                '''
            }
        }

        stage('Repository Inspection') {
            steps {
                echo 'Inspecting repository files...'

                sh '''
                    echo "Latest Commit:"
                    git log -1 --oneline

                    echo "Repository Files:"
                    ls -la

                    echo "Tracked File Count:"
                    git ls-files | wc -l
                '''
            }
        }

        stage('Build Simulation') {
            steps {
                echo '''
                
                ROBOT BUILDING APPLICATION...

                [#####...............] 25%
                [##########..........] 50%
                [###############.....] 75%
                [####################] 100%

                '''

                sh '''
                    echo "Checking Git repository..."

                    git rev-parse --is-inside-work-tree

                    echo "Repository check completed!"
                '''

                echo 'Build simulation completed!'
            }
        }

        stage('Mission Completed') {
            steps {
                echo '''

        ======================================

                  MISSION COMPLETED!

                      [ O  O ]
                      [  ^^  ]
                      [______]

                  BUILD SUCCESSFUL!

        ======================================

                '''

                echo "Build Number: ${BUILD_NUMBER}"
                echo "Pipeline Version: 2.0"
                echo "Status: SUCCESS"
            }
        }
    }

    post {
        success {
            echo 'ROBOT STATUS: ALL SYSTEMS OPERATIONAL!'
        }

        failure {
            echo 'ROBOT STATUS: BUILD FAILED!'
        }

        always {
            echo 'Pipeline 2 execution finished.'
        }
    }
}
```
