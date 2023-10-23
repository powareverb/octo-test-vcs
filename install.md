# Notes on Installs

<https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli>

## Ubuntu

```sh
# Prerequisites
sudo apt-get update && sudo apt-get install -y gnupg software-properties-common

# GPG key
wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor | sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg

# Check key
gpg --no-default-keyring \
--keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg \
--fingerprint

# Add source
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list

# Install
sudo apt-get update
sudo apt-get install terraform

touch ~/.bashrc
terraform -install-autocomplete


```
