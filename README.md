# gcb2018-ansible
Ansible skeleton role as hands-on for setting up kraken in the bibigrid cluster for the German Conference on Bioinformatics 2018 (Vienna/Austria)

## What is our goal?
In this hands on, we want you to create an ansible role for installing the bioinformatics tool [Kraken](https://ccb.jhu.edu/software/kraken/).
We want to install kraken on all machines in our freshly created BibiGrid-Cluster. We will need this environment later on
in this Tutorial Series.
  
We will also install [Krona](https://github.com/marbl/Krona/wiki) in our cluster, a tool for data exploring in the fields of metagenomics.

To get started, download this repo in your BibiGrid-Master node by executing on your master node:
```
cd ~
git clone https://github.com/awalende/gcb2018-ansible.git
```
After this, change the directory:
```
cd gcb2018-ansible
```
  
  
You will see various files listed here. Some of these files have tasks assigned on them. We will walk you through these
tasks. 
  
## Tasks

#### Task 0: Create a hosts (inventory) file.
As you remember, an ansible inventory is mandatory.
In the project folder you should see a file called ``hosts``. Open this file in your cloud9 environment
and follow its instructions.


#### Task 1: Edit the site.yml base playbook
The `./site.yml` file in the base-folder of this project, describes all actions that will be executed
in our cluster. This file should include all roles needed for this tutorial. Open the file and edit the missing fields.


#### Task 2: Insert the tasks for the kraken role
In `roles/gcb2018.kraken/tasks/main.yml`, you will see a list of tasks needed to be executed in order to get kraken installed.
I have set up the basic structure. You will need to fill out the missing fields. Follow the instructions in this file
and prepare to "google" for some ansible modules ;)

#### Task 3: Get familiar with Ansible Galaxy.
Including the kraken role (which you have finished creating) is sadly not enough. We need an additional role
for installing Krona, our visualisation tool. I have uploaded a role for this tool to Ansible Galaxy.
You will need to use the ansible-galaxy command-line-tool in order to download this role to your BibiGrid-master node.
Follow the instructions in the file ``./site.yml``, which you have previously edited in Task 1. On the lower part
of the file you should see the instructions for this task.

##### Optional: Install more roles form Ansible-Galaxy
You can also search for roles with ``ansible-galaxy search [TAGS]``. Try installing and adding various roles.
ANXS.nodejs and ANXS.build-essential are good starts.
