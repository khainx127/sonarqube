# Sonarqube

## Start Sonarqube on localhost
Persisting your database
```
sudo mkdir -p ./database/sonardb
sudo chown -R 1001:1001 ./database/sonardb
```

Install Java jdk 11 on ubuntu
```
sudo apt-get install openjdk-11-jdk -y
```

Install Java jdk 11 on windows
```
choco install openjdk11
```

Increase Linux setting https://docs.sonarqube.org/latest/requirements/requirements/#header-5
```
sudo sysctl -w vm.max_map_count=524288
sudo sysctl -w fs.file-max=131072
```

Increase Windows WSL setting
```
wsl -d docker-desktop
sysctl -w vm.max_map_count=524288
sysctl -w fs.file-max=131072
```

Increase setting permanently, add `/etc/sysctl.conf` 
```
vm.max_map_count=524288
fs.file-max=131072
```

Run command
```
docker-compose -f docker-compose-local.yml up -d
```

Open `http://localhost:9000` and login by username `admin`, password `admin`

## Create token
Open http://localhost:9000/account/security/ then generate a token
