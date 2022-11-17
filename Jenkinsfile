pipeline 
    { 
   agent 
		    {
			  label 
			   {
			     label '172.31.42.126'
		             customWorkspace '/data/projects'
			   }
		      
		    }
	  
     
      stages
        {
        stage('slave-1')
            {
              steps
               {           
               sh 'rm -rf *'
		       sh 'git clone https://github.com/Savitayewale/docker-app.git'
			   sh 'cd docker-app'
			   sh 'chmod -R 777 /data/projects/docker-app/index.html'
			   sh 'docker stop savi sanket rani'
			   sh 'docker system prune -a -f'
			   
			   sh 'docker run -itdp 80:80 --name savi httpd'
			   sh 'docker run -itdp 90:80 --name sanket httpd'
               sh 'docker run -itdp 8080:80 --name rani httpd'
			   sh 'docker cp /data/projects/docker-app/index.html savi:/usr/local/apache2/htdocs'
			   
			   sh 'git checkout 22q1 -f'
			   sh 'chmod 777 index.html'
			   sh 'docker cp index.html sanket:/usr/local/apache2/htdocs'
			   sh 'git checkout 22q2 -f'
			   sh 'chmod 777 index.html'
			   sh 'docker cp index.html rani:/usr/local/apache2/htdocs'

                }
            }
        }
    }
