node {

stage('deploy') 
{
   deploy adapters: [tomcat8(credentialsId: 'admin', path: '', url: 'http://172.31.22.68:8080/')], contextPath: 'demo3', onFailure: false, war: '**/*.war'
}
}
