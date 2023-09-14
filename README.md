# Prometheus Setup + Installation
Go to the official website and under downloads find Prometheus for Linux and copy the link for it.
Now on the Linux machine type “wget and then the URL COPIED”.
Now unzip the file using “ tar -xzvf NAME OF FILE”
Now go into the folder we extracted and we will have multiple files available edi file named Prometheus.yml and at the very bottom change " localhost:9090 " to " PUBLICIP:9090 "
Now use the command “./prometheus --config.file=prometheus.yml “ to start Prometheus.
Now we can’t use the same terminal to do anything so either we can open a new tab or stop Prometheus and work.
Now open a web browser and type “ http://PUBLICIP:9090”
# TILL NOW WE HAVE PROMETHEUS INSTALLED AND WORKING, IF THE PROMETHEUS WEBPAGE DOESN'T POP UP ON BROWSER THEN CHECK ERRORS ABOVE ONLY.
# Grafana Setup + Installation
Go to the official website of Grafana under the download section and under the edition make sure to choose "OSS" and commands to install will be provided just copy and paste it.
Once it is done we will receive commands on screen like starting grafana, keep grafana running, etc. make sure to use all commands to keep it up and running even after restart.
Now go to a browser and type “ localhost:3000 “ it is the default port number for grafana.
Now grafana is installed.
