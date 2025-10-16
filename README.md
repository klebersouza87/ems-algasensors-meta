# ems-algasensors-meta
Project to group all others algasensors projects

## Commands used in this project

Creating a ssh key to add in github.
```
ssh-keygen -t ed25519 -C "your email address"
```

You can see your key with:
```
ls -al ~/.ssh
```

With your generate key go to https://github.com and copy and past your id_ed25519.pub value to new SSH Key configuration.
This configuration will enable you to pull requests to github via ssh command in terminal.

### Cloning projects

Before using the commands below, create this projects on github site: ems-algasensors-meta, ems-algasensors-device-management, ems-algasensors-temperature-processing and ems-algasensors-temperature-monitoring.

```
git clone git@github.com:klebersouza87/ems-algasensors-meta.git algasensors
cd algasensors
mkdir microservices
git submodule add https://github.com/klebersouza87/ems-algasensors-device-management.git microservices/device-management
git submodule add https://github.com/klebersouza87/ems-algasensors-temperature-monitoring.git microservices/temperature-monitoring
git submodule add https://github.com/klebersouza87/ems-algasensors-temperature-processing.git microservices/temperature-processing
git status
git commit -m "New modules added"
git push
```

### Additional commands

If you want to update all submodules you can use this command.
```
git pull --recurse-submodules
```

You can clone all submodules with this command:
```
git clone --recurse-submodules -j8 git@github.com:klebersouza87/ems-algasensors-meta.git algasensores-meta-test
```

### Inserts to populate temperature_log table

```
INSERT INTO TEMPERATURE_LOG (ID, REGISTERED_AT, SENSOR_ID, "VALUE") VALUES
('0195cfd5-0487-7da9-a98e-ed69225fc211', '2025-03-25 21:12:00.766567-03', 692426757632926458, 100.0);

INSERT INTO TEMPERATURE_LOG (ID, REGISTERED_AT, SENSOR_ID, "VALUE") VALUES
('0195cfd5-9e8b-7374-b5bf-18fbafdf9537', '2025-03-25 21:12:00.766567-03', 692426757632926458, 50.0);
```