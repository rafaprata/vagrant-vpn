
BASE_BOX_NAME = "focal-server-cloudimg-amd64-vagrant"
BASE_BOX_URL = "https://cloud-images.ubuntu.com/focal/current/focal-server-cloudimg-amd64-vagrant.box"

SERVER_HOSTNAME = "server"
CLIENT_HOSTNAME = "client"

Vagrant.configure("2") do |config|
    config.vm.define :server do |server|
        server.vm.box = BASE_BOX_NAME
        server.vm.box_url = BASE_BOX_URL
        server.vm.hostname = SERVER_HOSTNAME
        server.vm.provider :virtualbox do |v|
            v.name = SERVER_HOSTNAME
        end
    end
    config.vm.define :client do |client|
        client.vm.box = BASE_BOX_NAME
        client.vm.box_url = BASE_BOX_URL
        client.vm.hostname = CLIENT_HOSTNAME
        client.vm.provider :virtualbox do |v|
            v.name = CLIENT_HOSTNAME
        end
    end
end