# Remote lab

<p>You can specify the box you want to deploy by visiting https://vagrantcloud.com/search and making the change according in the Vagrantfile</p>

## Requirements
-   Vagrant should be installed https://docs.vagrantup.com
-   Be brave and run the commands below

## Get vagrant running
`vagrant up` or to run specific box `vagrant up MyAnsibleServer1`

## Connect to a specific vagrant server
`vagrant ssh <<server-name>> eg: vagrant ssh Server1`

## Show open ports to VM
`vagrant port`

## Run provision
`vagrant provision`

## Other commands
1.  `vagrant status`
2.  `vagrant port`
3.  `vagrant validate`
