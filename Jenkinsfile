pipeline {
    agent any
    
    tools {
        // Ensure this matches the Maven name configured in Global Tool Configuration
        maven 'scope-maven' 
    }
    
    stages {
        stage('Checkout_loans') {
            steps {
                // Jenkins Multibranch automatically checkouts the correct branch
                echo "Building branch: ${BRANCH_NAME}"
            }
        }
        
        stage('Compile_loans') {
            steps {
                // Compiles the source code
                sh 'mvn compile'
            }
        }
        
        stage('Package_loans') {
            steps {
                // Packages the compiled code into its distributable format
                sh 'mvn clean package'
            }
        }
    }
    
    post {
        success {
            echo 'Build completed successfully!'
        }
        failure i{
            echo 'Build failed. Check the console logs.'
        }
    }
}

