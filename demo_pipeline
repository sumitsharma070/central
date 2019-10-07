Pipeline{
		agent any
		
		stages{
			stage ('Complie Stage') {
				steps{
					withMaven(maven : 'maven_3_6_2') {
						sh 'mvn clean compile'
						}
					}
				}
				
				stage ('Testing Stage') {
					
					steps('Testing Stage') {
						
						steps{
							withMaven(maven : 'maven_3_5_0') {
								sh 'mvn test'
								}
							}
						}
						
						stage ('Deployment Stage') {
							steps{
								withMaven(maven : 'maven_3_5_0') {
								
									sh 'mvn deploy'
								}
							
							}
						}
					}
		}
	}
