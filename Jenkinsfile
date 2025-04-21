
node {
    try {
        stage('Checkout') {
            git branch: 'main', url: 'https://github.com/shruti19-eng/jenkinsjavacoderepo.git'

        }

        stage('Build') {
            dir('Javarepo1') { // Change 'my-app' if needed
                echo 'Building the project...'
                bat 'mvn clean package'
            }
        }

        stage('Archive Artifacts') {
            archiveArtifacts artifacts: '**/target/*.war', onlyIfSuccessful: true
        }

        echo 'Build succeeded!'
        
    } catch (Exception e) {
        echo "Build failed due to: ${e}"
        currentBuild.result = 'FAILURE'
    } finally {
        echo 'Pipeline execution completed!'
    }
}
