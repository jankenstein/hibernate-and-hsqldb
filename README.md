hibernate-and-hsqldb
====================

A small hello world example using hibernate and hsqldb taken from This is based heavily on the [hibernate-and-hsqldb](https://github.com/jankenstein/hibernate-and-hsqldb) project and is taken from [Java Persistenct with Hibernate](http://www.amazon.com/gp/product/1932394885/tag=ericjank00-20)

Steps to recreate
=================

1.  Create Maven quickstart application using:  

    mvn archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.1

2.  Download HSQLDB from: http://sourceforge.net/projects/hsqldb/files/ and unpack .zip file.

3.  Create application (do some code things).  Code here is taken from Chapter 2 of Java Persistance with Hibernate by Christian Bauer and Gavin King

	a.  Add dependencies to pom.xml (page 42)
	
	b.  Copy jar dependencies into /lib folder (for Ant build -- Yes, this is dumb)
	
	c.  Create Message class (page 43)
	
	d.  Create hibernate mapping file - Message.hbm.xml (page 45)
	
	e.  Create HibernateUtil class (page 56)
	
	f.  Create HelloWorld class with main method (page 46 and 48)
	
	g.  Create hibernate.cfg.xml file (page 51)
	
	h.  Create log4j.properties file (page 58)
	
	i.  Create build.xml file (page 60, 65, 67)
	
4.  Start HSQLDB :: java -classpath ${PROJECT_DIRECTORY}/lib/hsqldb-2.2.9.jar org.hsqldb.Server (page 63)

5.  Export Schema:  
    
    a.  run `ant schemaexport`
    
    b.  Take a look at the generated helloworld-ddl.sql file

6.  Run main method:
    
    a.  run `ant run`
    
    -- or --
    
    b.  Eclipse: Run As... Java Application
    
7.  Behold the data
    
    -- run `ant dbmanager`
    
    -- run `SELECT * FROM "PUBLIC"."MESSAGES"`
    
8.  Profit


TODO
====

1. Find a way to perform functions of the Ant build with Maven
2. Find a way to connect to the latest HSQLDB version
3. Find a way to perform functions of the Ant build with Gradle
