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

// pipeline {
//     agent any
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
//         stage('Build') {
//             steps {
//                 sh 'docker --version'
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

pipeline {
    agent { docker { image 'aditya626/hello-world-python:0.0.1.RELEASE' } }
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
        stage('Code') {
            steps {
                sh 'python --version'
				sh 'python'
				sh 'print(5+4)'
				sh 'exit()'
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