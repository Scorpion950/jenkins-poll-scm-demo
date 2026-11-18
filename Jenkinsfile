pipeline {

    agent any

    options {
        timestamps()
        disableConcurrentBuilds()
    }

    stages {

        stage('Welcome') {
            steps {

                echo '''

        =====================================

                 JENKINS AUTOMATION

                    .-""""-.
                   /        \
                  |  O    O  |
                  |    __    |
                  |  \____/  |
                   \        /
                    '-.__.-'

               HELLO! I AM JENKINS BOT!

        =====================================

                '''

                echo "Build Number: ${BUILD_NUMBER}"
                echo "Build ID: ${BUILD_ID}"
                echo "Welcome to Jenkins Poll SCM!"

            }
        }

        stage('GitHub Checkout') {
            steps {

                echo 'Checking out GitHub repository...'

                checkout scm

                echo 'GitHub checkout successful!'

            }
        }

        stage('Repository Information') {
            steps {

                echo 'Collecting repository information...'

                sh '''
                    echo "Current Directory:"
                    pwd

                    echo "Current Branch:"
                    git branch --show-current

                    echo "Latest Commit:"
                    git log -1 --oneline

                    echo "Repository Files:"
                    ls -la
                '''

            }
        }

        stage('Build Process') {
            steps {

                echo '''

                BUILD STARTED...

                [#####...............] 25%
                [##########..........] 50%
                [###############.....] 75%
                [####################] 100%

                '''

                sh '''
                    echo "Checking repository..."

                    test -d .git

                    echo "Repository validation successful!"
                '''

            }
        }

        stage('Final Celebration') {
            steps {

                echo '''

              __________________________

                  BUILD SUCCESSFUL!

                     \\(^_^)/

              __________________________

                '''

                echo "Build Number: ${BUILD_NUMBER}"
                echo "Status: SUCCESS"

            }
        }

    }

    post {

        success {
            echo 'SUCCESS! Everything executed perfectly!'
        }

        failure {
            echo 'FAILED! Check Console Output.'
        }

        always {
            echo 'Jenkins Pipeline Execution Finished.'
        }

    }

}
