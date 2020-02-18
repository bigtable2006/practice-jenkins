pipeline {
    agent { docker { image 'node:8.0' } }
    parameters {
        string(
                name: 'RELEASE_COMMIT',
                defaultValue: 'none',
                description: 'Example: c155280')
        string(
                name: 'RELEASE_FEATURE_BRANCH',
                defaultValue: 'none',
                description: 'Example: feature/1001')
        string(
                name: 'RELEASE_TAG',
                defaultValue: 'none',
                description: 'Example: v0.0.1')
        string(
                name: 'RELEASE_ENVS',
                defaultValue: 'none',
                description: 'Example: ALL')
    }
    stages {
        stage('build') {
            steps {
                sh 'echo "###################################################"'
                sh 'echo ${params.RELEASE_COMMIT}'
                sh 'echo ${params.RELEASE_FEATURE_BRANCH}'
                sh 'echo ${params.RELEASE_TAG}'
                sh 'echo ${params.RELEASE_ENVS}'
                sh 'echo "###################################################"'
            }
        }
        stage('test') {
            steps {
                sh 'npm --version'
            }
        }
        stage('deploy') {
            steps {
                sh 'npm --version'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
