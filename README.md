# Avalanche HYPERSDK PROJECT

This project uses HyperSDK that provides the ability to create a custom virtual machine, which offers complete control over a custom blockchain. By using the HyperSDK, we have full control over the rules and functionality of your chain, allowing us to create a custom blockchain that is tailored to your startup's specific needs. 


## Description 
```consts/consts.go``` contains the constants that is accessible across the hyperVM. The HRP, Name, and Symbol constants define information about the TokenVM, including its Human-Readable Part (HRP), name, and symbol.

```registry/registry.go``` contains the action that will be performed in the terminal during interaction.

## Steps of Execution
This project is execute on WSl on windows and GO installed inside wsl.<br>
1) In terminal run command ```MODE="run-single" ./scripts/run.sh``` and this will start our machine with 1 subnet. after this command output will look like.
```javascript
Ran 4 of 4 Specs in 81.284 seconds
PASS
cluster is ready!
avalanche-network-runner is running in the background... 

use the following command to terminate:

killall avalanche-network-runner
```
2) To start interaction run ```./scripts/build.sh```. output will be :
```javascript
/scripts/build.sh
Building tokenvm in ./build/tHBYNu8ikqo4MWMHehC9iKB9mR5tB3DWzbkYmTfe9buWQ5GZ8
Building token-cli in ./build/token-cli
```
This command will put the compiled CLI in ./build/token-cli.
<b>NOTE- default address is ```token1rvzhmceq997zntgvravfagsks6w0ryud3rylh4cdvayry0dl97nsjzf3yp```</b>

3) Lastly, we'll need to add the chains we created and the default key to the token-cli. run command:
```javascript
./build/token-cli key import demo.pk
./build/token-cli chain import-anr
```
chain import-anr connects to the Avalanche Network Runner server running in the background and pulls the URIs of all nodes tracking each chain you created..

## Creation and Minting process
### Step 1 Asset Creation
To create an assest run the command:
```javascript
./build/token-cli action create-asset
```
Enter the metadata (eg:GoCoin) and confirm
output looks like:
```javascript
database: .token-cli
address: token1rvzhmceq997zntgvravfagsks6w0ryud3rylh4cdvayry0dl97nsjzf3yp
chainID: 2vCjHv1ws8YirjkcjsaVotLhCeownJDVBhUJgtBpu6j9ucupgf
metadata (can be changed later): GoCoin
continue (y/n): y
✅ txID: 2jce33uBTSa3yKrv7KngEdbwtyN4NBXfhGmx4Xtb6p6nPjtb9w
```
<b>NOTE - txID is the assetID of your new asset.</b>

### Step 2 Minting of asset
To mint the created assest run command:
```javascript
./build/token-cli action mint-asset
```


