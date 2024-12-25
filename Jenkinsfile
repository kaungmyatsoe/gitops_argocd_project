pipeline{

    agent any 

    environment{

        DOCKERHUB_USERNAME = "kaungmyatsoe"
        APP_NAME = "gitops-argo-app"
        IMAGE_TAG = "${BUILD_NUMBER}"
        IMAGE_NAME = "${DOCKERHUB_USERNAM}" + "/" + "${APP_NAME}"
        REGISTRY_CREDS = 'dockerhub'
    }

    stages{

        stage('Clenup workspace'){

            steps{

                script{

                    cleanWs()
                }
            }
        }
        stage('Checkout SCM'){

            steps{
                script{
                    git credentialsId:  'github',
                    url: 'https://github.com/kaungmyatsoe/gitops_argocd_project.git',
                    branch: 'main'
                }
            }
        }
    }
}
