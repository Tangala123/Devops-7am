pipeline{
    agent any
    stages{
        stage("Build"){
            when {
                branch "feature"
            }
            steps{
                sh "mvn clean package"
            }
        }
        stage("Deploy"){
            when {
                branch "main"
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
