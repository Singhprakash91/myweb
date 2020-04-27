node{
  stage('SCM Checkout'){
     git 'https://github.com/Singhprakash91/myweb'
    }
  stage('Compile-Package'){
    //Git Maven Home Path
    def mvnHOME = tool name: 'maven3', type: 'maven'
     sh "${mvnHOME}/bin/mvn package"
  }
  stage('Slack Notification'){
   slackSend baseUrl: 'https://hooks.slack.com/services/',
     channel: '#pipelinejob',
     color: 'good',
     message: 'War Build Sucess Notifications by Slack',
     tokenCredentialId: 'Slack-demo',
     username: 'DevOps2020'
  }
}
