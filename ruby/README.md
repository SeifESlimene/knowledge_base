git --version
rbenv --version
curl --version
lsb_release -a
curl -fsSL https://github.com/rbenv/rbenv-installer/raw/HEAD/bin/rbenv-installer | bash
rbenv --version
wget -q "https://github.com/rbenv/rbenv-installer/raw/HEAD/bin/rbenv-doctor" -O- | bash
~/.rbenv/bin/rbenv init
echo 'eval "$(/root/.rbenv/bin/rbenv init - bash)"' >> ~/.bashrc
source ~/.bashrc
rbenv --version
wget -q "https://github.com/rbenv/rbenv-installer/raw/HEAD/bin/rbenv-doctor" -O- | bash
ruby --version
rbenv versions
gem env
gem list
