pipeline {
    agent any

    environment {
        VERCEL_TOKEN = credentials('vercel_token')
    }
    
    stages {
        stage('Install Dependencies'){
            steps {
                echo '[Installing dependencies...]'
                bat 'npm install'
                echo '[Dependencies installed successfully.]'
            }
        }
        stage('Testing Application'){
            steps {
                echo '[Running tests...]'
                echo '[Running unit tests...]'
                echo '[Skipping Tests for now.]'
            }
        }
        stage('Building Application'){
            steps {
                echo '[Building application...]'
                bat 'npm run build'
                echo '[Application built successfully.]'
            }
        }
        stage('Deploy to Vercel'){
            steps {
                echo '[Deploying application to Vercel...]'
                bat 'npm install -g vercel'
                bat 'npx vercel --token %VERCEL_TOKEN% --prod --yes'
                echo '[Application deployed to Vercel successfully.]'
            }
        }
    }
}