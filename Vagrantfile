Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.provider :virtualbox do |vb|
    vb.customize [ 'modifyvm', :id, '--memory', 800 ]
  end
  config.vm.network "forwarded_port", guest: 3000, host: 4000
  config.vm.synced_folder "~/Documents/src/github/rails-tutorial", "/home/vagrant/rails-tutorial"

  config.vm.provision :shell, inline: "apt-get update"
  config.vm.provision :shell, inline: "apt-get -y upgrade"
  config.vm.provision :shell, inline: "apt-get -y install build-essential libpq-dev git curl emacs make nodejs libsqlite3-dev"
  config.vm.provision :shell, inline: "wget -qO- https://toolbelt.heroku.com/install-ubuntu.sh | sh"

  config.vm.provision :shell, path: "provision/chruby.sh"
  config.vm.provision :shell, path: "provision/ruby-install.sh"
  config.vm.provision :shell, path: "provision/ruby.sh"
  config.vm.provision :shell, path: "provision/rails.sh", privileged: false
  config.vm.provision :shell, path: "provision/mysql-server.sh"
  config.vm.provision :shell, path: "provision/postgresql-server.sh"
end
