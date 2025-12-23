# Infrastructure Observability Demo

A GitHub-ready project demonstrating **Cloud Infrastructure** and **Observability** concepts using Terraform, Ansible, and Grafana.

## ⚠️ Important Notice

**This is a MOCK/DEMO project** for educational purposes only. The configurations use placeholder values and simplified setups to demonstrate infrastructure concepts.

**This project does NOT:**
- Touch application code
- Touch Android code
- Deploy real infrastructure (without proper configuration)
- Include production-ready security configurations

## 📋 Project Overview

This project demonstrates three key DevOps and Cloud Infrastructure concepts:

1. **Infrastructure as Code (IaC)** with Terraform
2. **Configuration Management** with Ansible
3. **Monitoring & Observability** with Grafana

## 🏗️ Project Structure

```
infra-observability-demo/
├── terraform/
│   ├── main.tf          # Main Terraform configuration
│   ├── variables.tf     # Variable definitions
│   └── outputs.tf       # Output definitions
├── ansible/
│   └── setup-node.yml   # Ansible playbook for Node.js setup
├── grafana/
│   └── dashboard.json   # Grafana dashboard configuration
└── README.md            # This file
```

## 🛠️ Tools Explained

### Terraform (Infrastructure as Code)

**What is Terraform?**
Terraform is an Infrastructure as Code (IaC) tool that allows you to define and provision cloud infrastructure using declarative configuration files.

**What does it do?**
- Defines infrastructure resources (servers, networks, databases, etc.) in code
- Enables version control for infrastructure
- Allows reproducible infrastructure deployments
- Supports multiple cloud providers (AWS, Azure, GCP, etc.)

**In this project:**
The Terraform configuration defines three mock services:
- **Backend Service**: Mock EC2 instance for backend operations
- **AI Service**: Mock EC2 instance for AI/ML workloads
- **Blockchain Service**: Mock EC2 instance for blockchain operations

**Files:**
- `terraform/main.tf`: Defines the three EC2 instances
- `terraform/variables.tf`: Contains configurable variables (region, instance type, AMI IDs)
- `terraform/outputs.tf`: Outputs instance IDs and IPs after deployment

### Ansible (Configuration Management)

**What is Ansible?**
Ansible is a configuration management and automation tool that helps you manage and configure servers.

**What does it do?**
- Automates software installation and configuration
- Manages system settings and services
- Executes tasks across multiple servers
- Uses simple YAML files (playbooks) for configuration

**In this project:**
The Ansible playbook demonstrates:
- Installing Node.js and npm
- Creating a mock Node.js service
- Setting up a systemd service to run the mock service
- Verifying the installation

**Files:**
- `ansible/setup-node.yml`: Playbook that installs Node.js and sets up a mock service

### Grafana (Monitoring & Observability)

**What is Grafana?**
Grafana is an open-source analytics and visualization platform used for monitoring and observability.

**What does it do?**
- Creates dashboards to visualize metrics
- Monitors system performance and health
- Integrates with data sources like Prometheus, InfluxDB, etc.
- Provides real-time insights into infrastructure and applications

**In this project:**
The Grafana dashboard includes:
- **Request Count**: Number of HTTP requests per second
- **Service Uptime**: How long services have been running
- **Response Time**: Latency metrics (50th and 95th percentiles)
- **Service Health Status**: Table showing service availability

**Files:**
- `grafana/dashboard.json`: Dashboard configuration with mock Prometheus metrics

## 🚀 Getting Started

### Prerequisites

- **Terraform**: Install from [terraform.io](https://www.terraform.io/downloads)
- **Ansible**: Install from [ansible.com](https://docs.ansible.com/ansible/latest/installation_guide/index.html)
- **Grafana**: Install from [grafana.com](https://grafana.com/docs/grafana/latest/setup-grafana/installation/)

### Using Terraform

```bash
cd terraform

# Initialize Terraform
terraform init

# Review the execution plan
terraform plan

# Apply the configuration (creates resources)
terraform apply

# Destroy resources when done
terraform destroy
```

**Note**: The AMI IDs in `variables.tf` are mock values. Replace them with real AMI IDs for your AWS region before applying.

### Using Ansible

```bash
cd ansible

# Run the playbook (requires an inventory file)
ansible-playbook -i inventory setup-node.yml

# Or run against a specific host
ansible-playbook -i "your-server-ip," setup-node.yml
```

**Note**: You'll need to create an inventory file or specify target hosts. The playbook is designed to work with Ubuntu/Debian or RHEL/CentOS systems.

### Using Grafana

1. Import the dashboard JSON:
   - Open Grafana UI
   - Go to Dashboards → Import
   - Upload `grafana/dashboard.json`

2. Configure data source:
   - The dashboard expects Prometheus as a data source
   - Configure Prometheus in Grafana: Configuration → Data Sources → Add Prometheus

**Note**: The dashboard uses mock Prometheus queries. You'll need a running Prometheus instance with appropriate metrics for the dashboard to display real data.

## 📝 Key Concepts Demonstrated

### Infrastructure as Code (IaC)
- Version-controlled infrastructure
- Declarative configuration
- Resource provisioning automation

### Configuration Management
- Automated software installation
- Service management
- System configuration

### Observability
- Metrics collection and visualization
- Service health monitoring
- Performance tracking

## 🔒 Security Note

This is a **demo project** with simplified configurations. For production use:
- Add proper security groups and IAM roles
- Use secrets management (AWS Secrets Manager, HashiCorp Vault)
- Implement network security best practices
- Add authentication and authorization

## 📚 Learning Resources

- [Terraform Documentation](https://www.terraform.io/docs)
- [Ansible Documentation](https://docs.ansible.com/)
- [Grafana Documentation](https://grafana.com/docs/)

## 🤝 Contributing

This is a demonstration project. Feel free to use it as a learning resource or starting point for your own infrastructure projects.

## 📄 License

This project is provided as-is for educational purposes.

---

**Remember**: This is a mock/demo setup. Always review and customize configurations before using in any environment.

