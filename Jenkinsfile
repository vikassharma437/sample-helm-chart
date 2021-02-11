def repo="https://vikassharma437.github.io/sample-helm-chart/"
pipeline{
		agent{
				label 'helm'
		}
		stages{
				stage("Setup") {
            steps {
               
                    sh "helm repo add vikas ${repo}"
              
            }
        }
				stage("Deploy to Dev") {
            steps {
                script{
										openshift.withCluster(){
                       
                            sh "helm upgrade --install my-guestbook vikas/guestbook --values dev/values.yaml -n dev --wait"
                        
                    }
                }
            }
        }
				
				
		}

}
