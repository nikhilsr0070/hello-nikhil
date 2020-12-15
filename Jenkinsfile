
timestamps {

node () {

	stage ('1st_job - Build') {
 	when {
               expression { choice == '1'}
               }
                steps {
                  echo " Selected,choice 1"
                }
sshPublisher(publishers: [sshPublisherDesc(configName: 'Dev', transfers: [], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
sh """ 
df -h
ls 
 """ 
	}
	stage ('2nd job - Build') {
	    when {
               expression { choice == '2'}
               }
                steps {
                  echo " Selected,choice 2"
                }
 	
sshPublisher(publishers: [sshPublisherDesc(configName: 'qa', transfers: [], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
sh """ 
ls -altr
cat /etc/*release 
 """ 
	}
	stage ('3rd job - Build') {
	    when {
               expression { choice == '3'}
               }
                steps {
                  echo " Selected,choice 3"
                }
 	
sshPublisher(publishers: [sshPublisherDesc(configName: 'Deploy-test', transfers: [], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
sh """ 
echo "----this is success job" 
 """ 
	}
}
}
