pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                sh "mvn clean package"
            }
        }
        stage("Deploy"){
            steps{
                echo "deploy coming soon...."
            }
        }
        stage("upload"){
            steps{
                echo "Uploading artifacts........"
            }
        }
    }
}
