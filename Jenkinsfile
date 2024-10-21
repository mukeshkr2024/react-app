pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Clone the repository
                git 'https://github.com/mukeshkr2024/react-app.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                script {
                    // Set up Node.js environment
                    env.PATH = "${tool 'NodeJS'}:${env.PATH}"
                }
                // Install dependencies using npm or yarn
                sh 'npm install' // or 'yarn install' if you're using Yarn
            }
        }
        stage('Build') {
            steps {
                // Build the Vite app
                sh 'npm run build' // Ensure you have "build": "vite build" in your package.json scripts
            }
        }
        stage('Deploy') {
            steps {
                // Deploy the app (e.g., to a web server or Docker)
                // Example: copying to a remote server using SSH
                sh 'scp -r dist/* user@your-server-ip:/path/to/your/deployment/directory/'
            }
        }
    }
}
