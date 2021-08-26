
pipeline {
    agent { docker { image 'python:3.5.1' } }
    stages {
        stage('build') {
            steps {
                sh ''' #!/bin/bash
                    echo $PWD
                    PATH=$WORKSPACE/venv/bin:/usr/local/bin:$PATH
                    if [ ! -d "venv" ]; then
                        virtualenv venv
                    fi
                    . venv/bin/activate
                    pip install -r requirements.txt --download-cache=/tmp/$JOB_NAME
                    python test.py
                '''
            }
        }
    }
}

