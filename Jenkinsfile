@Library('mylibrary')_
pipeline
{
    agent any
    stages
    {
        stage('ContinuousDownload_Master')
        {
            steps
            {
                script
                {
                    cicd.newGit("https://github.com/krishnain/mymavenn.git")
                }
            }
        }
        stage('ContinuousBuild_Master')
        {
            steps
            {
                script
                {
                    cicd.newMaven()
                }
            }
        }
        stage('ContinuousDeployment_Master')
        {
            steps
            {
                script
                {
                    cicd.newDeploy("SharedLibrarywithDeclarativePipeline","172.31.2.90","testapp")
                }
            }
        }
        stage('ContinuousTesting_Master')
        {
            steps
            {
                script
                {
                    cicd.newGit("https://github.com/intelliqittrainings/FunctionalTesting.git")
                    cicd.runSelenium("SharedLibrarywithDeclarativePipeline")
                }
            }
        }
        stage('ContinuousDelivery_Master')
        {
            steps
            {
                script
                {
                    cicd.newDeploy("SharedLibrarywithDeclarativePipeline","172.31.0.146","prodapp")
                }
            }
        }
        
        
        
    }
}
