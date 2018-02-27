pipeline {
  agent any
  stages {
    stage('Stage1') {
      parallel {
        stage('Stage1') {
          steps {
            echo 'coucou'
          }
        }
        stage('Stage2') {
          agent {
            node {
              label 'slave1'
            }
            
          }
          steps {
            archiveArtifacts(fingerprint: true, artifacts: '**/target/*')
            junit '**/target/surefire-reports/TEST-*.xml'
          }
        }
      }
    }
  }
}