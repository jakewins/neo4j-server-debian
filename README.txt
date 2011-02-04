Debian packaging for Neo4 server
--------------------------------

To build this, you need a debian (or ubuntu) computer, and need debuild installed:

  sudo apt-get install devscripts

You also need to locally install the server-standalone project with the following added to your pom:

   <plugin>
     <groupId>org.codehaus.mojo</groupId>
     <artifactId>build-helper-maven-plugin</artifactId>
     <version>1.3</version>
     <executions>
       <execution>
         <id>attach-distribution</id>
         <phase>package</phase>
         <goals>
           <goal>attach-artifact</goal>
         </goals>
         <configuration>
           <artifacts>
             <artifact>
               <file>target/${server.shortname}-${pom.version}-unix.tar.gz</file>
               <type>tar.gz</type>
               <classifier>unix</classifier>
             </artifact>
             <artifact>
               <file>target/${server.shortname}-${pom.version}-windows.zip</file>
               <type>zip</type>
               <classifier>windows</classifier>
             </artifact>
           </artifacts>
         </configuration>
       </execution>
     </executions>
   </plugin>
   
Then just do:

mvn clean package

And you will have a .deb file in "target/"!