# AMD-ZLUDA-QUBIC 
This is a guide for Linux on how to setup and run your AMD GPUs with ZLUDA on QUBIC network.

#1 Install ROCM for your AMD GPU https://rocm.docs.amd.com/projects/install-on-linux/en/latest/

#2 Download official ZLUDA https://github.com/vosen/ZLUDA and extract it in a folder, take a note of the path because we will need it.

#3 Download gpu.sh and place it where the miner is, then edit the file with "nano gpu.sh" and change 3 values, #1 path of zluda, insert the path you took note of earlier #2 insert your wallet without brackets {} #3 insert your label without brackets {}

#4 Allow the script to be executed by typing "chmod +x gpu.sh"

#5 Run the script with "./gpu.sh" and it should run your AMD card with ZLUDA to mine QUBIC
