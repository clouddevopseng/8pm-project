node {
    stage('Download code from git scm') {
    git branch: 'dev', url: 'https://github.com/clouddevopseng/8pm-project.git'
     }
    stage('Convert code into artifacts') {
    sh 'mvn package'
    }
    stage('Deploy into container') {
    deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'f1c9c42d-414e-45f2-8a4e-141cded58af0', path: '', url: 'http://172.31.8.185:8080')], contextPath: '/dev-app-scripted', war: '**/*.war'
    }
}
