pipeline {
    agent any

    parameters {
        string(name: 'SPEC', defaultValue: "cypress/e2e/**/**", description: "Enter the script path that you want to execute")
        // choice(name: 'BROWSER', choices: ['chrome', 'edge', 'firefox'], description: "Choose the browser where you want to execute your scripts")
    }

    stages{
        stage('Building') {
            steps {
                echo "Building the application"
            }
        }
        stage('Testing') {
            steps {
                sh """
                    npm i
                    npx cypress run --browser chrome
                """
            }
        }
        stage('Deploying') {
            steps {
                echo "Deploy the application"
            }
        }
    }

    // post {
    //     always {
    //         publishHTML([allowMissing:false, alwaysLinkToLastBuild: false, keepAll: true, reportDir: 'cypress/report', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: ''])
    //     }
    // }
}