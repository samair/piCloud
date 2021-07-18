<h1 align="center">

  Private Home Cloud using RaspberryPI
</h1>
<p align="center">Create your own Private home cloud on a Raspberry Pi.</p>

<p align="center"><a href="https://github.com/create-go-app/cli/releases" target="_blank"><img src="https://img.shields.io/badge/version-v2.2.4-blue?style=for-the-badge&logo=none" alt="cli version" /></a>&nbsp;<a href="https://pkg.go.dev/github.com/create-go-app/cli/v2?tab=doc" target="_blank"><img src="https://img.shields.io/badge/Go-1.16+-00ADD8?style=for-the-badge&logo=go" alt="go version" /></a>&nbsp;<a href="https://gocover.io/github.com/create-go-app/cli/pkg/cgapp" target="_blank"><img src="https://img.shields.io/badge/Go_Cover-89.2%25-success?style=for-the-badge&logo=none" alt="go cover" /></a>&nbsp;<a href="https://goreportcard.com/report/github.com/create-go-app/cli" target="_blank"><img src="https://img.shields.io/badge/Go_report-A+-success?style=for-the-badge&logo=none" alt="go report" /></a>&nbsp;<img src="https://img.shields.io/badge/license-apache_2.0-red?style=for-the-badge&logo=none" alt="license" /></p>

## ⚡️ Quick start

piCloud currently uses
 - A version of https://filebrowser.org/; with some changes to make it work on Raspberrypi
 - Sendgrid APIs to send emails
 - https://ngrok.com/ to generate a dynamic public URL, so that you can access the Raspberry PI cloud from anywhere
 - 🐳 &nbsp; Docker to keep the service up and running 

As a first step you need to have a Raspberry Pi with an Operating System

Install Docker on your RaspberryPi.

#### Installing Docker 
```bash
# update your apt repos
sudo apt-get update && sudo apt-get upgrade

# download a cool script to install docker for you
curl -fsSL https://get.docker.com -o get-docker.sh

# run the script and follow instructions
sudo sh get-docker.sh

# Add use Pi to docker user group
sudo usermod -aG docker pi

# make sure latest version of docker is installed
docker version
```
#### SendGrid API Access
In order to make your Home Cloud on Raspberry Always accessible, when the service starts, it registers to https://ngrok.com/
for a SSH Tunnel. The public URLs generated by https://ngrok.com/ are dynamic in its free version. So we use Sendgrid APIs to send you/admin of the Cloud an email with the currently active public URL. In case you intend to use a Paid version of https://ngrok.com/, this step is optional.

Note - You could use your gmail/public email to begin with 

<a href="https://www.youtube.com/embed/DA2ubUEV1uQ" target="_blank"><img src="http://img.youtube.com/vi/DA2ubUEV1uQ/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>

#### Setup ngrok
Your RaspberryPi can not be accessed publicly unless you have a static IP address. Dont worry, ngrok is here for rescue.
Create a free account with ngrok - https://dashboard.ngrok.com/get-started/setup.
Copy the auth token and keep it, we need it in next steps.

#### Install PiCloud Docker image


## ⚙️ Commands & Options
