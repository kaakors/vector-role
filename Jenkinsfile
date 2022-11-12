pipeline {
  agent {
    label 'linux'
  }
  stages{
      stage("Chekout SCM"){
          steps{
            git branch: 'main', credentialsId: '283bea74-7c42-4f08-831f-b6c78fc6df6d', url: 'git@github.com:kaakors/vector-role.git'
          }
      }
      stage("Install molecule"){
          steps{
              sh 'pip3 install molecule molecule_docker'
          }
      }
      stage("Run molecule"){
          steps{
              sh 'molecule converge -s centos'
          }
      }
  }
}
