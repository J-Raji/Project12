## Step 1 Jenkins Job Enhancement

-Webhook
http://54.207.140.176:8080/github-webhook/

-Branch
PRJ-12

--Jenkins page 52.67.64.253:8080 -admin password d84735f4243e4faf8ea684558518804e

1.Go to your Jenkins-Ansible server and create a new directory called ansible-config-artifact

`sudo mkdir /home/ubuntu/ansible-config-artifact`

2.Change permissions to this directory, so Jenkins could save files there 

`sudo chmod -R 777 /home/ubuntu/ansible-config-artifact`

3.Go to Jenkins web console -> Manage Jenkins -> Manage Plugins -> on Available tab search for Copy Artifact and install this plugin without restarting Jenkins

![copy artifact plugins installed](./Images/copy-artifact.png)

4.Create a new Freestyle project (you have done it in Project 9) and name it save_artifacts

![save artifact freestyle project created](./Images/save-artifact.jpgImages/save-artifact.png)

5.This project will be triggered by completion of your existing ansible project. Configure it accordingly:

![save artifact settings](./Images/save-artifact-setting1.png)

6.create a Build step and choose Copy artifacts from other project, specify ansible as a source project and /home/ubuntu/ansible-config-artifact as a target directory.

![save artifact settings2](./Images/save-artifact-setting2.png)

7.Test your set up by making some change in README.MD file inside your ansible-config-mgt repository (right inside master branch)

![build confirmed](./Images/build.png)

##Step 2 – Refactor Ansible code by importing other playbooks into site.yml

1.create a new file and name it site.yml

2.Create a new folder in root of the repository and name it static-assignments.

3.Move common.yml file into the newly created static-assignments folder

4.Inside site.yml file, import common.yml playbook

---
- hosts: all
- import_playbook: ../static-assignments/common.yml

