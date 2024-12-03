pipeline {
    agent any
    environment {
        JAVA_HOME = '/usr/lib/jvm/java-11-openjdk'
    }
    stages {
        stage('Checkout') {
            steps {
                // Récupérer le code source du dépôt
                checkout scm
            }
        }
        stage('Build Java') {
            steps {
                script {
                    // Compiler le code Java
                    sh 'javac src/HelloWorld.java'
                }
            }
        }
        stage('Build Python') {
            steps {
                script {
                    // Exécuter le script Python
                    sh 'python3 hello_world.py'
                }
            }
        }
        stage('Test Java') {
            steps {
                script {
                    // Ajouter des tests pour Java ici si nécessaire
                    echo 'Pas de tests Java pour le moment.'
                }
            }
        }
        stage('Test Python') {
            steps {
                script {
                    // Ajouter des tests pour Python ici si nécessaire
                    echo 'Pas de tests Python pour le moment.'
                }
            }
        }
    }
    post {
        always {
            // Étapes de nettoyage ou de notification après l'exécution du pipeline
            echo 'Pipeline terminé.'
        }
    }
}
