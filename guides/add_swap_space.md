
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

1. Now edit `/etc/fstab` file to make changes permanent.

    ```
    vi /etc/fstab
    ```

1. Paste this at end of file
    ```
    /swapfile swap swap defaults 0 0
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
