Debian packaging for Neo4 server
--------------------------------

To build this, you need a debian (or ubuntu) computer, and need debuild installed:

  sudo apt-get install devscripts

Then just do:

  mvn clean package

And you will have a .deb file in "target/"!

