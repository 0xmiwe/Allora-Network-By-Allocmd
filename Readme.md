1. Configuration requirements
   Configuration requirements for 1 topic 
   Operating System: Ubuntu 
   CPU: 1-2 core.
   Memory: 2 to 3 GB.
   Storage: SSD or NVMe with at least 5GB of space.

   The instructions below have 2 worker sets Worker 1and Worker 2.
   Each worker set runs 3 topics, corresponding to 3 worker nodes.
   Each worker set should be configured with a minimum of 3 CPU cores and 6GB RAM.
   Instructions to check CPU and RAM in use 
   Settings htopto check CPU and RAM usage:

    ```sh
   sudo apt-get install htop
   ```

   After installation, run the command htopto see the CPU and RAM information in use.
   If CPU and RAM usage is too high, you should not install more Workers.
   (Click qor tap Quitto exit htop)

2. Install tool and create worker wallet
 Documents
For more details, see the official guide at:

   - https://docs.allora.network/devs/workers
   - https://app.allora.network/points/overview
   - https://github.com/allora-network/basic-coin-prediction-node
   - https://github.com/allora-network/allora-huggingface-walkthrough
   - https://github.com/0xmoei/allora-testnet

  **Install necessary software:**
    Install allorad

    ```sh
    curl -sSL https://raw.githubusercontent.com/allora-network/allora-chain/main/install.sh | bash -s -- v0.2.7
    ```

 **The result of successful installation is as follows:**

   ```sh
   Installation complete. The allorad is now available in /root/.local/bin
   To make allorad available from any terminal session, add the following line to your .bashrc or .zshrc:
   export PATH="$PATH:/root/.local/bin"
   ```


 **Add to .bashrc file to be able to use alloradfrom any terminal**

  ```sh
  vi ~/.bashrc
  ```
 - Click i to switch to edit mode.

  Add the following line at the end of the file, in the above 
  example:

  ```sh
  export PATH="$PATH:/root/.local/bin"
  ```

 - Save and exit by pressing Escthen type :wqand press Enter. (To exit without saving, press Escthen type :q!and press Enter)
   Reload the .bashrc file 

  ```sh
  source ~/.bashrc
  ```

Create a new wallet for the worker node 
allorad keys add net1_worker

Enter the new password twice for the newly created wallet, remember it to access the wallet later.
Save the new wallet information to a txt file, important are: addressand 24 từ mnemonic.
Use faucet to receive uallo: (Wallet address addressin the command above 
Each topic when running for the first time the worker will send a tx to register that topic so uallo is needed to send the tx.
Go to https://faucet.testnet-1.testnet.allora.network/ to receive uallo. Faucet is successful as shown below:
