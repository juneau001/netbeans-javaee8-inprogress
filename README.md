# netbeans-javaee8-inprogress
Apache NetBeans Java EE 8 Support Repository (In Progress)

This repository consists of the modified modules required to enable Java EE 8 support in Apache NetBeans 11.0.  The sources in this repository are in progress and there may still be bugs or some missing functionality.  Once approved, these sources will be used to create a pull request for the inclusion of Java EE 8 support in Apache NetBeans proper.

To use these sources, follow these steps:
 
1) Download the Apache NetBeans 11.0 sources, which can be found at the following link:  https://netbeans.apache.org/download/nb110/nb110.html 

2) Once the Apache NetBeans 11.0 sources have been downloaded and extracted to a directory on your machine, clone this repository to your machine.  

3) Overwrite the "enterprise" directory of the Apache NetBeans 11.0 sources with the entire contents of the "enterprise" directory in this repository.

4) Copy the cluster.properties file, which resides within the nbbuild directory of this repository, into the nbbuild directory of the Apache NetBeans 11.0 sources.

5) Build the Apache NetBeans 11.0 sources using the directions contained in the Apache NetBeans README.

6) Once Apache NetBeans 11.0 has been built, navigate into the nbbuild/netbeans/etc directory and open the netbeans.conf file.  Set the netbeans_jdkhome property within the file equal to the path of the JDK you plan to target for Java EE deployment.

Example Using Zulu JDK 8:
netbeans_jdkhome=/Java_Dev/OpenJDK/zulu8.36.0.1-ca-jdk8.0.202-macosx_x64

7) Run Apache NetBeans and use a new userdir, as follows, from within the nbbuild/netbeans directory:

<pre>
./bin/netbeans --userdir "/path/to/userdir/name"
</pre>

8) Open Tools->Plugins and then click on "Available Plugins".  Install the "nbjavac" and "Oracle JS Parser" plugins.

** Your environment should now be ready to do the following:
- Add a GlassFish 5, GlassFish 5.0.1, or GlassFish 5.1 server
- Create new Maven Web Application using the Java EE 8 Platform
- Configure an existing Maven Web Application to utilize the Java EE 8 Platform

** In this early release, you may have to kill the netbeans process after installing Oracle JS Parser and nbjavac.  After you have killed the process, you can restart Apache NetBeans and begin to use for Java EE 8 development.
