pipeline{
    agent any
    stages{
        stage("Build"){
            when {
                branch "main"
            }
            steps{
                sh "mvn clean package"
            }
        }
        stage("Deploy"){
            when {
                branch "develop"
            }
            steps{
                echo "deploy coming soon...."
            }
        }
        stage("upload"){
            when {
                branch "feature"
            }
            steps{
                echo "Uploading artifacts........"
            }
        }
    }
}
