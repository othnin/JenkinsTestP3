
pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh ''' 
                    #!/bin/bash
                    echo $PWD
                    PATH=$WORKSPACE/venv/bin:/usr/bin:$PATH
                    if [ ! -d "venv" ]; then
                        virtualenv venv
                    fi
                    . venv/bin/activate
                    pip install -r requirements.txt
                    python test.py
                '''
            }
        }
    }
}

