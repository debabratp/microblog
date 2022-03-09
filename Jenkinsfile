//Jenkinsfile
/*node {
  stage 'build-dockerapp'

  stage 'Publish containers'
  shouldPublish = input message: 'Publish Containers?', parameters: [[$class: 'ChoiceParameterDefinition', choices: 'yes\nno', description: '', name: 'Deploy']]
  if(shouldPublish == "yes") {
    echo "Publishing docker containers"
    sh "\$(aws ecr get-login)"

    sh "895059974424.dkr.ecr.us-east-1.amazonaws.com/hello-repository:latest"
    sh "docker push 895059974424.dkr.ecr.us-east-1.amazonaws.com/hello-repository:latest"
  }
}*/

pipeline {
  environment {
    imagename = "microblog"
    registryCredential = 'debabratp'
    dockerImage = ''
  }
  //agent any
  agent node1
  stages {
    stage('Cloning Git') {
      steps {
        git([url: 'https://github.com/debabratp/microblog.git', branch: 'main', credentialsId: 'debabratp'])
 
      }
    }
    stage('Building image') {
      steps{
        script {
          dockerImage = docker.build imagename
        }
      }
    }
    // stage('Deploy Image') {
    //   steps{
    //     script {
    //       docker.withRegistry( '', registryCredential ) {
    //         dockerImage.push("$BUILD_NUMBER")
    //          dockerImage.push('latest')
    //       }
    //     }
    //   }
    // }
    // stage('Remove Unused docker image') {
    //   steps{
    //     sh "docker rmi $imagename:$BUILD_NUMBER"
    //      sh "docker rmi $imagename:latest"
 
    //   }
    // }
  }
}
