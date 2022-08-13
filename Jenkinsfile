node
{
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
}
