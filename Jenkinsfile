
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
			   sh 'docker system prune -a -f'
			   sh 'docker run -itdp --name savi 80:80 httpd bash'
			   sh 'docker run -itdp --name sanket 90:80 httpd bash'
                           sh 'docker run -itdp --name rani 8080:80 httpd bash'
		           sh 'chmod 777 index.html'
			   sh 'docker cp index.html savi:/usr/local/apache2/htdocs'
			   sh 'git checkout 22q1'
			   sh 'docker cp index.html sanket:/usr/local/apache2/htdocs'
			   sh 'git checkout 22q2'
			   sh 'docker cp index.html rani:/usr/local/apache2/htdocs'

                }
            }
        }
    }

