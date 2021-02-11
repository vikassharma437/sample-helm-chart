def repo="https://github.com/sahilsethi12/sample-helm.git"
pipeline{
		agent{
				label 'helm'
		}
		stages{
				stage("Setup") {
            steps {
               
                    sh "helm repo add sahil ${repo}"
              
            }
        }
				stage("Deploy to Dev") {
            steps {
                script{
										openshift.withCluster(){
                       
                            sh "helm upgrade --install my-guestbook sahil/guestbook --values dev/values.yaml -n dev --wait"
                        
                    }
                }
            }
        }
				
				
		}

}
