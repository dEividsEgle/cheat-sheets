# WSL Ubuntu setup
----------
My preferred bash setup in Ubuntu running in WSL.

---------

1. Install the Azure CLI.
```bash
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
```

2. Sign into azure.
```bash
az login

az account show

az account set --subscription "<sub id or name>"
```

3. Install Terraform.
```bash
wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor | sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install terraform
```

4. Setup terraform auto-complete.
```bash
terraform -install-autocomplete
```

5. Set up Ubuntu as default WSL.
```bash
wsl.exe --set-default Ubuntu-22.04
```

6. Setup kubectl auto-complete.
```bash
kubectl completion bash | sudo tee /etc/bash_completion.d/kubectl > /dev/null

### make tab completion to work with kubectl alias *k*

echo 'complete -o default -F __start_kubectl k' >>~/.bashrc
```

7. Set up aliases in bash.
```bash
touch ~/.bash_aliases.sh
vim ~/.bash_aliases
```

```bash
alias tf='terraform'
alias g='git'
alias d='docker'
alias k='kubectl'
alias cls='clear'
```

8. Install starship shell promt.
```bash
curl -sS https://starship.rs/install.sh | sh
```

9. Open ~/.bashrc and ensure the following is at the end of the script.
```bash
vim ~/.bashrc
```

```bash
eval "$(starship init bash)"
export STARSHIP_CONFIG=~/.config/starship/starship.toml
export STARSHIP_DISTRO="🔱 $USER "
complete -C /usr/bin/terraform terraform
complete -o default -F __start_kubectl k
```

- Restart the shell
```bash
source ./bashrc
```

10. Ensure that git is install.
```bash
git --version
```

11. Setup git config.
```bash
vim ~/.gitconfig
```

```bash
[alias]
	hist = log --all --oneline --graph --decorate
[user]
	email = deivids.egle@gmail.com
	name = deivids
[credential "https://github.com"]
	helper = 
	helper = !/usr/bin/gh auth git-credential
```

12. Install net tools.
```bash
sudo apt isntall net-tools
```

12. Update the linux
```bash
sudo apt-get update
sudo apt-get upgrade
```

