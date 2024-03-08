pipeline {
    agent any

    stages {
        stage('Git') {
            steps {
                git branch: 'latest', url: 'https://github.com/bdcloudcomputing/project4-10-tier-app-on-EKS.git'
            }
        }
        
        
        stage('adservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/project4-10-tier-app-on-EKS/src/adservice/') {
                                 sh "docker build -t bpsod10/adservice:latest ."
                                 sh "docker push bpsod10/adservice:latest"
                        }
                    }
                }
            }
        }
		
		stage('cartservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/project4-10-tier-app-on-EKS/src/cartservice/src/') {
                                 sh "docker build -t bpsod10/cartservice:latest ."
                                 sh "docker push bpsod10/cartservice:latest"
                        }
                    }
                }
            }
        }
		
		stage('checkoutservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/project4-10-tier-app-on-EKS/src/checkoutservice/') {
                                 sh "docker build -t bpsod10/checkoutservice:latest ."
                                 sh "docker push bpsod10/checkoutservice:latest"
                        }
                    }
                }
            }
        }
		
		stage('currencyservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/project4-10-tier-app-on-EKS/src/currencyservice/') {
                                 sh "docker build -t bpsod10/currencyservice:latest ."
                                 sh "docker push bpsod10/currencyservice:latest"
                        }
                    }
                }
            }
        }
        
		stage('emailservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/project4-10-tier-app-on-EKS/src/emailservice/') {
                                 sh "docker build -t bpsod10/emailservice:latest ."
                                 sh "docker push bpsod10/emailservice:latest"
                        }
                    }
                }
            }
        }
		
		stage('frontend') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/project4-10-tier-app-on-EKS/src/frontend/') {
                                 sh "docker build -t bpsod10/frontend:latest ."
                                 sh "docker push bpsod10/frontend:latest"
                        }
                    }
                }
            }
        }
		
		stage('loadgenerator') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/project4-10-tier-app-on-EKS/src/loadgenerator/') {
                                 sh "docker build -t bpsod10/loadgenerator:latest ."
                                 sh "docker push bpsod10/loadgenerator:latest"
                        }
                    }
                }
            }
        }
		
		stage('paymentservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/project4-10-tier-app-on-EKS/src/paymentservice/') {
                                 sh "docker build -t bpsod10/paymentservice:latest ."
                                 sh "docker push bpsod10/paymentservice:latest"
                        }
                    }
                }
            }
        }
        
		stage('productcatalogservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/project4-10-tier-app-on-EKS/src/productcatalogservice/') {
                                 sh "docker build -t bpsod10/productcatalogservice:latest ."
                                 sh "docker push bpsod10/productcatalogservice:latest"
                        }
                    }
                }
            }
        }
		
		stage('recommendationservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/project4-10-tier-app-on-EKS/src/recommendationservice/') {
                                 sh "docker build -t bpsod10/recommendationservice:latest ."
                                 sh "docker push bpsod10/recommendationservice:latest"
                        }
                    }
                }
            }
        }
		
		stage('shippingservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/project4-10-tier-app-on-EKS/src/shippingservice/') {
                                 sh "docker build -t bpsod10/shippingservice:latest ."
                                 sh "docker push bpsod10/shippingservice:latest"
                        }
                    }
                }
            }
        }
        

//         stage('shippingservice') {
//             steps {
//                 script{                   
//                     sh "docker rmi -f \$(docker images -aq)"
//                          }
//                     }
//                 }



//         stage('K8') {
//             steps {
//                 withKubeConfig(caCertificate: '', clusterName: 'my-eks', contextName: '', credentialsId: '40662307-ca84-4893-ab4b-f6ffadfc3f8c', namespace: 'devops', restrictKubeConfigAccess: false, serverUrl: 'https://7DF03B658F34713AF60204C79AB4DF84.gr7.ap-south-1.eks.amazonaws.com') {
//                        sh "kubectl apply -f deployment-service.yml"
// 					   sh "kubectl get pods -n devops"
// 					   sh "kubectl get svc -n devops"
// }
//             }
//         }


    }
}
