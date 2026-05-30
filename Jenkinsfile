pipeline {
agent {
label 'python-agent'
}

triggers {
    pollSCM('*/5 * * * *')
}

stages {

    stage('Checkout') {
        steps {
            echo 'Downloading source code from GitHub...'
        }
    }

    stage('Verify Flask App') {
        steps {
            sh '''
            ls -la

            python3 --version || true

            test -f app.py

            grep "Flask" app.py
            '''
        }
    }

    stage('Build') {
        steps {
            sh '''
            echo "Flask application found successfully"
            '''
        }
    }

    stage('Deliver') {
        steps {
            sh '''
            echo "Pipeline completed successfully"
            '''
        }
    }
}


}