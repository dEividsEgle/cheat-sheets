----------
WSL Ubuntu setup.

---------

1. Install the Azure CLI.
```
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
```

2. Sign into azure.
```
az login

az account show

az account set --subscription "<sub id or name>"
```

3. Install Terraform.
```
wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor | sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install terraform
```

4. Setup terraform auto-complete.
```
terraform -install-autocomplete
```

5. Set up Ubuntu as default WSL.
```
wsl.exe --set-default Ubuntu-22.04
```

6. Setup kubectl auto-complete.
```
kubectl completion bash | sudo tee /etc/bash_completion.d/kubectl > /dev/null

### make tab completion to work with kubectl alias *k*

echo 'complete -o default -F __start_kubectl k' >>~/.bashrc
```

7. Set up aliases in bash.
```
touch ~/.bash_aliases.sh
```

```
alias tf='terraform'
alias g='git'
alias d='docker'
alias k='kubectl'
alias cls='clear'
```

