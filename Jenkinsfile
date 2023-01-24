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

pipeline {
    agent any
    environment{
        dockerHome = tool 'firstDocker'
        mavenHome = tool 'firstMaven'
        PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
    }
    stages {
        stage('Build in Declartive stage') {
            steps {
                echo "Build in Declartive"
            }
        }
        stage('Test in Declartive stage') {
            steps {
				echo "PATH - $PATH"
                echo "Test in Declartive"
                sh 'docker version'
                sh 'mvn --version'
            }
        }
        stage('Test1 - mvn test'){
            steps{
                sh 'mvn test'
            }
        }

        stage('Test2 - Integration Test'){
            steps{
                sh 'mvn failsafe:integration-test failsafe:verify'
            }
        }

        stage('Build') {
            steps {
                sh 'docker --version'
            }
        }

        stage('Build Docker Image'){
            steps{
                //"docker build -t in28min/currency-exchange-devops:$env.BUILD_TAG"
                script{
                    dockerImage = docker.build("aditya626/currency-exchange-devops:${env.BUILD_TAG}")
                }
            }
        }

        stage('Push Docker Image in DockerRepo'){
            steps{
                    docker.withRegistry('', 'dee64dc0-2100-4007-95b0-48b9d2676a3e'){
                        dockerImage.push();
                        dockerImage.push('latest');
                    }
                    
                }
            }
        }

    }

	post{
		always{
			echo 'Single qoute and run always'
		}
		success{
			echo "Double quote and if all stages pass"
		}
		failure{
			echo 'If something is messed up'
		}
		// changed
		// unstable
	}
}

// pipeline {
//     agent { docker { image 'aditya626/hello-world-python:0.0.1.RELEASE'} }
//     stages {
//         stage('Build in Declartive stage') {
//             steps {
//                 echo "Build in Declartive"
//             }
//         }
//         stage('Test in Declartive stage') {
//             steps {
//                 echo "Test in Declartive"
//             }
//         }
//         stage('Code') {
//             steps {
//                 sh 'python --version'
//             }
//         }
//     }

// 	post{
// 		always{
// 			echo 'Single qoute and run always'
// 		}
// 		success{
// 			echo "Double quote and if all stages pass"
// 		}
// 		failure{
// 			echo 'If something is messed up'
// 		}
// 		// changed
// 		// unstable
// 	}
// }