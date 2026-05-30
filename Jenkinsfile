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
                checkout scm
            }
        }

        stage('Test') {
            steps {
                sh '''
                python3 -m py_compile app.py
                '''
            }
        }

        stage('Build Docker Image') {
            steps {
                sh '''
                docker build -t rawanc/flask-app:latest .
                '''
            }
        }

        stage('Push to Docker Hub') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', usernameVariable: 'USER', passwordVariable: 'PASS')]) {
                    sh '''
                    echo $PASS | docker login -u $USER --password-stdin
                    docker push rawanc/flask-app:latest
                    '''
                }
            }
        }
    }
}




// pipeline {
// agent {
// label 'python-agent'
// }
//  triggers {
//         pollSCM '*/5 * * * *'
//     }


// stages {

//     stage('Checkout') {
//         steps {
//             echo 'Downloading source code from GitHub...'
//         }
//     }

//     stage('Verify Flask App') {
//         steps {
//             sh '''
//             ls -la

//             python3 --version || true

//             test -f app.py

//             grep "Flask" app.py
//             '''
//         }
//     }

//     stage('Build') {
//         steps {
//             sh '''
//             echo "Flask application found successfully"
//             '''
//         }
//     }

//     stage('Deliver') {
//         steps {
//             sh '''
//             echo "Pipeline completed successfully"
//             '''
//         }
//     }
// }


// }