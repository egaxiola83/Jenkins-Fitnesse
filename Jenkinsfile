pipeline {
    agent any

    stages {
        stage('FitNesseStarting') {
            steps {
                echo 'Connecting to FitNesse'
			}
		}
		stage('Run Tests'){
			parallel{
				
				stage('ExecutingSuite') {
					steps{
						echo 'Executing Suite'
						step([$class: 'FitnesseBuilder', options: [fitnesseStart: 'False', fitnessePathToJunitResultsOut: '', fitnesseHost: 'localhost', fitnessePassword: '', fitnesseHttpTimeout: '', fitnesseEnableSsl: 'false', fitnesseTestTimeout: '', fitnesseTargetIsSuite: 'false', fitnessePortRemote: '8080', fitnesseTargetPage: 'FrontPage.fitnessetest.SuitePage?suite&partitionCount=2&partitionIndex=1', fitnessePathToXmlResultsOut: 'C:\\Fitnesse\\fitnesse_suite_results.xml', fitnesseUsername: '']])
						
					}
				}
			}
		}
		stage('Showing Results') {
            steps {
                echo 'Showing results'
				
				step([$class: 'FitnesseResultsRecorder', fitnessePathToXmlResultsIn: 'C:\\Fitnesse\\fitnesse_suite_results.xml'])
			}
		}
    }
}
