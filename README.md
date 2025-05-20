
# 🧪 Local Metrics & Logs Aggregator

## 🎯 Project Overview

This setup was created for my own fun and QoL improvements during some of my possible tasks.
As I often have to work with logs remotely exported to my local system, this project aims to:

- **Aggregate metrics** from external Kubernetes clusters and local system tools.
- **Visualize data** using Grafana and Grafana Loki dashboards.
- **Maintain a local, containerized environment** for testing and security reasons.

## 🛠️ Tools Used

- **Grafana**: For creating dashboards and visualizing data.
- **Grafana Loki**: For log aggregation.
- **Grafana Alloy**: For collecting and forwarding metrics and logs.
- **Docker Compose**: To orchestrate the local environment.

## 📂 Directory Structure of the project

```
.
├── config/
│   ├── loki-config.yaml
│   ├── alloy-config.yaml
├── docker-compose.yml
```

- `config/loki-config.yaml`: Contains the configuration for Grafana Loki.
- `config/alloy-config.yaml`: Contains config for Grafana Alloy. Almost all the logic happens here to process the logs.
- `docker-compose.yml`: Defines the services for the local environment.

## 🚀 Getting Started

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/DecseiD/local-metrics-aggregator.git
   cd local-metrics-aggregator
   ```

2. **Place Your Data**:

   - Mount your local folder where you store the logs as a volume to Grafana Alloy service in the Docker compose file.
   - Specify the folder within the Grafana Alloy container where it should read the logs in the config/alloy-config.yaml.

3. **Start the Environment**:

   ```bash
   docker-compose up -d
   ```

4. **Access Grafana**:

   Navigate to [http://localhost:3000](http://localhost:3000) in your browser.

   - **Username**: `admin`
   - **Password**: `admin`

## 🧩 Notes

- **Data Compatibility**: Ensure that your exported metrics and logs are in a format compatible with Grafana Alloy and Loki.
- **Customization**: Modify `alloy.config` and `docker-compose.yml` as needed to fit your specific requirements.

## 🐾 Final Thoughts

This setup is a sandbox for exploring the aggregation and visualization of diverse data sources. It's a work in progress, and I welcome any suggestions or contributions.
