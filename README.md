# hpc_dotfiles
dotfiles for bash shell loaded at login - subset of [dotfiles](https://github.com/caseyyoungflesh/dotfiles) for hpc resources:

 * `~/.hpc_bash_prompt` used to change shell prompt
 * `~/.hpc_aliases` used to set aliases for shell commands

For git:

 * `~/.gitconfig` used to configure git options

On setup, add the following to existing `.bash_profile` on hpc resource to source necessary files:

```
#source files on login
source ~/.hpc_aliases
source ~/.hpc_bash_prompt

#load commonly used modules (if required)
module load git
module load torque
```

Additionally, add the following to `config` in `~/.ssh` (create file if necessary) if using ssh keys for authentication - this stores ssh key password in key agent:

```
Host *
  UseKeychain yes
  AddKeysToAgent yes
  IdentityFile ~/.ssh/id_rsa
```
