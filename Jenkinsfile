pipeline {
  agent any
  stages{
    stage('build'){
      steps{ 
        sh 'npm install'
      }
    }
    stage('Test'){
      steps{
        sh './jenkins/scripts/test.sh'
      }
    }
    stage('build the react app'){
      steps{
        sh 'npm run build'
      }
    }
    stage('remove the existing build'){
      steps{
        sh 'sudo rm -rf /usr/share/nginx/react-app/build'
      }
    }
    stage ('copy the latest build'){
      steps {
        sh 'sudo cp -r /var/lib/jenkins/workspace/sample_react/build /usr/share/nginx/react-app/'
      }
    }
  }
}
