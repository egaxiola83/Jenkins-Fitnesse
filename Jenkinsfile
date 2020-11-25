

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

				stage('Addition') {
					steps{
						echo 'Executing Suite Add'
						step([$class: 'FitnesseBuilder', options: [fitnesseStart: 'False', fitnessePathToJunitResultsOut: 'Junit_fitnesse_suite_add_results.xml', fitnesseHost: 'localhost', fitnessePassword: '', fitnesseHttpTimeout: '', fitnesseEnableSsl: 'false', fitnesseTestTimeout: '', fitnesseTargetIsSuite: 'false', fitnessePortRemote: '8080', fitnesseTargetPage: 'FrontPage.fitnessetest.SuitePage?suite&partitionCount=4&partitionIndex=0', fitnessePathToXmlResultsOut: 'fitnesse_suite_add_results.xml', fitnesseUsername: '']])

					}
				}

				stage('Subtraction') {
					steps{
						echo 'Executing Suite'
						step([$class: 'FitnesseBuilder', options: [fitnesseStart: 'False', fitnessePathToJunitResultsOut: 'Junit_fitnesse_suite_sub_results.xml', fitnesseHost: 'localhost', fitnessePassword: '', fitnesseHttpTimeout: '', fitnesseEnableSsl: 'false', fitnesseTestTimeout: '', fitnesseTargetIsSuite: 'false', fitnessePortRemote: '8080', fitnesseTargetPage: 'FrontPage.fitnessetest.SuitePage?suite&partitionCount=4&partitionIndex=3', fitnessePathToXmlResultsOut: 'fitnesse_suite_sub_results.xml', fitnesseUsername: '']])

					}
				}

				stage('Multiplication') {
					steps{
						echo 'Executing Suite'
						step([$class: 'FitnesseBuilder', options: [fitnesseStart: 'False', fitnessePathToJunitResultsOut: 'Junit_fitnesse_suite_mul_results.xml', fitnesseHost: 'localhost', fitnessePassword: '', fitnesseHttpTimeout: '', fitnesseEnableSsl: 'false', fitnesseTestTimeout: '', fitnesseTargetIsSuite: 'false', fitnessePortRemote: '8080', fitnesseTargetPage: 'FrontPage.fitnessetest.SuitePage?suite&partitionCount=4&partitionIndex=2', fitnessePathToXmlResultsOut: 'fitnesse_suite_mul_results.xml', fitnesseUsername: '']])

					}
				}

				stage('Division') {
					steps{
						echo 'Executing Suite'
						step([$class: 'FitnesseBuilder', options: [fitnesseStart: 'False', fitnessePathToJunitResultsOut: 'Junit_fitnesse_suite_div_results.xml', fitnesseHost: 'localhost', fitnessePassword: '', fitnesseHttpTimeout: '', fitnesseEnableSsl: 'false', fitnesseTestTimeout: '', fitnesseTargetIsSuite: 'false', fitnessePortRemote: '8080', fitnesseTargetPage: 'FrontPage.fitnessetest.SuitePage?suite&partitionCount=4&partitionIndex=1', fitnessePathToXmlResultsOut: 'fitnesse_suite_div_results.xml', fitnesseUsername: '']])

					}
				}
			}
		}
		stage('Showing Results') {
            		steps {
                		echo 'Showing results'
				step([$class: 'FitnesseResultsRecorder', fitnessePathToXmlResultsIn: 'fitnesse_suite_*_results.xml'])
				
				step([$class: 'JUnitResultArchiver', checksName: 'Tests', testResults: 'Junit_fitnesse_suite_add_results.xml'])
				step([$class: 'JUnitResultArchiver', checksName: 'Tests', testResults: 'Junit_fitnesse_suite_sub_results.xml'])
				step([$class: 'JUnitResultArchiver', checksName: 'Tests', testResults: 'Junit_fitnesse_suite_mul_results.xml'])
				step([$class: 'JUnitResultArchiver', checksName: 'Tests', testResults: 'Junit_fitnesse_suite_div_results.xml'])

				
		    	
			}
		}
		
    }
}
