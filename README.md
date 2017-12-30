Calimero Graphical User Interface
=================================

A graphical user interface based on the [Standard Widget Toolkit](https://www.eclipse.org/swt/) for device discovery, process communication, and monitoring.

Download
--------

~~~ sh
# Either using git
$ git clone https://github.com/calimero-project/calimero-gui.git

# Or using hub
$ hub clone calimero-project/calimero-gui
~~~


Supported Features
------------------

* KNXnet/IP discovery and self description
* KNX process communication, read or write a KNX datapoint
* Group monitor for KNX datapoints, decode datapoint values, filter/export KNX messages to file
* Network monitor (busmonitor raw frames on the network, completely passive), filter/export KNX messages to file
* Show device information of a device in a KNX network
* Read the IP configuration of a KNXnet/IP server (Local Device Management) or KNX device (Remote Property Services) using KNX properties
* Scan KNX devices in a KNX subnet area/line, or check whether a specific KNX individual address is currently assigned to a KNX device
* KNX properties viewer for KNX devices that implement an Interface Object Server (IOS)

Supported Access Protocols
--------------------------

* KNXnet/IP Tunneling
* KNXnet/IP Routing (KNX IP)
* KNXnet/IP Local Device Management
* KNX RF USB (Java 8 branch only)
* KNX USB (Java 8 branch only)
* KNX FT1.2 Protocol (serial connections)

Execution
---------

### Using Maven

Resolve/Compile/Install

	mvn clean install -DskipTests -Dgpg.skip=true

On OS X (takes care of the Cocoa thread restrictions)

	mvn exec:exec

On Linux/Windows

	mvn exec:java


### Using Java

The graphical user interface has the following _mandatory_ dependencies: calimero-core, calimero-tools, calimero-rxtx, SWT

The graphical user interface has the following _optional_ dependencies: serial-native

Use your specific version in the following commands.
Either, relying on the Java MANIFEST (check the MANIFEST for exact dependency names and versions)

	java -jar calimero-gui-2.3.jar

If all dependencies are resolved, you can also directly start the GUI by opening it in Nautilus, Windows File Explorer, etc.

Assuming all calimero dependencies (of any compliant version) are in the current working directory (using the JRE `-classpath` or `-cp` option), on first invocation the SWT checker will try to download the appropriate SWT library for your platform (you might have to run the command twice). Note, on MacOS also use `-XstartOnFirstThread`:

	java -cp "./*" tuwien.auto.calimero.gui.SwtChecker
