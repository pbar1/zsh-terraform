# zsh-terraform

Terraform convenience functions and aliases for ZSH

### Install

Depending on your ZSH plugin framework, add the following to your `.zshrc`:

##### zplug
```sh
zplug "pbar1/zsh-terraform"
```

##### Zgen
```sh
zgen load pbar1/zsh-terraform
```

##### Antigen
```sh
antigen bundle pbar1/zsh-terraform
```

### Usage

This is the entire source, I think it speaks for itself:
```sh
alias tf=terraform
alias tfw="terraform workspace"

tfv(){
  terraform validate -var-file=vars/$(terraform workspace show).tfvars
}

tfp(){
  terraform plan -var-file=vars/$(terraform workspace show).tfvars
}

tfa(){
  terraform apply -var-file=vars/$(terraform workspace show).tfvars
}

tfc(){
  terraform console -var-file=vars/$(terraform workspace show).tfvars
}
```
