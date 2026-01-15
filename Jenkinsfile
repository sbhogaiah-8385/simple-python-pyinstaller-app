pipeline {
    agent any
    stages {
        stage('Build') {
            environment {
              PATH = "C:/Users/somas/AppData/Local/Programs/Python/Python313;$PATH"
              PATH = "C:/Users/somas/anaconda3/Scripts;$PATH"
            }
            steps {
                sh 'python -m py_compile sources/add2vals.py sources/calc.py'
                stash(name: 'compiled-results', includes: 'sources/*.py*')
            }
        }

        stage('Test') {
            steps {
                sh 'py.test --junit-xml test-reports/results.xml sources/test_calc.py'
            }
            post {
                always {
                    junit 'test-reports/results.xml'
                }
            }
        }
    }
}
