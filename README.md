# Shell Historikk

This project contains a small presentation for a lightning talk about shell command history.
The original presentation file is a keynote file and can be opened with Keynote. I have also added a PDF version for portability. Note that the presentation is written in Norwegian.

The demo-box contains a Vagrantfile which can be used to spin up an alpine image in a virtual machine. The Vagrantfile contains some simple provisioning:

1. Three users are added, level1, level2 and level3
2. A premade bash history file is copied into the home folder of each user
3. FZF is installed on user level3

To start the image, install Vagrant and run

`vagrant up`

To ssh into the box, run

`vagrant ssh`

I have added the aliases `l1`, `l2` and `l3` to quickly switch from the vagrant user to level1, level2 and level3.
When you want to switch back to the vagrant user, press `CTRL+D` or type `exit` to log out.

The fzf installation can be copied and used on your own machine. Note that the patch in the Vagrantfile is not generally necessary; only if you are installing fzf for a different user. The install instructions without the patch is copied below:

```bash
git clone --depth 1 https://github.com/junegunn/fzf.git .fzf
cd .fzf
./install --all
```
The `--all` flag will create keybindings for your shell.
