node {
    stage('Download code from git scm') {
    git branch: 'test', url: 'https://github.com/clouddevopseng/8pm-project.git'
     }
    stage('Convert code into artifacts') {
    sh 'mvn package'
    }
    stage('Deploy into container') {
    deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: '688da7d5-53af-4485-adb8-76a4c381692d', path: '', url: 'http://13.204.83.28:8080')], contextPath: '/dev-app-scripted', war: '**/*.war'
    }
}
