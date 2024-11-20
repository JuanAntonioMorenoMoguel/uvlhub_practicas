Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/jammy64"
    
    config.vm.network "forwarded_port", guest: 5000, host: 8080
    
    # Sincronización de la carpeta de tu proyecto para que sea accesible desde la VM
    config.vm.synced_folder ".", "/home/vagrant/app", type: "virtualbox"
    
    # Aprovisionamiento con Ansible
    config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"  # Nombre del archivo playbook de Ansible
    ansible.extra_vars = {
      ansible_python_interpreter: "/usr/bin/python3"
    }
  end
end
