pipeline{
	agent any
	   stages{
		    stage('Deploy 2026Q1-Branch'){
		       steps{
			    git branch: '2026Q1-Branch', url: 'https://github.com/ShreehariBandrawad/Dockerrepo.git'
			    script{
				sh '''
				docker rm -f c1 || true
				docker run -d --name c1 -p 80:80 httpd
				docker exec c1 rm -rf /usr/local/apache2/htdocs/*
				docker cp . c1:/usr/local/apache2/htdocs/
				'''
			    }

			}	
		    }
	            stage('Deploy 2026Q2-Branch'){
                       steps{
                            git branch: '2026Q2-Branch', url: 'https://github.com/ShreehariBandrawad/Dockerrepo.git'
                            script{
                                sh '''
                                docker rm -f c2 || true
                                docker run -d --name c2 -p 90:80 httpd
                                docker exec c2 rm -rf /usr/local/apache2/htdocs/*
                                docker cp . c2:/usr/local/apache2/htdocs/
                                '''
                            }

                        }
                    }
	            stage('Deploy 2026Q3-Branch'){
                       steps{
                            git branch: '2026Q3-Branch', url: 'https://github.com/ShreehariBandrawad/Dockerrepo.git'
                            script{
                                sh '''
                                docker rm -f c4 || true
                                docker run -d --name c4 -p 80:80 httpd
                                docker exec c4 rm -rf /usr/local/apache2/htdocs/*
                                docker cp . c4:/usr/local/apache2/htdocs/
                                '''
                            }

                        }
                    }
	}
}
