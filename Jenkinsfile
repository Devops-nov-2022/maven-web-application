node
{
    def notifyBuild(String buildStatus = 'STARTED') {
  // build status of null means successful
  buildStatus =  buildStatus ?: 'SUCCESSFUL'

  // Default values
  def colorName = 'RED'
  def colorCode = '#FF0000'
  def subject = "${buildStatus}: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'"
  def summary = "${subject} (${env.BUILD_URL})"

  // Override default values based on build status
  if (buildStatus == 'STARTED') {
    color = 'YELLOW'
    colorCode = '#FFFF00'
  } else if (buildStatus == 'SUCCESS') {
    color = 'GREEN'
    colorCode = '#00FF00'
  } else {
    color = 'RED'
    colorCode = '#FF0000'
  }

  // Send notifications
  slackSend (color: colorCode, message: summary)
}

    
    def mavenHome = tool name: "maven3.8.4"
    stage('checkoutcode')
    {
     git branch: 'development', credentialsId: '81d5ecb0-8160-415d-85d4-53cb89bf24a2', url: 'https://github.com/Devops-nov-2022/maven-web-application.git'   
}
  /*
stage('branch')
{
sh "${mavenHome}/bin/mvn clean package"
}
stage('executesonarqube')
{
sh "${mavenHome}/bin/mvn clean sonar:sonar"
}
stage('upload Artifactinto Nexus')
{
sh "${mavenHome}/bin/mvn deploy"
}
stage('DeployTomcatApp'){
sshagent(['33db5e4f-e0e4-406f-ab96-155bef878924']) {
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@13.232.225.51:/opt/apache-tomcat-9.0.64/webapps"
}
}
stage('sendemailNotification')
{
  emailext body: '''build over..,

Thanks,
Rekha S''', subject: 'build over..', to: 'rekhareddy0807@gmail.com'  
}
*/
 notifyBuild(currentBuild.result)   
   
}
