#IHMC Workspaces

This repo contains some configurations for pulling down IHMC workspaces quickly.

Currently, these configuration files are in the form of [vcs tool .yaml files](https://github.com/dirk-thomas/vcstool). Note that this is the *vcstool* standard and ***NOT*** the *vcstools* standard.

Note that, for the sake of simplicity, all .yaml files use SSH when defining the repository URLs. You must have SSH keys set up for your GitHub account to use the workspace configurations. Consult the [GitHub Documentation](https://help.github.com/categories/ssh/) for help with this.

###Usage

Install `vcstool`:

```bash
$ sudo apt-get install python-vcstool
```

Clone this repository:

```bash
$ git clone https://github.com/ihmcrobotics/ihmc_workspaces.git
```

Use `vcs import` to clone all of the repositories for the workspace you want to clone.

For example, if you want to pull down the Valkyrie developer Catkin workspace (we recommend overlaying), you could:

```bash
$ sudo apt-get update
$ sudo apt-get install python-vcstool
$ cd ~
$ $ git clone https://github.com/ihmcrobotics/ihmc_workspaces.git
$ mkdir -p ihmc_catkin_ws/src
$ cd ihmc_catkin_ws
$ catkin_init_workspace src
$ cd src
$ vcs import < "$HOME"/ihmc_workspaces/catkin_workspaces/ihmc_valkyrie_developer_workspace.yaml
$ cd ..
$ catkin_make install
$ source ./install/setup.sh
```
