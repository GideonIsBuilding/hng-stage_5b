# Installation Instructions for Java Boilerplate Deployment

## Prerequisites
- Ansible installed on your local machine
- SSH access to target servers
- Basic knowledge of Ansible and YAML

## Setup and Deployment

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd hng-stT...
   ```

2. **Configure Inventory**
   Edit `inventory.cfg` to include your target servers:
   ```ini
   [webservers]
   server1 ansible_host=192.168.1.10
   server2 ansible_host=192.168.1.11
   ```

3. **Set Up Vault**
   Create or edit the `vault.yml` file for sensitive information:
   ```bash
   ansible-vault edit vault.yml
   ```
   Include necessary secrets like database passwords and API keys.

4. **Review Playbook**
   Open `main.yaml` and ensure all tasks and variables are correctly set for your environment.

5. **Run the Playbook**
   Execute the following command:
   ```bash
   ansible-playbook -i inventory.cfg main.yaml --ask-vault-pass
   ```

6. **Monitor Deployment**
   Watch the Ansible output for progress and any potential errors.

7. **Verify Installation**
   Once completed, access your Java application through the configured Nginx server.

## File Structure
```
HNG-ST...
├── templates
├── inventory.cfg
├── main.yaml
├── springboot.service.j2
└── vault.yml
```

## Notes
- Keep `vault.yml` secure and never commit it to version control unencrypted.
- For troubleshooting, check Ansible's output and server logs.
- Customize `main.yaml` as needed for your specific deployment requirements.