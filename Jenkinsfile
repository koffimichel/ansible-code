pipeline{
    agent any

    stages{
        stage('zip the file'){
            steps{
                sh 'zip ansible-${BUILD_ID}.zip * --exclude Jenkinsfile'
            }
        }
        stage('upload artifacts to jfrog'){
            steps{
                sh 'curl -uadmin:APHKcPC3a5vmZR9FV9hqX6v1qo -T ansible-${BUILD_ID}.zip \
                "http://54.237.227.168:8081/artifactory/ansible/ansible-${BUILD_ID}.zip"'
            }
        }
    }
}