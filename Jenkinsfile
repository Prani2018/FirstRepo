pipeline {
    agent {
        label 'JavaBuildServer'
    }
    tools {
        maven 'localMaven'
    }

stages{
        stage('Build'){
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    echo 'Archiving the artifacts'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }

        stage ('Deployments'){
                    steps {
                        echo "Deploying the Artifacts into tomcat Server"
                        deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: '93181eff-8f60-4f07-8126-d28a0dfa6c7f', path: '', url: 'http://23.22.211.197:8080')], contextPath: null, war: '**/*.war'
                    }
            }
        }
}
