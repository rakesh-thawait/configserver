pipeline {
  // Use Jenkins Maven slave
  // Jenkins will dynamically provision this as OpenShift Pod
  // All the stages and steps of this Pipeline will be executed on this Pod
  // After Pipeline completes the Pod is killed so every run will have clean
  // workspace
  agent any

  // Pipeline Stages start here
  // Requeres at least one stage
  stages {

    stage("Initialize") {
        steps {
            script {
              echo "Branch Specifier"
            }
        }
    }
    // Checkout source code
    // This is required as Pipeline code is originally checkedout to
    // Jenkins Master but this will also pull this same code to this slave
    //stage('Git Checkout') {
    //  steps {
        // Turn off Git's SSL cert check, uncomment if needed
        // sh 'git config --global http.sslVerify false'
        //git url: "https://github.com/rakesh-thawait/configserver.git"
      //}
    //}

    // Run Maven build, skipping tests
    stage('Build'){
      steps {
        sh "mvn clean install"
      }
    }
 }
}