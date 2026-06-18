pipeline {
    agent any  // Use any available agent

    tools {
        maven 'Maven'
        jdk 'JDK'// Ensure this matches the name configured in Jenkins
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/ymtarun/Ansible.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  // Run Maven build
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'  // Run unit tests
            }
        }

        
        
       
        stage('Run Application') {
            steps {
                // Start the JAR application
                sh 'ansible-playbook ansible/playbook.yml -i ansible/hosts.ini'
            }
        }

