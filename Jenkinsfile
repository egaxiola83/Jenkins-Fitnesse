

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
						echo 'Executing Suite'
						step([$class: 'FitnesseBuilder', options: [fitnesseStart: 'False', fitnessePathToJunitResultsOut: '', fitnesseHost: 'localhost', fitnessePassword: '', fitnesseHttpTimeout: '', fitnesseEnableSsl: 'false', fitnesseTestTimeout: '', fitnesseTargetIsSuite: 'false', fitnessePortRemote: '8080', fitnesseTargetPage: 'FrontPage.fitnessetest.SuitePage?suite&partitionCount=4&partitionIndex=0', fitnessePathToXmlResultsOut: 'C:\\Fitnesse\\fitnesse_suite_results.xml', fitnesseUsername: '']])

					}
				}

				stage('Subtraction') {
					steps{
						echo 'Executing Suite'
						step([$class: 'FitnesseBuilder', options: [fitnesseStart: 'False', fitnessePathToJunitResultsOut: '', fitnesseHost: 'localhost', fitnessePassword: '', fitnesseHttpTimeout: '', fitnesseEnableSsl: 'false', fitnesseTestTimeout: '', fitnesseTargetIsSuite: 'false', fitnessePortRemote: '8080', fitnesseTargetPage: 'FrontPage.fitnessetest.SuitePage?suite&partitionCount=4&partitionIndex=3', fitnessePathToXmlResultsOut: 'C:\\Fitnesse\\fitnesse_suite_results.xml', fitnesseUsername: '']])

					}
				}

				stage('Multiplication') {
					steps{
						echo 'Executing Suite'
						step([$class: 'FitnesseBuilder', options: [fitnesseStart: 'False', fitnessePathToJunitResultsOut: '', fitnesseHost: 'localhost', fitnessePassword: '', fitnesseHttpTimeout: '', fitnesseEnableSsl: 'false', fitnesseTestTimeout: '', fitnesseTargetIsSuite: 'false', fitnessePortRemote: '8080', fitnesseTargetPage: 'FrontPage.fitnessetest.SuitePage?suite&partitionCount=4&partitionIndex=2', fitnessePathToXmlResultsOut: 'C:\\Fitnesse\\fitnesse_suite_mul_results.xml', fitnesseUsername: '']])

					}
				}

				stage('Division') {
					steps{
						echo 'Executing Suite'
						step([$class: 'FitnesseBuilder', options: [fitnesseStart: 'False', fitnessePathToJunitResultsOut: '', fitnesseHost: 'localhost', fitnessePassword: '', fitnesseHttpTimeout: '', fitnesseEnableSsl: 'false', fitnesseTestTimeout: '', fitnesseTargetIsSuite: 'false', fitnessePortRemote: '8080', fitnesseTargetPage: 'FrontPage.fitnessetest.SuitePage?suite&partitionCount=4&partitionIndex=1', fitnessePathToXmlResultsOut: 'C:\\Fitnesse\\fitnesse_suite_div_results.xml', fitnesseUsername: '']])

					}
				}
			}
		}
		stage('Showing Results Add-Sub') {
            		steps {
                		echo 'Showing results'

				build 'ShowAdd'
				build 'ShowSub'
		    	
			}
		}
		
    }
}
