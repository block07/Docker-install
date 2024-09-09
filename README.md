# Docker Installation Guide

## Introduction

Docker is a platform for developing, shipping, and running applications in containers. This guide will help you install Docker on your system.

## Prerequisites

- A 64-bit operating system
- Root or administrator privileges

## Install Docker on Linux

### Step 1: Update Your System

```bash
sudo apt update
sudo apt upgrade -y
```
### Step 2: Install Required Packages
```
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common
```
### Step 3: Add Docker’s Official GPG Key
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
### Step 4: Add Docker Repository
```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```
### Step 5: Update Package Database
```
sudo apt update
```
### Step 6: Install Docker
```
sudo apt install -y docker-ce
```
### Step 7: Verify Docker Installation
```
sudo systemctl status docker
```
### Step 8: Run Docker as a Non-Root User
#### 1. Create the docker group if it doesn't already exist:
```
sudo groupadd docker
```
#### 2. Add your user to the docker group:
```
sudo usermod -aG docker $USER
```
#### 3. Log out and log back in so that your group membership is re-evaluated.
```
sudo reboot
```
### Step 9: Verify that you can run docker commands without sudo:
```
docker run hello-world
```
