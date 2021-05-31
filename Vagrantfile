
BASE_BOX_NAME = "focal-server-cloudimg-amd64-vagrant"
BASE_BOX_URL = "https://cloud-images.ubuntu.com/focal/current/focal-server-cloudimg-amd64-vagrant.box"

BRIDGE_INTERFACE = "wlp2s0"

SERVER_HOSTNAME = "server"
CLIENT_HOSTNAME = "client"

CLIENT_BRIDGE_01 = "192.168.15.180"

Vagrant.configure("2") do |config|
    config.vm.define :server do |server|
        server.vm.box = BASE_BOX_NAME
        server.vm.box_url = BASE_BOX_URL
        server.vm.hostname = SERVER_HOSTNAME
        server.vm.cloud_init do |cloud_init|
            cloud_init.content_type = "text/cloud-config"
            cloud_init.path = "./cloud-init/UserData.yml"
        end
        server.vm.provider :virtualbox do |v|
            v.name = SERVER_HOSTNAME
        end
    end
    config.vm.define :client do |client|
        client.vm.box = BASE_BOX_NAME
        client.vm.box_url = BASE_BOX_URL
        client.vm.hostname = CLIENT_HOSTNAME
        client.vm.cloud_init do |cloud_init|
            cloud_init.content_type = "text/cloud-config"
            cloud_init.path = "./cloud-init/UserData.yml"
        end
        client.vm.network :public_network, bridge: BRIDGE_INTERFACE,
            name: "enp0s8",
            ip: CLIENT_BRIDGE_01,
            netmask: "255.255.255.0"        
        client.vm.provider :virtualbox do |v|
            v.name = CLIENT_HOSTNAME
        end
    end
end