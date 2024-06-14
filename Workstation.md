**FirstEC2(Workstation)**

_1,Download Chef Workstation(Ubuntu):_

wget https://packages.chef.io/files/stable/chef-workstation/24.4.1064/ubuntu/20.04/chef-workstation_24.4.1064-1_amd64.deb

_Install Chef Workstation(Ubuntu):_

dpkg -i chef-workstation_24.4.1064-1_amd64.deb

_Reference(For all OS):_

https://docs.chef.io/workstation/install_workstation/

_2,Create a cookbook:_

chef generate cookbook cookbookname

_Signup and Login to Chef Server and download Starter Kit in local desktop:_

https://manage.chef.io/login

_Upload Cookbook(Edit changes in default.rb file present in recipes directory:_

knife cookbook upload cookbookname

_3,Upload Starter Kit and Key Pair to EC2 using scp command:_

scp -i "path_to_your_private_key.pem" "path_to_local_file" username@ec2-instance-public-dns:/remote/destination/path/

_4,Bootstrap the client Node:_

knife bootstrap <NODE_IP_OR_HOSTNAME> -x <SSH_USERNAME> -i <PATH_TO_PRIVATE_KEY> --sudo -N <NODE_NAME> --chef-license accept -VV

Reference: https://docs.chef.io/workstation/knife_bootstrap/




