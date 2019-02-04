# <p stytle="align:center">ipfs-private-network</p>

## Setup Instructions

 - Install docker -> https://docs.docker.com/install/
 
 - Install Go -> https://golang.org/doc/install
 
 - Install the swarm key generator
	 - `$ go get github.com/Kubuxu/go-ipfs-swarm-key-gen/ipfs-swarm-key-gen` 
 
 - Generate a new private swam key
	 - `$ ipfs-swarm-key-gen > swarm.key`

- Generate ipfs data directories
	- `$ mkdir -p ./ipfsData/ipfsA ./ipfsData/ipfsB ./ipfsData/ipfsC`

- Add your private swarm.key to the data directories
	- `$ tee ./ipfsData/ipfsA/swarm.key ./ipfsData/ipfsB/swarm.key ./ipfsData/ipfsC/swarm.key <  swarm.key` 

- Start Ipfs instances 
	- `$ docker-compose up -d ipfsA ipfsB ipfsC` 

- Get you machine IP and set it to a environment file
	- `$ echo "HOST_IP=YOUR_MACHINE_IP" > .env`

- Start Ipfs cluster service
	- `$ sudo docker-compose up clusterA clusterB clusterC`