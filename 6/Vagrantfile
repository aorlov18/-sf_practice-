Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-18.04"
 
  config.vm.network "forwarded_port", guest: 8080, host: 8080
  
  config.vm.provision "shell", privileged: false, inline: <<-SHELL


  sudo add-apt-repository ppa:deadsnakes/ppa
  sudo apt-get update && yes | sudo apt-get upgrade 

  #install python 3.8 
  sudo apt-get install -y python3.8 python3.8-distutils python3.8-venv python3.8-dev python-pip python3-pip software-properties-common

  #install psycorp2
  sudo apt-get install -y libpq-dev python3-psycopg2 python3-pip
  sudo -H pip3 install Psycopg2
 
  #install django
  sudo apt install -y python3-django python3-venv
SHELL

  config.vm.synced_folder "./6", "/home/vagrant/6"
end
