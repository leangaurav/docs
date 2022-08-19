
## Ubuntu  

**Adding swapspace**  

1. Run below commands:
    ```
    sudo swapon --show                  # show current swap details
    sudo fallocate -l 1G /swapfile      # allocate 1G of swap space
    sudo chmod 600 /swapfile
    sudo mkswap /swapfile
    sudo swapon /swapfile
    sudo swapon --show
    ```

1. To make changes permanent paste this `/swapfile swap swap defaults 0 0` at end of `/etc/fstab` 

    ```
    vi /etc/fstab
    ```
    OR
    ```
    sudo echo '/swapfile swap swap defaults 0 0' | sudo tee -a /etc/fstab
    ```

**Removing swap**

1. Turn off swap
    ```
    sudo swapoff -v /swapfile
    ```

1. Remove this entry `/swapfile swap swap defaults 0 0` from `/etc/fstab`.

1. Delete swap file
    ```
    sudo rm /swapfile
    ```


[Source](https://www.cloudbooklet.com/how-to-add-swap-space-on-ubuntu-18-04-google-cloud/)
