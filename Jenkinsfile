pipeline {
    agent any
    stages {
        stage('Build') {
            environment {
              PATH = "C:\Users\somas\AppData\Local\Programs\Python\Python313;$PATH"
            }
            steps {
                sh 'python -m py_compile sources/add2vals.py sources/calc.py'
                stash(name: 'compiled-results', includes: 'sources/*.py*')
            }
        }
    }
}
