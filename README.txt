Debian packaging for Neo4 server
--------------------------------

To build this, you need a debian (or ubuntu) computer, and need debuild installed:

  sudo apt-get install devscripts

Then just do:

  mvn clean package

And you will have a .deb file in "target/"!

If you get errors saying "Debian revision (`SNAPSHOT') doesn't contain any digits", 
you can explicitly set the version number passed to debuild:

  mvn clean package -Dneo4j.debian.version=1.3

