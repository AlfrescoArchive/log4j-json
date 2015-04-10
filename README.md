Output application logs in json format
==========================================

Author: Steve Rigby

This project provides the capability for Alfresco, Share and Solr logs to be output in json 
format for easy consumption by ELK.

The add-on is packaged as an AMP file for easy installation.

To build:
Check out the project, then zip the log4j-json directory.
Rename the resultant .zip file to .amp.
Deploy to a war file using the amp deployment process - see:
http://docs.alfresco.com/5.0/concepts/dev-extensions-modules-intro.html

To use: 

Modify your log4j properties file to include the json appender, e.g.:
Note, ${logfilename} should be substituted for the file name and path.

log4j.appender.Json=org.apache.log4j.FileAppender
log4j.appender.Json.File=${logfilename}.json
log4j.appender.Json.layout=net.logstash.log4j.JSONEventLayoutV1