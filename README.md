## **Description**
- This is a guide on how to use ZLUDA translation layer that makes AMD/ROCM work on NVIDIA/CUDA only software. the specific use case of this guide is how to make Qubic mining software work on AMD GPUs and help people use their AMD GPUs instead of keeping them for dust collection.

## **Prerequisites**

- Before starting, ensure that you have the following:
  
- An AMD GPU compatible with ROCm.
  
- Access to a terminal on your Linux machine.

  
## **Step 1: Install ROCm for your AMD GPU**

 - You need to install the ROCm (Radeon Open Compute) stack to enable your AMD GPU on Linux.
  
 - Follow the official ROCm installation guide: ROCm Installation.
  
 - Make sure your GPU is supported by ROCm, and your system meets the installation requirements.


## **Step 2: Download and Extract ZLUDA, ZLUDA is a CUDA compatibility layer for Intel and AMD GPUs. Download the latest release and extract it and take a note of the path.** https://github.com/vosen/ZLUDA

  ![image](https://github.com/user-attachments/assets/cbf666f7-c862-45d1-9b23-fef093deb076)

## **Step 2: HiveOS only! use this command to setup ROCM and ZLUDA**

  ```mkdir /usr/lib/zluda && cd /usr/lib/zluda && wget https://github.com/Gddrig/Qubic_Hiveos/releases/download/0.4.1/zluda_hiveos-6.1.zip && unzip zluda_hiveos-6.1.zip && chmod +rwx /usr/lib/zluda/* && cd / && amd-ocl-install 5.7 5.7 && cd /opt/rocm/lib && wget https://github.com/Gddrig/Qubic_Hiveos/releases/download/0.4.1/libamdhip64.so.zip && unzip libamdhip64.so.zip && chmod +rwx /opt/rocm/lib/* && rm libamdhip64.so.zip && cd / && ldconfig && tail -f /var/log/miner/custom/custom.log```

## **Step 3: Download and Edit gpu.sh**

 - You will need a script to help run your miner using ZLUDA with your AMD GPU.

 - Download the gpu.sh script from the Repository, and place it in the same directory as your miner executable.

 - Open the script for editing using nano or your preferred text editor:

   ```nano gpu.sh```

 - Modify the following values inside the script:

 - Path of ZLUDA: Replace with the path where you extracted ZLUDA in Step 2.
  
 - Your Wallet: Insert your QUBIC wallet address (without the curly braces {}).
  
 - Label: Set a label for your mining rig (again, without the curly braces {}).

    ```LD_LIBRARY_PATH="/path/to/zluda/:$LD_LIBRARY_PATH" ./rqiner-x86-cuda -i {WALLET} -l {LABEL}```

 -  **PATH FOR ZLUDA #HiveOS and only if you used Step 2: for HiveOS**

    ```LD_LIBRARY_PATH="usr/lib/zluda:$LD_LIBRARY_PATH" ./rqiner-x86-cuda -i {WALLET} -l {LABEL}```


## **Step 4: Make the Script Executable**

  - Ensure the script has the correct permissions to be executed:

    ```chmod +x gpu.sh```


## **Step 5: Run the Script**

  - Now that everything is set up, you can run the script to start mining on the QUBIC network using ZLUDA with your AMD GPU:

    ```./gpu.sh```
 


## **#NOTE: OS Graphical Interface may lag spike every couple seconds while mining, I personally have RX 7900XTX and I have that issue but mining is smooth and fast.**










