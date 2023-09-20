# Prometheus Setup + Installation
Go to the official website and under downloads find Prometheus for Linux and copy the link for it.
Now on the Linux machine type “wget and then the URL COPIED”.
Now unzip the file using “ tar -xzvf NAME OF FILE”
Now go into the folder we extracted and we will have multiple files available edi file named Prometheus.yml and at the very bottom change " localhost:9090 " to " PUBLICIP:9090 "
Now use the command “./prometheus --config.file=prometheus.yml “ to start Prometheus.
Now we can’t use the same terminal to do anything so either we can open a new tab or stop Prometheus and work.
!Now create a service file to run prometheus as service in background.
Now open a web browser and type “ http://PUBLICIP:9090”
# TILL NOW WE HAVE PROMETHEUS INSTALLED AND WORKING, IF THE PROMETHEUS WEBPAGE DOESN'T POP UP ON BROWSER THEN CHECK ERRORS ABOVE ONLY.
# Node exporter Setup
These all steps needs to be performed on the 2nd machine.
Make sure we can ssh from one machine to other, otherwise we will keep on getting connection refused error.
Make sure keys are generated and copied under authorized_keys file.
Now go to  download section in prometheus official site and look for node exporter for linux and copy the download link.
Now in the machine type “ wget URL COPIED “ 
Now unzip using “ tar -xzvf FILE DOWNLOADED “
Now go into the folder and type “ ./node_exporter --web.listen-address IP OF SAME MACHINE:8080(any random port number can be selected make sure to use the port numbe not being used by any other service).
After running this command again we won’t be able to do anything on the same terminal so either open new window/tab or stop the service.
! Now create a service file to run node_exporter as service in background.

#  Connecting Prometheus+Node Exporter

Now go back to prometheus server and stop it usin CTRL+C.
Now in the prometheus folder look for prometheus.yml file (ITS VERY IMPORTANT AND HEART OF IT) and go at very bottom.
Now under static config and add the ip and port we used at the time of starting node exporter.
Now start the prometheus again
Go to browser and go to localhost:9090 and click on STATUS>TARGETS and look fo the node exporter make sure all of the targets are UP.

# Grafana Setup + Installation
Go to the official website of Grafana under the download section and under the edition make sure to choose "OSS" and commands to install will be provided just copy and paste it.
Once it is done we will receive commands on screen like starting grafana, keep grafana running, etc. make sure to use all commands to keep it up and running even after restart.
Now go to a browser and type “ localhost:3000 “ it is the default port number for grafana.
To start grafana use " systemctl start grafana-server "
Now grafana is installed.

# Grafana Graph Setup

Once we are in the homepage of grafana now login and click on add a dashboard.
Now we will get a prompt as connecting data source, select prometheus there and in the address section type in the URL to access prometheus make no other changes and click on save and exit.
Now go back to dashboard and select the data we would like to access on graph/table.
Now at top right save the dashboard so we don’t need to search and access data every time.
