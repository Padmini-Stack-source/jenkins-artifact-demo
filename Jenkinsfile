
pipeline {
    agent any

    triggers {
        pollSCM('H/2 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Running build.sh'
                sh 'bash build.sh'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'output.txt',
                                 fingerprint: true
            }
        }
    }
}
