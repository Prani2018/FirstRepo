pipeline {
    stages{
        stage ('Deployments'){
                    steps {
                        echo "Deploying the Artifacts into tomcat Server"
                        deploy adapters: [tomcat9(alternativeDeploymentContext: '', path: '', url: 'http://13.236.185.112:8080')], contextPath: null, war: '**/*.war'                    }
            }
        }
}
