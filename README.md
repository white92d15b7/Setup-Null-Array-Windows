NulleX – Null Array Setup Guide Windows



What you need
1. More than 50000 NLX
2. One Computer with nullex-qt wallet.  (Put your 50000 NLX in this wallet)
3. One Windows Server VPS with nullex-qt. (This will be your Null Array Wallet)
4. Some time, patience, and a minimal amount of technical knowledge.


Step 1 – Main Wallet

Setup your controller wallet.  This will keep your coins safe.
Download and install nullex-qt for windows.

1.1.  Load the NulleX wallet and sync
1.2.  Set a password on your NulleX wallet (the wallet will shut down, you must restart)
1.3.  Find your wallet.dat file (usually located in c:\Users\username\AppData\Roaming\NulleX
1.4.  Backup your private keys and wallet.dat file (VERY IMPORTANT)
1.5.  Load nullex-qt wallet again and sync.

Step 2 – Main Wallet

2.1.  Click Tools
2.2.  Open Debug Console
2.3.  Click Console in the top tab.

Get your Null Array Key & Null Array Address

2.4.   In the debug console command box (bottom of screen) ENTER:

NullArray genkey

2.5.  You should see something similar to this (save this to a TXT file) THIS is your NA_GENKEY

<-masternode genkey
-> 77hdjYHBnsgi63mstdu444EvWEE36hhWggsd33a8sllcXYW56a

2.6.  Enter the following to create a Null Array address ENTER:

getaccountaddress NA1

(You must replace NA1 with your NULL_ARRAY_ALIAS)

2.7.   You should see something similar to this (save this to the TXT file)

<-getaccountaddress NA1
->9Gy2XTXriArE5nQNSccuKfkM8aQzGsfDkq
Step 3 – Main Wallet

Send 50000 NLX to the Null Array Address & get the outputs

3.1.   Click Send Tab
3.2.   Send 50000 NLX to the address(NULL_ARRAY_ALIAS) from step 2.7.
3.3.   WAIT FOR CONFIRMATIONS
3.4.   Open Debug Console
3.5.   Enter the following to get outputs ENTER:

masternode outputs

3.6.   You should see something like this (save this to the TXT file)

<-[
     {
		“txhash”: “a3cd7s9ddg0874gh8sa8q8t52mmso293sg57sjdys76w90ds762ed9f39d6s6d”,
		“txhash”: : 0
      }
    ];

This is your TX_ID, TX_INDEX

Step – 4  Main Wallet

Edit your NullArray.conf file.

4.1.   Find your NullArray.conf file (usually located in c:\Users\username\AppData\Roaming\NulleX
4.2.   Open NullArray.conf with Notepad you should see something similar to this

# NullArray config file
# Format: alias IP:port masternodeprivkey collateral_output_txid collateral_output_index
# Example: mn1 127.0.0.2:46200 93HaYBVUCYjEMeeH1Y4sBGLALQZE1Yc1K64xiqgX37tGBDQL8Xg 2bcd3c84c84f87eaa86e4e56834c92927a07f9e18718810b92e0d0324456a67c 0

4.3.   Format your Null Array Information

NULL_ARRAY_ALIAS VPS_IP:PORT NA_GENKEY TX_ID TX_INDEX

(You can get the VPS_IP in step # 5)

4.4.   Paste your new Null Array information into NullArray.Conf on a new line.
4.5.   Save and close NullArray.conf





Step 5 – The Null Array Wallet

Setup your Windows Server VPS and load up the nullex-qt

(Follow your hosts procedures for this step)


Step 6 – The Null Array Wallet

Edit NulleX.conf on your VPS 

6.1.   NulleX.conf will be located in c:\Users\username\AppData\Roaming
6.2.   Open NulleX.conf with Notepad and enter the following information

rpcuser=YOUR_USER_NAME
rpcpassword=YOUR_PASSWORD
rpcallowip=127.0.0.1
listen=1
server=1
daemon=1
maxconnections=256
masternode=1
logtimestamps=1
nullarrayprivkey=NA_GENKEY
nullarrayaddr=VPS_IP:PORT
externalip=VPS_IP:PORT


Modify the above information:
Change YOUR_USER_NAME to a username
Change YOUR_PASSWORD to a secure random password
Replace VPS_IP with your VPS IP address
Replace NA_GENKEY with your Null Array Key from step 2.5.


6.3.   Save and close NulleX.conf
6.4.   Close and Restart your Null Array Wallet

Step 7 – Main Wallet

START YOUR NULL ARRAY !!

7.1.   Restart and unlock the main wallet
7.2.   Open the Debug Console
7.3.   Enter the following to start your Null Array (NULL_ARRAY_ALIAS step 2.7)

NullArray start-alias NULL_ARRAY_ALIAS


7.4.   You will see

	“alias” : “NULL_ARRAY_ALIAS”
	“result” : “successful”

(You may also start your Null Array from the Null Array MN Tab – This will be easier)

7.5.   You can use the following command to check the status of the Null Array in the Debug Console

NullArray status

7.6.  Keep your Main wallet and Null Array Wallet running

Step 8 – Enjoy the rewards.  Thank-You for supporting the NulleX Chain.

