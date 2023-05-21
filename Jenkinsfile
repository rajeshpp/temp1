properties([parameters([[$class: 'ChoiceParameter', choiceType: 'PT_CHECKBOX', filterLength: 1, filterable: false, name: 'import_flag', randomName: 'choice-parameter', 
                                script: [$class: 'GroovyScript', fallbackScript: [classpath: [], oldScript: '', sandbox: true, script: 'return'], 
                                script: [classpath: [], oldScript: '', sandbox: true, script: 'return [1,2,3,4]']]]])])

pipeline {
    agent any
    triggers {
        cron('* * * * *')
    }
    stages {
		
		stage('Selected Values') {
			steps {
				echo "Values: ${params.import_flag}"
			}
		}
        
        
        stage('Check code quality') {
              parallel {
                    stage('1') {
                      when {
                        expression { params.import_flag == 1 }
                      }
            
                      steps {
                        sh 'echo "1"'
                      }
                    }
            
                    stage('2') {
                      when {
                        expression { params.import_flag == 2 }
                      }
            
                      steps {
                        sh 'echo "2"'
                      }
                    }
              }
        }
    }   
}
