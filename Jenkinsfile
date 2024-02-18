pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // Use the correct path to your Node.js installation
                    def nodejsHome = tool 'Node.js'
                    def npmHome = "${nodejsHome}/npm"
                    
                    // Add Node.js and npm to the PATH
                    PATH = "${nodejsHome}/bin:${npmHome}/bin:${env.PATH}"
                    
                    // Install project dependencies
                    sh 'npm install'
                }
            }
        }

        // Add more stages for additional steps as needed
        // For example, stages for linting, testing, and deployment
    }

    post {
        always {
            // Clean up workspace or perform any other cleanup tasks
            echo 'Always running, regardless of success or failure!'
        }
    }
}
