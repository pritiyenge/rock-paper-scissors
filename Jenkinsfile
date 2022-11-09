node {
   stage('download') 
{
    git 'https://github.com/rakya07/mvn.git'
}
stage('build') 
{
    sh 'mvn package'
}
stage('Approval') 
{
            def deploymentDelay = input id: 'Deploy', message: 'Deploy to production?', submitter: 'admin', parameters: [choice(choices: ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9', '10', '11', '12', '13', '14', '15', '16', '17', '18', '19', '20', '21', '22', '23', '24'], description: 'Hours to delay deployment?', name: 'deploymentDelay')]
            sleep time: deploymentDelay.toInteger(), unit: 'HOURS'
            
}
stage('deploy') 
{
   deploy adapters: [tomcat8(credentialsId: 'admin', path: '', url: 'http://172.31.22.68:8080/')], contextPath: 'demo', onFailure: false, war: '**/*.war'
}
}
