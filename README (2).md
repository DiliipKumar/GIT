# 🚀 Managing Multiple SSH Keys for Different Git Accounts

Handling multiple Git accounts can be tricky, especially when it comes to managing SSH keys. But don't worry! This guide will walk you through setting up and configuring separate SSH keys for different Git accounts, ensuring a smooth workflow.

### 🔧 Prerequisites
Before diving in, ensure you have Git Bash installed. Open Git Bash to get started!

![Git Bash Screenshot](https://github.com/user-attachments/assets/6015e925-581f-4e1b-afbc-f80c44bd3f7b)


## 1. Generate SSH Keys for Each Account

First, generate a new SSH key for each account.


### For Account 1:
```
ssh-keygen -t rsa -b 4096 -C "email_for_account1@example.com"

```
### For Account 2:
```
ssh-keygen -t rsa -b 4096 -C "email_for_account2@example.com"
```
![image](https://github.com/user-attachments/assets/bfe62228-0f56-4778-b220-a84a490fd6cf)

## 2. Add the SSH Keys to the SSH Agent
```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa_account1
ssh-add ~/.ssh/id_rsa_account2
```

![image](https://github.com/user-attachments/assets/7f6017c0-f7c7-44ad-a0f7-acc18d9268c5)

## 3. Configure the SSH Config File

Open the SSH config file:

```
nano ~/.ssh/config

```
Add the following configuration:


```
# GitHub Account 1
Host github-account1
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_account1

# GitHub Account 2
Host github-account2
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_account2

```

And save



