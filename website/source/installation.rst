Installation:
=============

Answer consists of two main blocks: - frontend (MySQL, Java, Tomcat) -
backend (MongoDB, Python, nginx)

Installing the Frontend:
~~~~~~~~~~~~~~~~~~~~~~~~

-  Install MySQL 5.7+
-  Create a database user with read and update access. You will need to
   use those credentials in ``answer.properties`` (see
   `Configuration/Customization <#Configurationcustomization>`__
   section)
-  Create a new schema (eg. "answer") and import the following database
   template `SQL zipped
   file <https://github.com/medforomics/Answer_DB_and_Web_App/blob/master/answer_template.zip>`__
-  The template database has a few dummy user accounts setup and all the
   supporting data to use the lookup tool.
-  You will need to match tokens and urls to your server's configuration
   (see `Configuration/Customization <#Configurationcustomization>`__
   section)
-  Install Java 8+ (not tested on Java 9+)
-  Install Tomcat 8.5+
-  Create this directory structure on your sever: ``/opt/answer/``
-  :warning: All files in ``/opt/answer`` should be readable by the
   service running Tomcat. If you are using a shared server, make sure
   only authorized users can read and modify files in
   ``/opt/answer/conf/`` because ALL your credentials are stored in
   ``answer.properties``
-  Copy/paste files from
   `dir\_structure <https://github.com/medforomics/Answer_DB_and_Web_App/tree/master/dir_structure/opt/answer>`__
   in ``/opt/answer/``
-  You will need to add the database details and other credential
   information in ``/opt/answer/conf/`` (see
   `Configuration/Customization <#Configurationcustomization>`__
   section)
-  Copy the web application
   `Answer.war <https://github.com/medforomics/Answer_DB_and_Web_App/blob/master/Answer.war>`__
   to your Tomcat webapps directory (eg. /opt/tomcat/webapps/)

Configuration/Customization:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This section describes how to configure and customize Answer for your
institution (own logo, address, titles, credentials, file paths, etc)
Supporting files, description of directories and templates are in this
`repository <https://github.com/medforomics/Answer_DB_and_Web_App/tree/master/webapp/Answer/external-resources>`__

In ``/opt/answer/conf``:
^^^^^^^^^^^^^^^^^^^^^^^^

answer.properties: DO NOT SHARE THIS FILE! It’s where all modifications
to customize Answer are. Modify the file to save all credentials
(database, ldap, etc), api keys, application settings (eg. prod vs.
dev), login type (ldap, vs local), institution name and application
urls. Save this file to /opt/answer/conf/answer.properties

answer-static-api.properties: links to external APIs. Should not be
modified. Save this file to ``/opt/answer/conf/``

answer-file-paths.properties: Path to static resources (images, fonts,
etc). Unless necessary, the file does not need modification. Save this
file to ``/opt/answer/conf/``

In ``/opt/answer/utils/pdf``:
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Address.txt: address of your institution + main person responsible for
the cancer tests. This information is used in the top left corner of the
PDF report.

In MySQL (Optional):
^^^^^^^^^^^^^^^^^^^^

API token: set your own token to make sure nobody else can use the
following end points:

::

    UPDATE `answer_db`.`token` SET `token` = <{token: }> WHERE `type` = 'parse-mda'; 
    UPDATE `answer_db`.`token` SET `token` = <{token: }> WHERE `type` = 'update-genie'; 
    UPDATE `answer_db`.`token` SET `token` = <{token: }> WHERE `type` = 'dev-login'; 

Unless you intent to update genie to the latest database on your own
(beyond the scope of this documentation), the other end points are for
legacy purposes and leaving the tokens empty won't affect the
application.

For logos in the application and in the PDF, copy your own images in the
paths below, keep aspect ratio when possible. File names must remain the
same. Original images can be found in `this
repository <https://github.com/medforomics/Answer_DB_and_Web_App/tree/master/webapp/Answer/WebContent/resources/images>`__

In ``/opt/answer/links/media/``:
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

``Im5.png``: home page title bar logo

``ngs-tow-lines.png``: home page title bar logo

In ``/opt/answer/utils/pdf/``:
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

``Im5.png``: top PDF page title bar logo

``ngs-tow-lines.png``: top PDF page title bar logo

In Answer (website), an admin should add/remove/edit:
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

-  Users
-  Groups
-  Gene Panels
-  Permissions
-  Clinical Tests See this `documentation
   section <https://answer-wiki.readthedocs.io/en/latest/admin.html>`__

