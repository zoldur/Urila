# Urila Coin
Shell script to install a [Urila Coin Masternode](https://urila.network/) on a Linux server running Ubuntu 16.04.
***

## VPS installation
```
wget -N https://raw.githubusercontent.com/zoldur/Urila/master/urila_install.sh
bash urila_install.sh
```
***

## Desktop wallet setup

After the Masternode is up and running, you need to configure the desktop wallet accordingly. Here are the steps:
1. Open the Urila Desktop Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **4500** URA to **MN1**. You need to send all 4500 coins in one single transaction.  **This is a tiered Masternode so the collateral will change**
4. Wait for 15 confirmations.
5. Go to **Help -> "Debug Window - Console"**
6. Type the following command: **masternode outputs**
7. Go to  **Tools -> "Open Masternode Configuration File"**
8. Add the following entry:
```
Alias Address Privkey TxHash TxIndex
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* TxIndex:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
12. Select your MN and click **Start Alias** to start it.
13. Alternatively, open **Debug Console** and type:
```
startmasternode alias 0 MN1
```
14. Login to your VPS and check your masternode status by running the following command to confirm your MN is running:
```
urila-cli masternode status
```
***

## Usage:
```
urila-cli masternode status #To check your MN status
urila-cli getinfo #To get general info such as Urila version and current block numnber
urila-cli mnsync status #To check if your MN is synced.
```
Also, if you want to check/start/stop **Urila**, run one of the following commands as **root**:

```
systemctl status Urila #To check if Urila service is running
systemctl start Urila #To start Urila service
systemctl stop Urila #To stop Urila service
systemctl is-enabled Urila #To check if Urila service is enabled on boot
```
***

## Donations
Any donation is highly appreciated

**BTC**: 3MQLEcHXVvxpmwbB811qiC1c6g21ZKa7Jh
**ETH**: 0x26B9dDa0616FE0759273D651e77Fe7dd7751E01E
**LTC**: LNZpK4rCd1JVSB3rGKTAnTkudV9So9zexB
