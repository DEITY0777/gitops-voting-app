@Library('Shared') _

pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "rohitsunka/result-app"
        IMAGE_TAG = "${env.BUILD_NUMBER}"
    }

    stages {

        stage('Workspace Cleanup') {
            steps {
                cleanWs()
            }
        }

        stage('Checkout Code') {
            steps {
                code_checkout(
                    "git@github.com:DEITY0777/DEITY0777-K8S-Gitops-Deployment-on-AWS-EC2-using-Argo-CD.git",
                    "main"
                )
            }
        }

        stage('Build Result Image') {
            steps {
                docker_build(
                    DOCKER_IMAGE,
                    IMAGE_TAG,
                    "./result"
                )
            }
        }

        stage('Trivy Scan') {
            steps {
                trivy_scan(
                    "${DOCKER_IMAGE}:${IMAGE_TAG}"
                )
            }
        }

        stage('Push to DockerHub') {
            steps {
                docker_push(
                    DOCKER_IMAGE,
                    IMAGE_TAG
                )
            }
        }

        stage('Trigger CD') {
            steps {
                build job: 'VotingApp-CD', parameters: [
                    string(name: 'DOCKER_IMAGE', value: "${DOCKER_IMAGE}"),
                    string(name: 'IMAGE_TAG', value: "${IMAGE_TAG}")
                ]
            }
        }
    }
}
