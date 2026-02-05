pipeline {
    agent any
    
    tools {
        maven 'Maven-3.9'
    }
    
    stages {
        stage('Cloner le Repository') {
            steps {
                echo 'Clonage du code source...'
                git branch: 'main', 
                    url: 'https://github.com/Basma04-cloud/devops-tp-2026.git'
            }
        }
        
        stage('Compiler le Projet') {
            steps {
                echo 'Compilation avec Maven...'
                bat 'mvn clean compile'
            }
        }
        
        stage('Tests Unitaires') {
            steps {
                echo 'Exécution des tests...'
                bat 'mvn test'
            }
        }
        
        stage('Package') {
            steps {
                echo 'Création du JAR/WAR...'
                bat 'mvn package -DskipTests'
            }
        }
    }
    
    post {
        success {
            echo 'Build réussi !'
        }
        failure {
            echo 'Build échoué !'
        }
    }
}
