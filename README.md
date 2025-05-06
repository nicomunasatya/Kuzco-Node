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
```
sudo apt update && sudo apt install -y docker.io docker-compose
```

Activate Docker:
```
sudo systemctl start docker 
sudo systemctl enable docker
```
3. Register an Account at ViKey.ai
Open: 🔗 https://vikey.ai
Then register an account, login, and go to the menu:

👉 My API Key → click Create New API Key

4. Top Up Balance on ViKey.ai 💸
Before continuing, you must top up your balance on your ViKey account first.

Why? Because the inference you run later uses ViKey's GPU-based inference service, but you don't need to rent a GPU per hour, just pay according to usage (pay-as-you-go). Much more economical and practical!

Enter the Billing / Top Up menu on the ViKey dashboard, then fill in the balance sufficiently.

5. Clone and Run ViKey Inference
```
git clone https://github.com/direkturcrypto/vikey-inference
cd vikey-inference
```
Edit file .env:
```
nano .env
```
Fill it like this:
```
VIKEY_API_KEY=ISI_DENGAN_API_KEY_KAMU
NODE_PORT=14444
```
Save the file, then run the application:
```
chmod +x vikey-inference-linux
./vikey-inference-linux
```
If it appears:
```
Ollama server running on port 14444
```
This means that the inference is running! Type ctrl + C to exit this application.

6. Run ViKey Inference in the Background
So that inference continues to run even if you exit the terminal:
```
nohup ./vikey-inference-linux > vikey.log &
```
7. Clone and Setup Kuzco Node
Now it's time to install the Kuzco node:
```
cd ~
git clone https://github.com/direkturcrypto/kuzco-installer-docker
cd kuzco-installer-docker/kuzco-main
```
8. Get Kuzco Worker & Kuzco Code
Login to the official Kuzco website, then register an account.
After logging in, you will get:

KUZCO_WORKER (XXXf8KuZaSJYMSmp-5aP8 -> if the example is in the picture)

KUZCO_CODE (05e1b639-30ef-4437-a2b3-94a5b3f56dc5 -> if the example is in the picture)







