## Step 1 Jenkins Job Enhancement

-Webhook
http://52.67.64.253:8080/github-webhook/

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

![copy artifact plugins installed](./Images/copy-artifact.png)
