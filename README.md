# answer-wiki
This WIKI is a description of the ANSWER web application components.


[How to use Answer](https://answer-wiki.readthedocs.io/en/latest/)

## Installation:

Answer consists of two main blocks:
- frontend (MySQL, Tomcat)
- backend (MongoDB, Python, nginx)

### Frontend installation:

- Install MySQL 5.7+
- Create a new schema and import the following database template [SQL zipped file](https://github.com/medforomics/Answer_DB_and_Web_App/blob/master/answer_template.zip)
- The template database has a few dummy user accounts setup and all the supporting data to use the lookup tool.
- You will need to match tokens and urls to your server's configuration (see customization section)
- Install Tomcat 8.5+
- Create a directory structure in `/opt/answer/`
- Copy/paste files from [dir_structure](https://github.com/medforomics/Answer_DB_and_Web_App/tree/master/dir_structure/opt/answer)
- You will need to add the database and other credential information in `/opt/answer/conf/` (see customization section)
- Copy the web application [Answer.war](https://github.com/medforomics/Answer_DB_and_Web_App/blob/master/Answer.war) to your Tomcat webapps directory (eg. /opt/tomcat/webapps/)

### Customization:

This section describes how to customize Answer for your institution (own logo, address, titles, credentials, file paths, etc) 
Supporting files, description of directories and templates are in this [repository](https://github.com/medforomics/Answer_DB_and_Web_App/tree/master/webapp/Answer/external-resources)

#### In `/opt/answer/conf`: 

application-template.properties: DO NOT SHARE THIS FILE! It’s where all modifications to customize Answer are. Modify the file to save all credentials (database, ldap, etc), api keys, application settings (eg. prod vs. dev), login type (ldap, vs local), institution name and application urls. Save this file to /opt/answer/conf/answer.properties 

answer-static-api.properties: links to external APIs. Should not be modified. Save this file to `/opt/answer/conf/` 

answer-file-paths.properties: Path to static resources (images, fonts, etc). Unless necessary, the file does not need modification. Save this file to `/opt/answer/conf/` 

#### In `/opt/answer/utils/pdf`: 

Address.txt: address of your institution + main person responsible for the cancer tests. Top left corner of the PDF.  

 
#### In MySQL: 

API token: use your own token to make sure nobody else can use the following end points: 

    UPDATE `answer_db`.`token` SET `token` = <{token: }> WHERE `type` = 'parse-mda'; 
    UPDATE `answer_db`.`token` SET `token` = <{token: }> WHERE `type` = 'update-genie'; 
    UPDATE `answer_db`.`token` SET `token` = <{token: }> WHERE `type` = 'dev-login'; 
 

For logos in the application and in the PDF, copy your own images in the paths below, keep aspect ratio when possible. File names must remain the same. Original images can be found on git in webapp/Answer/WebContent/resources/images: 

#### In `/opt/answer/links/media/`: 

Im5.png: home page title bar logo 

ngs-tow-lines.png: home page title bar logo 

#### In `/opt/answer/utils/pdf/`: 

Im5.png: top PDF page title bar logo 

ngs-tow-lines.png: top PDF page title bar logo 


#### In Answer (website), an admin should add/remove/edit: 
- Users 
- Groups 
- Gene Panels 
- Permissions 
- Clinical Tests 
