.. include:: ../../variables.rst
.. _downloads:

=========
Downloads
=========

.. contents::
   :local:
   :backlinks: none

This topic contains information about where you can download the Concordium tools and Concordium Wallets for |Net|. You can also find out about the hardware requirements for running a node.


Concordium Mobile Wallet
========================

The Concordium Mobile Wallet is available for iOS and Android™. The Mobile Wallet supports iOS 13 or later and Android 8 or later.

iOS
----

#.  Install `TestFlight <https://apps.apple.com/us/app/testflight/id899247664>`_ on your iPhone to get the Concordium Mobile Wallet for Testnet on iOS.
#.  Follow `this link <https://testflight.apple.com/join/HZRi1WDT>`_ on your iPhone to join our beta. You must have TestFlight installed.

Android
-------

- `Download the Android version of Concordium Mobile Wallet for Testnet <http://distribution.testnet.concordium.com/tools/android/concordium-mobile-wallet_1.0.22(61).apk>`_


Concordium Desktop Wallet
=========================

- `Download the Testnet version of Concordium Desktop Wallet for Windows <https://distribution.testnet.concordium.com/tools/windows/concordium-desktop-wallet-testnet-1.3.0.exe>`_

- `Download the Testnet version of Concordium Desktop Wallet for MacOS <https://distribution.testnet.concordium.com/tools/macos/concordium-desktop-wallet-testnet-1.3.0.dmg>`_

- Download the Testnet version of Concordium Desktop Wallet for Linux®:

   - `AppImage <https://distribution.testnet.concordium.com/tools/linux/concordium-desktop-wallet-testnet-1.3.0.AppImage>`_

      - SHA256 checksum of the download: ``cdab04e41fd0fb9beacdc8e82fb19470b34936a945280a8cb91ba693ad04f620``

   - `Debian package <https://distribution.testnet.concordium.com/tools/linux/concordium-desktop-wallet-testnet-1.3.0.deb>`_

      - SHA256 checksum of the download: ``cf3bc60a3fdf4b73595052bdf40e0857adf9f85500dc76dee64526ac648038cb``

   - `RPM. <https://distribution.testnet.concordium.com/tools/linux/concordium-desktop-wallet-testnet-1.3.0.rpm>`_

      - SHA256 checksum of the download: ``a0542d841f9ad18b85cfe6de669186d56afe304b18e0392541df084f93466b08``


Concordium Ledger App
=====================


  - `Download the Concordium Ledger App 2.0.3 for Ledger firmware version 2.1.0 <https://distribution.mainnet.concordium.software/tools/concordium-ledger-app-2.0.3-target-2.1.0.zip>`_
  - `Download the Concordium Ledger App 2.0.1 for Ledger firmware version 2.0.0 <https://distribution.mainnet.concordium.software/tools/concordium-ledger-app-2.0.1-target-2.0.0.zip>`_

This version of the Ledger App is the same as the one used for Mainnet, so if you already have that installed, you do not need to install this version.

.. _concordium-node-and-client-download:


Concordium Client
=================
Download the Concordium Client:

-  `Download the Concordium Client for Linux <https://distribution.concordium.software/tools/linux/concordium-client_3.0.4-0>`_

   - SHA256 checksum of the download: ``6ea2674ebae5dafd9de3c730db536fc0675627b6b867f05a944a1a60dd5ceca8``

-  `Download the Concordium Client for macOS <https://distribution.concordium.software/tools/macos/signed/concordium-client_3.0.4-0.zip>`_

-  `Download the Concordium Client for Windows <https://distribution.concordium.software/tools/windows/signed/concordium-client_3.0.4-0.exe>`_


Cargo-concordium
================
Download cargo-concordium:

-  `Download cargo-concordium for Linux <https://distribution.concordium.software/tools/linux/cargo-concordium_1.0.0-2>`_

-  `Download cargo-concordium for MacOS <https://distribution.concordium.software/tools/macos/cargo-concordium_1.0.0-2>`_

