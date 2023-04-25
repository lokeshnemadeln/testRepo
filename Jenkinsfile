
pipeline {
    agent {
    label 'node1' 
    }
    stages {
        stage("Parallel Jobs") {
            parallel {
                stage("Task A") 
				{
                  steps 
				  { 
					sh 'ls -la > command.output' 
                  } 
                }				
                stage("Task C") 
				{
                   steps 
				   { 
					//sh 'mkdir /home/node1/lokesh'
					sh '''
                    #!/bin/bash
                    if [ -d "/home/node1/lokesh" ]; then
                            echo "Directory already exists"
                        else
                            mkdir "/home/node1/lokesh"
                        fi
                        '''
                        
					sh 'cp /home/node1/workspace/agentTest/command.output  /home/node1/lokesh '
                   }   
                }
            }
        }
        stage('Task B') 
			{ 
				steps 
				{ 
					echo "The commandOutput run on Node1 "
                } 
			} 
    }
}
