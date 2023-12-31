# Kali NetHunter Installation Guide for Termux

Welcome to the Kali NetHunter Installation Guide for Termux repository! This repository aims to provide a comprehensive guide for installing Kali NetHunter within the Termux environment, ensuring a smooth and error-free installation process.

## Installation Steps

To get started with Kali NetHunter in Termux, follow these steps:

1. **Requirements**
  - Ensure Termux is properly installed on your device.
  - Grant storage access by running
  ```bash
    termux-setup-storage
  ```
  - Update packages with
  ```bash
    pkg update && pkg upgrade -y
  ```
  - Install `wget` using
  ```bash
    pkg install wget -y
  ```

3. **Interface Selection**
    - Follow the prompts to select the desired version of Kali NetHunter. When prompted, you may encounter:
    
   ```bash
      [*] Checking device architecture ... 

      [1] NetHunter ARMhf (full)
      [2] NetHunter ARMhf (minimal)
      [3] NetHunter ARMhf (nano)
      Enter the image you want to install: 1
    ```
    
    - Additionally, you might encounter the following prompt related to deleting the downloaded rootfs file:
    
   ```bash
   [?] Delete Downloaded Rootfs file? [y/N]
    ```
    
    - To proceed with the installation as intended, respond accordingly. Press `y` to delete the downloaded rootfs file or make your selection based on the provided options.

    - Additionally, during the installation process, upon successful completion, you might encounter an interface similar to the following:

   ```bash
      ##################################################
      ##                                              ##
      ##  88      a8P         db        88        88  ##
      ##  88    .88'         d88b       88        88  ##
      ##  88   88'          d8''8b      88        88  ##
      ##  88 d88           d8'  '8b     88        88  ##
      ##  8888'88.        d8YaaaaY8b    88        88  ##
      ##  88P   Y8b      d8''''''''8b   88        88  ##
      ##  88     '88.   d8'        '8b  88        88  ##
      ##  88       Y8b d8'          '8b 888888888 88  ##
      ##                                              ##
      ####  ############# NetHunter ####################
      
      [=] Kali NetHunter for Termux installed successfully
      
      [+] To start Kali NetHunter, type:
          - `nethunter`               # To start NetHunter CLI
          - `nethunter kex passwd`    # To set the KeX password
          - `nethunter kex &`         # To start NetHunter GUI
          - `nethunter kex stop`      # To stop NetHunter GUI
   ```
   - Use the provided commands to initiate and manage Kali NetHunter within your Termux environment.

## Fixing Errors on Kali NetHunter

  ### Update & Upgrade error in Kali NetHunter

  If you encounter an error while trying to update Kali NetHunter using `apt update`, which looks similar to this:

  ```bash
    ┌──(kali㉿localhost)-[~]
    └─$ apt update
    Ign:1 http://http.kali.org/kali kali-rolling InRelease
    Ign:1 http://http.kali.org/kali kali-rolling InRelease
    Ign:1 http://http.kali.org/kali kali-rolling InRelease
    Err:1 http://http.kali.org/kali kali-rolling InRelease
      Temporary failure resolving 'http.kali.org'
    Reading package lists... Done
    Building dependency tree... Done
    Reading state information... Done
    All packages are up to date.
    W: Failed to fetch http://http.kali.org/kali/dists/kali-rolling/InRelease  Temporary failure resolving 'http.kali.org'
    W: Some index files failed to download. They have been ignored, or old ones used instead
  ```
  **To resolve this issue, follow these steps:**
  
  1. type `sudo su` in the terminal. You see an interface prompt like this: 
  ```bash
   [sudo] password for kali:
  ```
  2. Enter the password for the superuser permission and press `ENTER`. If you are unsure of the password, the default password for the Kali-Linux and Kali NetHunter is `kali`.
  After entering `sudo su` and providing the password, you’ll be in superuser mode.
  
  3. Now change the directory to `/etc/apt` by entering `cd /etc/apt` Type `ls` to list all contents in the `/etc/apt` directory. You will find a file named `sources.list` in the directory.
  4. To open the file, use the command `nano sources.list`
  In the file you find this type of content:
  ```bash
    deb http://http.kali.org/kali kali-rolling main contrib no>
    # For source package access, uncomment the following line
    # deb-src http://http.kali.org/kali kali-rolling main cont>
  ```
  5. Replace the whole content to this:
  ```bash
    deb http://http.kali.org/kali kali-rolling main contrib no>
    # For source package access, uncomment the following line
    deb-src http://http.kali.org/kali kali-rolling main cont>
  ```
  6. And press `CTRL` + `S` to save the changes, after that press `CTRL` + `x` to close the file
  7. After that enter `cd /home/kali`
  8. Now try to `update` your Kali NetHunter using `apt update`
   
## Contributing

Contributions to enhance and improve this installation guide are welcome! If you find any issues or have suggestions, feel free to submit pull requests or open issues in the repository.

## License

This repository is licensed under [MIT License](LICENSE).

## Acknowledgments

Special thanks to the contributors and the Kali NetHunter community for their valuable contributions and support.

Feel free to explore the contents, follow the installation steps, and begin your Kali NetHunter journey in the Termux environment. Happy hacking!
