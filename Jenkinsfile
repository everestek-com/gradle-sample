env.MYTOOL_VERSION = '1.33'
node {
    echo "GitHub BranhName ${env.BRANCH_NAME}"
  echo "Jenkins Job Number ${env.BUILD_NUMBER}"
  echo "Jenkins Node Name ${env.NODE_NAME}"
  
  echo "Jenkins Home ${env.JENKINS_HOME}"
  echo "Jenkins URL ${env.JENKINS_URL}"
  echo "JOB Name ${env.JOB_NAME}"
//properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '5', artifactNumToKeepStr: '5', daysToKeepStr: '5', numToKeepStr: '5')), disableConcurrentBuilds(abortPrevious: true), pipelineTriggers([pollSCM('* * * * *')])])
    def gradlehome=tool name:'gradle6.3'
    stage('checkout'){
        git branch: 'dev', credentialsId: '67837e2a-d168-4f13-b8c5-5a427dd5f584', url: 'https://github.com/everestek-com/gradle-sample.git'
    }
    stage('Compile'){
        sh "${gradlehome}/bin/gradle compileTestJava"
    }
    stage('Build'){
        sh "${gradlehome}/bin/gradle build"
    }
    stage('Tests'){
        sh "${gradlehome}/bin/gradle Test"
    }
    /*stage('SendEmailNotification'){
        mail bcc: '', body: '''Build Over
Regards Vishal Sharma''', cc: 'vishuu202@gmail.com', from: 'vishuu202@gmail.com', replyTo: '', subject: 'Build Complete', to: 'sbmworld786@gmail.com'
    }*/
}
