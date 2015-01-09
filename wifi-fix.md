# Install Broadcom Wireless Drivers

Once Ubuntu is installed you will have no network connections.
To install the wireless drivers located in drivers/:

 1. Install DKMS

    dkpg -i dkms_2.2.0.3-1.1ubuntu5_all.deb

 2. Install Wireless Drivers

    dkpg -i bcmwl-kernel-source_6.30.223.141+bdcom-0ubuntu2_amd64.deb

