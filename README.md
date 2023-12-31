# Kali NetHunter Installation Guide for Termux

Welcome to the Kali NetHunter Installation Guide for Termux repository! This repository aims to provide a comprehensive guide for installing Kali NetHunter within the Termux environment, ensuring a smooth and error-free installation process.

## Installation Steps

To get started with Kali NetHunter in Termux, follow these steps:

1. **Requirements**
    - Ensure Termux is properly installed on your device.
    - Grant storage access by running
      `termux-setup-storage`.
    - Update packages with
      `pkg update && pkg upgrade -y`.
    - Install `wget` using
      `pkg install wget -y`.

2. **Kali NetHunter Installation**
    - Download the installation script:
      ```bash
      wget -O Install-Nethunter https://offs.ec/2MceZWr
      ```
    - Set executable permissions:
      ```bash
      chmod +x Install-Nethunter
      ```
    - Run the installation script:
      ```bash
      ./Install-Nethunter
      ```

3. **Interface Selection**
    - Follow the prompts to select the desired version of Kali NetHunter. When prompted, you may encounter:
    
      ```
      [*] Checking device architecture ... 

      [1] NetHunter ARMhf (full)
      [2] NetHunter ARMhf (minimal)
      [3] NetHunter ARMhf (nano)
      Enter the image you want to install: 1
      ```
    
    - Additionally, you might encounter the following prompt related to deleting the downloaded rootfs file:
    
      ```
      [?] Delete Downloaded Rootfs file? [y/N]
      ```
    
    - To proceed with the installation as intended, respond accordingly. Press `y` to delete the downloaded rootfs file or make your selection based on the provided options.

          - Additionally, during the installation process, upon successful completion, you might encounter an interface similar to the following:

      ```
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
## Contributing

Contributions to enhance and improve this installation guide are welcome! If you find any issues or have suggestions, feel free to submit pull requests or open issues in the repository.

## License

This repository is licensed under [MIT License](LICENSE).

## Acknowledgments

Special thanks to the contributors and the Kali NetHunter community for their valuable contributions and support.

Feel free to explore the contents, follow the installation steps, and begin your Kali NetHunter journey in the Termux environment. Happy hacking!
