## Ubuntu

Always better to follow the [original guide](https://docs.docker.com/engine/install/ubuntu/#set-up-the-repository) from docker.

But below is the list of all commands to install docker in one place.

1. Run these to install
    ```
    sudo apt-get update
    sudo apt-get -y install \
        ca-certificates \
        curl \
        gnupg \
        lsb-release
    sudo mkdir -p /etc/apt/keyrings
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
    echo \
      "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
      $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    sudo apt-get update
    sudo apt-get -y install docker-ce docker-ce-cli containerd.io docker-compose-plugin
    ```

1. Test if docker works:
    ```
    docker ps
    ```

1. If you get this `Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock:` error while running `docker ps`
    ```
    sudo usermod -aG docker <replace with username>  # run 'whoami' to get username
    ```
 
 1. Reboot to let settings take effect
     ```
     sudo reboot
     ```
