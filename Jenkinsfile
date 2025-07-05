pipeline {
    agent any 
    stages {
        stage('Build') { 
           agent {
                docker {
                    image 'python:3.13-alpine3.22'
                }
            }
            steps {
                sh 'python3 -m py_compile sources/add2vals.py sources/calc.py' 
                stash(name: 'compiled-results', includes: 'sources/*.py*') 
            }
        }
    }
}


