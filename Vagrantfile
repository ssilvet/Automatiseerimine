Vagrant.configure("2") do |config|
  # NAT Network nimi
  NAT_NETWORK_NAME = "ansible_ssilvet"

  # Debian 12 - Docker host
  config.vm.define "ssilvet-dockerhost" do |docker|
    docker.vm.box = "debian/bookworm64"
    docker.vm.hostname = "ssilvet-dockerhost"
    docker.vm.network "private_network", ip: "10.10.10.130", netmask: "255.255.255.128", virtualbox__intnet: NAT_NETWORK_NAME
    docker.vm.provider "virtualbox" do |vb|
      vb.name = "ssilvet-dockerhost"
      vb.memory = "8192"
      vb.cpus = "4"
    end
    docker.vm.provision "shell", inline: <<-SHELL
      apt-get update && apt-get install -y snmpd tmux mc wget tree git
      apt-get install -y docker.io docker-compose
      systemctl enable --now docker
    SHELL
  end

  # Debian 12 - Ansible host
  config.vm.define "ssilvet-ansible" do |ansible|
    ansible.vm.box = "debian/bookworm64"
    ansible.vm.hostname = "ssilvet-ansible"
    ansible.vm.network "private_network", ip: "10.10.10.131", netmask: "255.255.255.128", virtualbox__intnet: NAT_NETWORK_NAME
    ansible.vm.provider "virtualbox" do |vb|
      vb.name = "ssilvet-ansible"
      vb.memory = "1024"
      vb.cpus = "1"
    end
    ansible.vm.provision "shell", inline: <<-SHELL
      apt-get update && apt-get install -y snmpd tmux mc wget tree git
      apt-get install -y ansible sshpass yamllint ansible-lint
    SHELL
  end

  # Ubuntu 24.04
  config.vm.define "ssilvet-ubuntu" do |ubuntu|
    ubuntu.vm.box = "ubuntu/jammy64"
    ubuntu.vm.hostname = "ssilvet-ubuntu"
    ubuntu.vm.network "private_network", ip: "10.10.10.132", netmask: "255.255.255.128", virtualbox__intnet: NAT_NETWORK_NAME
    ubuntu.vm.provider "virtualbox" do |vb|
      vb.name = "ssilvet-ubuntu"
      vb.memory = "1024"
      vb.cpus = "1"
    end
    ubuntu.vm.provision "shell", inline: <<-SHELL
      apt-get update && apt-get install -y snmpd tmux mc wget tree git
    SHELL
  end

  # CentOS Stream 9
  config.vm.define "ssilvet-centos" do |centos|
    centos.vm.box = "generic/centos9s"
    centos.vm.hostname = "ssilvet-centos"
    centos.vm.network "private_network", ip: "10.10.10.133", netmask: "255.255.255.128", virtualbox__intnet: NAT_NETWORK_NAME
    centos.vm.provider "virtualbox" do |vb|
      vb.name = "ssilvet-centos"
      vb.memory = "1024"
      vb.cpus = "1"
    end
    centos.vm.provision "shell", inline: <<-SHELL
      dnf install -y net-snmp tmux mc wget tree git
    SHELL
  end

  # OpenSUSE Leap
  config.vm.define "ssilvet-opensuse" do |opensuse|
    opensuse.vm.box = "opensuse/Leap-15.4.x86_64"
    opensuse.vm.hostname = "ssilvet-opensuse"
    opensuse.vm.network "private_network", ip: "10.10.10.134", netmask: "255.255.255.128", virtualbox__intnet: NAT_NETWORK_NAME
    opensuse.vm.provider "virtualbox" do |vb|
      vb.name = "ssilvet-opensuse"
      vb.memory = "1024"
      vb.cpus = "1"
    end
    opensuse.vm.provision "shell", inline: <<-SHELL
      zypper refresh && zypper install -y net-snmp tmux mc wget tree git
    SHELL
  end
end