-  `Download cargo-concordium for Windows <https://distribution.concordium.software/tools/windows/cargo-concordium_1.0.0-2.exe>`_

For information about installing cargo-concordium, see :ref:`Install tools for development <setup-tools>`

Concordium node distributions
=============================

Node Debian package
-------------------
To run a node on a server with Ubuntu, you need a Debian package.

- `Download the Debian package <https://distribution.testnet.concordium.com/deb/concordium-testnet-node_3.0.1_amd64.deb>`_

   - SHA256 checksum of the download: ``ad8ef5c95e35266f2e807788c599f5f163fe83cb3b4de4672cb071c279978dc3``

To learn how to run a node with Ubuntu, see :ref:`Run a node on a server with Ubuntu <run-node-ubuntu>`.

.. _concordium-docker-package-download:

Full suite for running a node on Linux using Docker
---------------------------------------------------
Download the full suite for running a node on Linux using Docker. The suite contains Concordium Node, Concordium Client and cargo-concordium.

- `Download the suite for Linux <https://distribution.testnet.concordium.com/tools/linux/concordium-software-linux-3.0.1-0-testnet.tar.gz>`_

   - SHA256 checksum of the download: ``3c3ba7b6dabcd3431deecfc08b7455c5ee64df49ba799e87061e3a5ed48c55da``

To learn how to run a node with Docker, see :ref:`Run a node with Docker <run-a-node>`.

Native Windows node
------------------------

To run a node on Windows, you need a Windows Installer package. **Please be aware that you should backup your configuration, as the installer will overwrite the current configuration with a standard configuration.**

- `Download the Windows Installer package <https://distribution.concordium.software/windows/Signed/Node-3.0.1.msi>`_

To learn how to run a node on Windows, see :ref:`Run and manage a node on Windows <run-node-windows>`

Native Mac node
----------------

To run a node on macOS, you need a macOS installer package. **Please be aware that you should backup your configuration, as the installer will overwrite the current configuration with a standard configuration.**

- `Download the macOS installer package <https://distribution.concordium.software/macos/signed/concordium-node-3.0.1.pkg>`_

To learn how to run a node on Mac, see :ref:`Run and manage a node on macOS  <run-node-macos>`.

Testnet genesis block
=====================
The genesis block is included in node distributions.
Download the block separately to inspect it or to run a node in a custom configuration.

- `Download the testnet genesis block <https://distribution.testnet.concordium.com/data/genesis.dat>`_

  - SHA256 checksum of the download: ``592a921e8b43185f1726037bf7e23e78a2ea22ced82179a0840d42088e28f44a``


.. _requirements-run-node:

Requirements for running a node
===============================

The following are the minimum system requirements for running a node. If your system does not meet or exceed these requirements, you might not be able to run the node properly.

You need a broadband connection to run a node, and we strongly recommend that the node is running around the clock. This is especially important if you're running a baker node.

If you use a laptop in combination with Docker, sleep mode can cause problems with the Docker container used to run the node.

System requirements
-------------------

-  CPU: A quad core CPU or better of a new generation x64 (AMD Ryzen™ 5000 series or Intel® Core™ 11000 series desktop or mobile CPUs or CPU with similar single threaded performance).

-  Minimum 16 GB of RAM.

-  Minimum of 1TB fast SSD disk space available (minimum NVMe PCI Express 3.0 4x SSD).

Auxiliary tools
===============

Auxiliary tools are a collection of tools that can be used by developers to perform actions as needed.

Encrypt/decrypt tool
--------------------

- `Download the Encrypt/decrypt tool for Linux <https://distribution.concordium.software/tools/linux/utils-1.0.0>`_

- `Download the Encrypt/decrypt tool for Windows <https://distribution.concordium.software/tools/windows/signed/utils-1.0.0.zip>`_

- `Download the Encrypt/decrypt tool for MacOS <https://distribution.concordium.software/tools/macos/signed/utils-1.0.0.zip>`_

For information about how to use the encrypt/decrypt tool, see :ref:`Auxiliary tools  <developer-tools>`.
