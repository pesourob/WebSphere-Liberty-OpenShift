This files contains data for build container images. The finall image have created controller application server. contains setup for admin console and controller feature.  
Scipt setup necessary certificateas for ssl conextion between controller and other members than you can join other members to the cluster. 

controller is configured by bash scripts entrypoint.sh under /tmp this script force controller.xml on right place in /opt/ibm/wlp/usr/servers/controller/
with subdirectory /resources there is a stored pair of the key for ssh comunication for function stop/start for members in cluster.

Keys files :
             /opt/ibm/wlp/usr/servers/controller/server.xml 
             
             
