pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/medlaifa/EVALUATION-ProjetJenkins.git'
            }
        }
        stage('Build') {
            steps {
                script {
                    if (isUnix()) {
                        withEnv([
                            "JAVA_HOME=/usr/bin",
                            "PATH=${env.PATH}:/usr/bin"
                        ]) {
                            sh 'echo "Running on Unix"'
                            sh 'javac HelloWorld.java'
                            sh 'java HelloWorld'
                            sh 'python3 hello.py'
                        }
                    } else {
                        withEnv([
                            "JAVA_HOME=C:\\Program Files\\Java\\jdk1.8.0_202",
                            "PYTHON_HOME=C:\\Users\\admin\\AppData\\Local\\Microsoft\\WindowsApps",
                            "PATH=%JAVA_HOME%\\bin;%PYTHON_HOME%;%PATH%"
                        ]) {
                            bat 'echo "Running on Windows"'
                            bat 'javac HelloWorld.java'
                            bat 'java HelloWorld'
                            bat 'python hello.py'
                        }
                    }
                }
            }
        }
    }
}