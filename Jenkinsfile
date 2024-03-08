pipeline {
    agent any

    stages {
        stage('Git') {
            steps {
                git branch: 'latest', url: 'https://github.com/jaiswaladi246/10-Tier-MicroService-Appliction.git'
            }
        }
        
        
        stage('adservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-MicroService-Appliction/src/adservice/') {
                                 sh "docker build -t adijaiswal/adservice:latest ."
                                 sh "docker push adijaiswal/adservice:latest"
                        }
                    }
                }
            }
        }
		
		stage('cartservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-MicroService-Appliction/src/cartservice/src/') {
                                 sh "docker build -t adijaiswal/cartservice:latest ."
                                 sh "docker push adijaiswal/cartservice:latest"
                        }
                    }
                }
            }
        }
		
		stage('checkoutservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-MicroService-Appliction/src/checkoutservice/') {
                                 sh "docker build -t adijaiswal/checkoutservice:latest ."
                                 sh "docker push adijaiswal/checkoutservice:latest"
                        }
                    }
                }
            }
        }
		
		stage('currencyservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-MicroService-Appliction/src/currencyservice/') {
                                 sh "docker build -t adijaiswal/currencyservice:latest ."
                                 sh "docker push adijaiswal/currencyservice:latest"
                        }
                    }
                }
            }
        }
        
		stage('emailservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-MicroService-Appliction/src/emailservice/') {
                                 sh "docker build -t adijaiswal/emailservice:latest ."
                                 sh "docker push adijaiswal/emailservice:latest"
                        }
                    }
                }
            }
        }
		
		stage('frontend') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-MicroService-Appliction/src/frontend/') {
                                 sh "docker build -t adijaiswal/frontend:latest ."
                                 sh "docker push adijaiswal/frontend:latest"
                        }
                    }
                }
            }
        }
		
		stage('loadgenerator') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-MicroService-Appliction/src/loadgenerator/') {
                                 sh "docker build -t adijaiswal/loadgenerator:latest ."
                                 sh "docker push adijaiswal/loadgenerator:latest"
                        }
                    }
                }
            }
        }
		
		stage('paymentservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-MicroService-Appliction/src/paymentservice/') {
                                 sh "docker build -t adijaiswal/paymentservice:latest ."
                                 sh "docker push adijaiswal/paymentservice:latest"
                        }
                    }
                }
            }
        }
        
		stage('productcatalogservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-MicroService-Appliction/src/productcatalogservice/') {
                                 sh "docker build -t adijaiswal/productcatalogservice:latest ."
                                 sh "docker push adijaiswal/productcatalogservice:latest"
                        }
                    }
                }
            }
        }
		
		stage('recommendationservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-MicroService-Appliction/src/recommendationservice/') {
                                 sh "docker build -t adijaiswal/recommendationservice:latest ."
                                 sh "docker push adijaiswal/recommendationservice:latest"
                        }
                    }
                }
            }
        }
		
		stage('shippingservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-MicroService-Appliction/src/shippingservice/') {
                                 sh "docker build -t adijaiswal/shippingservice:latest ."
                                 sh "docker push adijaiswal/shippingservice:latest"
                        }
                    }
                }
            }
        }
        

        stage('shippingservice') {
            steps {
                script{                   
                    sh "docker rmi -f \$(docker images -aq)"
                         }
                    }
                }



        stage('K8') {
            steps {
                withKubeConfig(caCertificate: '', clusterName: 'my-eks', contextName: '', credentialsId: '40662307-ca84-4893-ab4b-f6ffadfc3f8c', namespace: 'devops', restrictKubeConfigAccess: false, serverUrl: 'https://7DF03B658F34713AF60204C79AB4DF84.gr7.ap-south-1.eks.amazonaws.com') {
                       sh "kubectl apply -f deployment-service.yml"
					   sh "kubectl get pods -n devops"
					   sh "kubectl get svc -n devops"
}
            }
        }


    }
}
