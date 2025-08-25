# ems-algasensors-meta
Project to group all others algasensors projects

## Commands used in this project

Creating a ssh key to add in github.
ssh-keygen -t ed25519 -C "your email address"

You can see your key with:
ls -al ~/.ssh

With your generate key go to https://github.com and copy and past your id_ed25519.pub value to new SSH Key configuration.
This configuration will enable you to pull requests to github via ssh command in terminal.

### Cloning projects

git clone git@github.com:klebersouza87/ems-algasensors-meta.git algasensors
cd algasensors
mkdir microservices
git submodule add https://github.com/klebersouza87/ems-algasensors-device-management.git microservices/device-management
git submodule add https://github.com/klebersouza87/ems-algasensors-temperature-monitoring.git microservices/temperature-monitoring
git submodule add https://github.com/klebersouza87/ems-algasensors-temperature-processing.git microservices/temperature-processing
git status
git commit -m "New modules added"
git push

### Additional commands

If you want to update all submodules you can use this command.
git pull --recurse-submodules

You can clone all submodules with this command:
git clone --recurse-submodules -j8 git@github.com:klebersouza87/ems-algasensors-meta.git algasensores-meta-test
