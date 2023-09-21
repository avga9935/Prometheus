# Prometheus Setup and Installation
1. Visit the official Prometheus website and navigate to the downloads section.
2. Copy the download link for Prometheus for Linux.
3. On your Linux machine, open a terminal and use the `wget` command with the copied URL to download Prometheus:
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
