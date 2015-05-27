### OpenShift Apache Solr 4.10.4 with Drupal Configuration Quickstart

Thanks to Dave Meikle (https://github.com/dameikle)

### Installation

    # Create new jboss application 
    rhc app create solr jbossews-2.0
    
    # Remove build material
    git rm -rf src/ pom.xml
    git commit -a -m "Removing default files"
    
    # Pull in quickstart
    git remote add upstream -m master https://github.com/jbanka/openshift-solr-drupal-quickstart.git
    git pull -s recursive -X theirs upstream master
    
	# Edit .openshift/conf/tomcat-users.xml within the ```<tomcat-user>``` element:

	```
	<role rolename="manager-gui"/>
	<role rolename="solr_admin"/>
	<user username="username" password="password" roles="manager-gui,solr_admin"/>
	```
    # Commit and push
    git commit -am "Solr Quickstart with Drupal conf"
    git push

### Usage

Your Solr Admin URL:
    
    http://solr-<yournamespace>.rhcloud.com/
	
Install and configure Drupal's apachesolr module.    

Your Solr server URL:
    
    http://solr-<yournamespace>.rhcloud.com/
    

### Support

This code is provided provided "as is", with absolutely no warranty expressed or implied. Any use is at your own risk.

