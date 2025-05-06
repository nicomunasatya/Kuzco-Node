# Kuzco-Node
Kuzco Node using vikey API

Tutorial on Running Kuzco Node Without GPU (Can Be Done with 2GB RAM Only!)
Want to run Kuzco Node but don't have a GPU? Don't worry, you can run this node with only a 2GB RAM VPS. This tutorial is perfect for those of you who are still beginners, because it will be explained step-by-step completely and clearly!

🧾 What is Needed?
- VPS (free to use Contabo, Vultr, DigitalOcean, etc.)
- OS: Ubuntu 20.04 or 22.04
- Stable internet connection
- Account on vikey.ai
- Account on the official Kuzco website

Steps
1. Buy VPS
- You can buy VPS from anywhere, for example:
- Contabo (https://contabo.com/en/)
- Vultr (https://www.vultr.com/)
- DigitalOcean (https://www.digitalocean.com/)

Minimum specifications:
RAM: 2GB
OS: Ubuntu (20.04 / 22.04)

2. Install Docker on VPS
Log in to your VPS via SSH, then install Docker:
```sudo apt update && sudo apt install -y docker.io docker-compose```

Activate Docker:
```sudo systemctl start docker 
sudo systemctl enable docker```

