This repository contains data for building container images. The resulting image creates a controller application server, including setup for the admin console and controller functionality.

SSL Communication:
The script sets up the necessary certificates for secure communication between the controller and other cluster members, allowing them to join the cluster.

Controller Configuration:

The controller is configured through a bash script, entrypoint.sh, located in the /tmp directory.
The script places the configuration file controller.xml in the correct path: /opt/ibm/wlp/usr/servers/controller/.
It also creates a subdirectory /resources, where the SSH key pair is stored, enabling the functionality to start/stop cluster members.

Configuration Files:

Key configuration files for the server are located in /opt/ibm/wlp/usr/servers/controller/server.xml.
This project is designed to simplify the deployment and management of application servers in a containerized environment. 

Dynamically sets the hostname in the collective-create-include.xml file, using the hostname of the host where the container is running and add this file in to the server.xml

"**For testing purposes."**
