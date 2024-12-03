pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Clone le dépôt GitHub
                git branch: 'main', url: 'https://github.com/medlaifa/EVALUATION-ProjetJenkins.git'
            }
        }
        stage('Build and Execute') {
            steps {
                script {
                    if (isUnix()) {
                        // Définition des variables d'environnement pour Unix
                        withEnv([
                            "JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64",  
                            "PATH=${env.PATH}:/usr/lib/jvm/java-11-openjdk-amd64/bin"
                        ]) {
                            echo "Running on Unix"

                            // Compilation et exécution du programme Java
                            sh 'javac HelloWorld.java'
                            sh 'java HelloWorld'

                            // Exécution du script Python
                            sh 'python3 hello_world.py'
                        }
                    } else {
                        // Gestion des systèmes Windows (facultatif)
                        echo "Running on Windows"
                        bat 'javac HelloWorld.java'
                        bat 'java HelloWorld'
                        bat 'python hello_world.py'
                    }
                }
            }
        }
    }
}
