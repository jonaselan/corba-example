# CORBA Echo Server

This is a primitive CORBA echo server (and client) in three languages, straight from the OMNIOrb and Java tutorials:

http://omniorb.sourceforge.net/omni42/omniORB/index.html
http://docs.oracle.com/javase/7/docs/technotes/guides/idl/jidlExample.html

All server appliations print their IOR and block then. All client applications take the IOR as command-line argument, connect to that servant and call the echo() routine once. You can now run the different client / servers against each other for some 'CORBA is cool' demonstrations. Check the demo.py script.

Everything is optimized to be small, including the Makefile's. Therefore, the usage of a naming service is ommitted.

All code was tested on MacOS X Yosemite, with an OMNIOrb installation from Homebrew.

## Python
- Install OMNIOrb, test that it is available as Python package (import OMNIOrb).
- Go into the ./python subdirectory.
- (Optional) Re-generate stubs and skeletons with "omniorb -bpython ../echo.idl".
- Start the server with "python server.py". It will print the server IOR to be used by the client.
- Start the client with "python client.py <IOR>".

## C++
- Install OMNIOrb.
- Go into the ./cxx subdirectory.
- (Optional) Re-generate stubs and skeletons with "omniorb -bcxx ../echo.idl".
- Call "make" to build client and server.

## Java
- Install a recent JDK.
- Go into the ./java subdirectory.
- (Optional) Re-generate stubs and skeletons with "idlj -fall ../echo.idl".
- Call "make" to build the JAR files for client and server.
- Run the server with "java -jar server.jar".  It will print the server IOR to be used by the client.
- Run the client with "java -jar client.jar <IOR>".
