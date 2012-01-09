Vagrant::Config.run do |config|
  config.vm.box = "lucid32"
  config.vm.box_url = "http://files.vagrantup.com/lucid32.box"

  # config.vm.network "33.33.33.10"
  config.vm.forward_port "http", 80, 8080

  # config.vm.share_folder "v-data", "/vagrant_data", "../data"

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = [ "cookbooks", "cookbooks-in-progress" ]
    chef.data_bags_path = "data_bags"
    chef.roles_path = "roles"
    chef.add_role "vagrant"

    # You may also specify custom JSON attributes:
    #chef.json = { :mysql_password => "foo" }
  end
end
