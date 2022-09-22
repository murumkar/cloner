pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                sh '/usr/bin/python3 /home/ec2-user/dremio-cloner/src/dremio_cloner.py /home/ec2-user/dremio-cloner/export_config.json'
            }
        }
    }
}
