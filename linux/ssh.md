##### Create the key pair:

> `$ ssh-keygen -t rsa -b 4096 -f ~/.ssh/vps-cloud.web-server.key -C "My web-server key"`

##### Install the public key in remote server:

> `$ ssh-copy-id -i $HOME/.ssh/linode.pub root@139.162.179.236`

##### Try Logging Into The Machine:

> `$ ssh root@139.162.179.236`
