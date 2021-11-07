require 'yaml'

file = 'vagrant-config.yml'

# Validation configuration file
if File.file?(file)
    conf_file = YAML.load_file(file)
    if ( defined?(conf_file['machine']) &&
         defined?(conf_file['vagrant_api_version']))

        machine_conf = conf_file['machine']
        vagrant_conf = conf_file['vagrant_api_version']
    else
      raise "Configuration file does not contain machines fields."
    end

    if (defined?(conf_file['web']))
        v_port = conf_file['web'].has_key?('v_http_port') ? conf_file['web']['v_http_port'] : '' 
        if (v_port.nil?)
          raise "Please insert the value of v_http_port key in web key"
        end
        host_port = conf_file['web'].has_key?('host_http_port') ? conf_file['web']['host_http_port'] :  '' 
        if (host_port.nil?)
          raise "Please insert the value of host_http_port key in web key"
        end
    else
      raise 'Configuration for web does not exists! Please add \'web\' key and expected values like in example file.'
    end 
else
  raise "Configuration file 'config.yaml' does not exist."
end
# END of validation configuration

# Vagrant declaration
Vagrant.configure("#{vagrant_conf}") do |config|
    config.vm.provision :shell, :inline => "setenforce 0", run: "always"
    config.vm.box = machine_conf["box"]

    # Minimum values for dev-machine
    config.vm.provider "#{machine_conf['v_provider']}" do |v|
        v.name = machine_conf["v_name"]
        # v.hostname = machine_conf["v_hostname"]
        v.memory = machine_conf["v_memory"]
        v.cpus = machine_conf["v_cpus"]
    end

    # Config port forwarding for http
    config.vm.network "forwarded_port",
       guest: "#{v_port}", host: "#{host_port}"

  # Installation all required packages by tags
    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible/main.yml"
      ansible.tags = "python"
    end

    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible/main.yml"
      ansible.tags = "nginx"
    end
    
    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible/main.yml"
      ansible.tags = "ansible"
    end

    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible/main.yml"
      ansible.tags = "cockpit"
    end

    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible/main.yml"
      ansible.tags = "docker"
    end

  end