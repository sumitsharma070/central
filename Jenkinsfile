Pipeline{
		agent any
		tools{
		maven 'maven3.6.2'
		jdk 'jdk8'
		}
		
		stages{
		 stage ('Compile') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }
			stage ('Build') {
				steps{
					withMaven(maven : 'maven_3_6_2') {
						sh 'mvn clean compile'
						}
					}
				}
				
				stage ('Test') {
					
					steps('Testing Stage') {
						
						steps{
							withMaven(maven : 'maven_3_5_0') {
								sh 'mvn test'
								}
							}
						}
						
						stage ('Deployment') {
							steps{
								withMaven(maven : 'maven_3_5_0') {
								
									sh 'mvn deploy'
								}
							
							}
						}
					}
		}
	}
