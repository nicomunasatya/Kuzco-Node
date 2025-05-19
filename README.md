# Kuzco-Node
## Fundraising Kuzco and Hyperbolic
Using this method you can double earning from confirmed incentive airdrop Gaia Node and retroactive Hyperbolic
Below Fundrasing Gaia and Hyperbolic

![Fundraising Kuzco](https://raw.githubusercontent.com/nicomunasatya/Kuzco-Node/main/image/fundraising%20kuzco.png)

![Fundraising Hyperbolic](https://raw.githubusercontent.com/nicomunasatya/Gaia-Node/main/hyperbolic%20fundraising.png)

## Kuzco Node using vikey API

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
![image](https://raw.githubusercontent.com/nicomunasatya/Kuzco-Node/main/image/1.webp)

👉 My API Key → click Create New API Key
![image](https://raw.githubusercontent.com/nicomunasatya/Kuzco-Node/main/image/2.webp)

4. Top Up Balance on ViKey.ai 💸
Before continuing, you must top up your balance on your ViKey account first.

Why? Because the inference you run later uses ViKey's GPU-based inference service, but you don't need to rent a GPU per hour, just pay according to usage (pay-as-you-go). Much more economical and practical!

Enter the Billing / Top Up menu on the ViKey dashboard, then fill in the balance sufficiently.
![image](https://raw.githubusercontent.com/nicomunasatya/Kuzco-Node/main/image/3.webp)

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
![image](https://raw.githubusercontent.com/nicomunasatya/Kuzco-Node/main/image/4.webp)

9. Edit Konfigurasi nginx dan Docker
```
nano nginx.conf
```
Replace this part:
```
proxy_pass http://YOUR_VPS_IP:14444;
```
🔧 File docker-compose.yml
```
nano docker-compose.yml
```
Fill in the code from your Kuzco account:
```
environment:
  - KUZCO_WORKER=contents_of_kuzco_dashboard
  - KUZCO_CODE=contents_of_kuzco_dashboard
```

10. Run Kuzco Node 🚀
Now let's run the node:
```
docker-compose up -d --build
```
![image](https://raw.githubusercontent.com/nicomunasatya/Kuzco-Node/main/image/5.webp)

🔍 Log Check Tips
Check Kuzco Worker log:
```
docker-compose logs -f --tail 100
```
Check the ViKey Inference log:
```
cd ~/vikey-inference
tail -f vikey.log
```

## Kuzco Node using rent GPU from Hyperbolic
1. First, [Login Hyperbolic](https://app.hyperbolic.xyz/) continue with Google

   ![Login](https://raw.githubusercontent.com/nicomunasatya/Gaia-Node/main/login.png)
2. Go to menu Setting and top up fund 5$ using crypto or visa

   ![Top up](https://raw.githubusercontent.com/nicomunasatya/Gaia-Node/main/top%20up.png)
3. Go to your terminal using your own device or you can use vps.To get your SSH public key on a Linux VPS, follow these steps:

   Run this in your terminal:
   ```
    ls ~/.ssh/id_rsa.pub
   ```
   If the file exists, you already have an SSH public key. To view it:
   ```
    cat ~/.ssh/id_rsa.pub
   ```

4. IMPORTANT copy your ssh public from your device/vps to ssh public hyperbolic in menu settings

   ![ssh public key](https://raw.githubusercontent.com/nicomunasatya/Gaia-Node/main/ssh%20public%20key.png)
5. Rent a GPU for example rent GPU RTX 3070 to rent for one hour pay 0.16 dollars

   ![Rent GPU](https://raw.githubusercontent.com/nicomunasatya/Gaia-Node/main/rent%20gpu.png)
6. Connect your rentu GPU to your device/VPS

   ![Connect GPU](https://raw.githubusercontent.com/nicomunasatya/Gaia-Node/main/connect.png)
7. When it's connected, congratulations, you can use it to work on the Gaia node

   ![ssh login vps](https://raw.githubusercontent.com/nicomunasatya/Gaia-Node/main/ssh%20login%20vps.PNG)
   
8. Clone and Setup Kuzco Node
Now it's time to install the Kuzco node:
```
cd ~
git clone https://github.com/direkturcrypto/kuzco-installer-docker
cd kuzco-installer-docker/kuzco-main
```
9. Get Kuzco Worker & Kuzco Code
Login to the official Kuzco website, then register an account.
After logging in, you will get:

![image](https://raw.githubusercontent.com/nicomunasatya/Kuzco-Node/main/image/4.webp)

  Paste that code to your rent GPU terminal from hyperbolic 

