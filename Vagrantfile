Vagrant.configure("2") do |config|
    config.ssh.forward_agent = true
    config.ssh.insert_key = false

    # Ubuntu 12.02 - Precise Pangolin
    config.vm.define "gozma16" do |gozma16|
        gozma16.vm.box = "geerlingguy/ubuntu1204"
        gozma16.vm.hostname = "gozma16"
        gozma16.vm.network "private_network", ip: "192.168.27.16"
        config.vm.synced_folder "sites/gozma16.local/", "/var/www/gozma16.local/public_html"
        config.vm.synced_folder "sites/adminer.gozma16.local/", "/var/www/adminer.gozma16.local/public_html"
        config.vm.synced_folder "sites/www.gozma16.local/", "/var/www/www.gozma16.local/public_html"
        config.vm.provision "ansible" do |ansible|
            ansible.playbook = "playbook.yml"
        end
    end
end