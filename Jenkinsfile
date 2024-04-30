pipeline {
  agent any

  // Define tools used in the pipeline
  tools {
    // Define Maven tool named 'Maven'
    maven 'Maven'
  }

  // Define stages for your build
  stages {
    // Checkout stage 0 (xtext dependencies)
    stage('Checkout Stage 0') {
      steps {
        // Use Git SCM plugin to checkout the first repository
        git branch: 'master',
             url: 'https://github.com/bankolejohn/xtext-docs-gen.git'

        // Build and install the project using Maven
        sh "${tool 'Maven'}/bin/mvn clean install -Djava.version=17"
      }
    }
    // Checkout stage 1 (main project)
    stage('Checkout Stage 1') {
      steps {
        // Use Git SCM plugin to checkout the first repository
        git branch: 'main',
             url: 'https://github.com/bankolejohn/query-new.git'

        // Build and install the project using Maven
        sh "${tool 'Maven'}/bin/mvn clean install -Djava.version=17"
      }
    }

    // Checkout stage 2 (dependent project)
    stage('Checkout Stage 2') {
      steps {
        // Use Git SCM plugin to checkout the second repository
        git branch: 'main',
             credentialsId: 'your_github_credentials_id', // Replace with actual ID
             url: 'https://github.com/bankolejohn/uddl-new.git'

        // Build and install the project using Maven 
        sh "${tool 'Maven'}/bin/mvn clean install -Djava.version=17"
      }
    }

    // Checkout stage 3 (dependent project - FACE) - Improved naming
    stage('Checkout Stage 3 - FACE Project') { // Clearer stage name
      steps {
        git branch: 'main',
             url: 'https://github.com/bankolejohn/face-new'

        // Build and install the project using Maven (assuming FACE uses Maven)
        sh "${tool 'Maven'}/bin/mvn clean install -Djava.version=17" // Verify if FACE uses Maven
      }
    }
  }
}

        
