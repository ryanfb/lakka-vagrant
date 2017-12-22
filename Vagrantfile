Vagrant.configure("2") do |config|
  config.vm.hostname = "lakka-build"
  config.vm.box = "ubuntu/xenial64"
  config.disksize.size = '128GB'

  config.vm.provider "virtualbox" do |v|
    v.memory = 16384
  end

  locale = "en_US.UTF-8"
  config.vm.provision :shell, :inline => "echo 'Setting locale to UTF-8 (#{locale})...' && locale | grep 'LANG=#{locale}' > /dev/null || update-locale --reset LANG=#{locale} && dpkg-reconfigure -f noninteractive locales"
  config.vm.provision :shell, :inline => "echo 'Turning off console beeps...' && grep '^set bell-style none' /etc/inputrc || echo 'set bell-style none' >> /etc/inputrc"
  config.ssh.forward_agent = true
  config.ssh.shell = "bash -c 'BASH_ENV=/etc/profile exec bash'"
  config.vm.provision "shell", :inline => "apt-get update && apt-get upgrade -y && apt-get install -y build-essential wget bc gcc-multilib libc6-dev-i386 patchutils gawk gperf zip unzip texinfo lzop xfonts-utils xsltproc bc patchutils gawk gperf zip unzip texinfo lzop xfonts-utils xfonts-utils xfonts-utils xsltproc libncurses5-dev libjson-perl git pkg-config u-boot-tools && apt-get autoremove && apt-get autoclean"
end
