pipeline {
    agent none 
    stages {
        stage("build") {
            agent {
                docker {
                    image: 'python:2-alpine'
                }
            }
            steps {
                echo "Starting to complie python source code..."
                sh 'python -m py_compile sources/add2vals.py sources/calc.py'
                stash(name: 'compiled-results', includes: 'sources/*.py*')
            }

        }
    }
}
