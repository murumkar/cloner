properties([pipelineTriggers([githubPush()])])
 
pipeline {
    /* specify nodes for executing */
    agent any
 
    stages {
        /* checkout repo */
        stage('Checkout SCM') {
            steps {
                checkout([
                 $class: 'GitSCM',
                 branches: [[name: 'main']],
                 userRemoteConfigs: [[
                    url: 'https://github.com/murumkar/cloner.git',
                    credentialsId: '57f9d213-35c7-4545-803d-e8c9d3fc2347',
                 ]]
                ])
            }
        }
         stage('Deploy') {
            steps {
                sh 'ls'
                #sh '/usr/bin/python3 /home/ec2-user/dremio-cloner/src/dremio_cloner.py /home/ec2-user/dremio-cloner/put_config.json'
            }
        }
    }
 
    /* Cleanup workspace */
    post {
       always {
           deleteDir()
       }
   }
}
