//Jenkinsfile
pipeline {
  stage 'build-dockerapp'

  stage 'Publish containers'
  shouldPublish = input message: 'Publish Containers?', parameters: [[$class: 'ChoiceParameterDefinition', choices: 'yes\nno', description: '', name: 'Deploy']]
  if(shouldPublish == "yes") {
    echo "Publishing docker containers"
    sh "\$(aws ecr get-login)"

    sh "895059974424.dkr.ecr.us-east-1.amazonaws.com/hello-repository:latest"
    sh "docker push 895059974424.dkr.ecr.us-east-1.amazonaws.com/hello-repository:latest"
   }
}
