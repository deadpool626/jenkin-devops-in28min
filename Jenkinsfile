// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
// 	stage('Integration Test') {
// 		echo "Integration Test"
// 	}
// }

// pipeline{
// 	agent any

// 	stages{
// 		stage{
// 			step('Build in Declartive stage'){
// 		echo "Build in Declartive"}
// 	}
// 	stage{
// 		step('Test in Declartive stage'){
// 			echo "Test in Declartive"
// 		}
		
// 	}
// 	stage{
// 		step('Integration Test in Declartive stage'){
// 			echo "Integration Test in Declartive"
// 		}
		
// 	}
// 	}
// }

pipeline {
    agent any
    stages {
        stage('Build in Declartive stage') {
            steps {
                echo "Build in Declartive"
            }
        }
        stage('Test in Declartive stage') {
            steps {
                echo "Test in Declartive"
            }
        }
        stage(‘Build’) {
            steps {
                sh 'docker --version'
            }
        }
    }
}