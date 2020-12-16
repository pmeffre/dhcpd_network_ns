# dhcpd_network_ns
Docker container for dhcpd serveur using  network name space. Design to work on Cisco Nexus Docker engine

## Docker Hub

Pull the image from Docker Hub:

docker pull pmeffre/dhcpd_network_ns

## Manually

Clone this repository, and run docker build to build an image:

    #git clone https://github.com/pmeffre/dhcpd_network_ns.git
    #cd dhcpd_network_ns
    #docker build .

## How to use

    #docker run --net=host -v <dhcpd.conf>:/bootflash/data --name dhcpd_ns <username>/dhcpd <interface> <vrf_name>

The most common use-case is to provide DHCP service to the switches of the machine running Docker (Cisco Nexus Docker engine). For that you need to create a configuration for the dhcpd server, start the container with the --net host docker run option and add the path to the switches configuration file with -v option. finally specify the network interface and VRF you want to provide DHCP service on.
