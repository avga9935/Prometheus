# Prometheus Setup and Installation
Visit the official Prometheus website and navigate to the downloads section.
Copy the download link for Prometheus for Linux.
On your Linux machine, open a terminal and use the `wget` command with the copied URL to download Prometheus:
   ```bash
   wget <PROMETHEUS_DOWNLOAD_URL>
   ```
Unzip the downloaded file using the tar command: 
   ```bash
tar -xzvf <PROMETHEUS_FILE_NAME>
```
Enter the extracted folder and locate the prometheus.yml file.
Edit the prometheus.yml file and change "localhost:9090" to "PUBLICIP:9090" at the bottom.
Start Prometheus with the following command: 
   ```bash
./prometheus --config.file=prometheus.yml
```
To free up the terminal, either open a new tab or stop Prometheus
## Running Prometheus as a Service
Create a service file to run Prometheus as a background service.
Open a web browser and enter " URL:9090 "
## Node Exporter Setup
# Perform these steps on the second machine:
Ensure you can SSH from one machine to the other without issues. Verify that SSH keys are generated and copied to the authorized_keys file.
Visit the Prometheus official website's download section and copy the download link for Node Exporter for Linux.
On the second machine, use following command :
```bash
wget <NODE_EXPORTER_DOWNLOAD_URL>
tar -xzvf <NODE_EXPORTER_FILE_NAME>
./node_exporter --web.listen-address IP_OF_SAME_MACHINE:8080
```
# we can use any random port number as well,but make sure that port is not in use
# To free up the terminal, open a new window/tab or stop the service.
## Connecting Prometheus and Node Exporter
Stop Prometheus on the Prometheus server using CTRL+C.
Locate the prometheus.yml file in the Prometheus folder.
Under the "static config" section, add the IP and port used when starting Node Exporter.
Start Prometheus again.
In your browser, go to localhost:9090, click on "STATUS," then "TARGETS," and ensure that all Node Exporter targets are UP.
## Grafana Setup and Installation
Visit the official Grafana website's download section and choose "OSS" edition.
Copy and paste the provided installation commands.
After installation, follow any on-screen instructions to start Grafana. Ensure it runs automatically after restart
Access Grafana by opening a browser and navigating to localhost:3000.
To manually start Grafana, use: 
```bash
systemctl start grafana-server
```
##    Grafana Graph Setup
In the Grafana homepage, log in and click "Add a Dashboard."
You'll be prompted to connect a data source. Select Prometheus and enter the URL to access Prometheus. Save and exit.
Go back to the dashboard, select the data you want to visualize on graphs or tables.
Save the dashboard to avoid reconfiguration each time.
