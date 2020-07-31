# Administrative Commands
The following is a reference sheet for command syntax for various validator administration tasks. Most commands listed here match the CosmosSDK implementation with Gaia, but note the binary name change from gaiad -> mtd and gaiacli -> mtcli.

# systemd
These systemd command assume that the validator is using a systemd service implementation. In a default installation this is not the case as the binaries are run directly from the command line (stdout).

## Start Service
`sudo systemctl start microtick`

## Stop Service 
`sudo systemctl stop microtick`

## Restart Service 
`sudo systemctl restart microtick`

## Enable Service at boot
`sudo systemctl enable microtick`

## Disable Service at boot
`sudo systemctl disable microtick`

# Logs
These commands reference logs and status assuming one is using a systemd or similar logging mechanism. In a default installation this information is piped to stdout on the console. It is recommended in these instances that a `screen` session be utilized for keep alive and better console log scroll buffer purposes.  
## systemd
`sudo systemctl status microtick`
`journalctl -u microtick -f`

# Validator
These commands are specific to the Microtick binary distribution. While the functions may match those in CosmosSDK and Gaia, the binary name will be different. 

## Display validator key
`mtcli keys show (keyname) -a`
example:  `mtcli keys show validator -a`

## Query bank balances
`mtcli query bank balances (microaddress) --chain-id microtickzone-a1`
Please note that chain-id is not explicitly required if this is set in the Microtick configuration files. 

## Query outstanding rewards
`mtcli query distribution rewards (microaddress)  --chain-id microtickzone-a1`
Please note that chain-id is not explicitly required if this is set in the Microtick configuration files. 

## Claim outstanding rewards
`mtcli tx distribution withdraw-rewards (microvaloperaddress) --from (microaddress) --chain-id microtickzone-a1 --commission`
Please note that chain-id is not explicitly required if this is set in the Microtick configuration files. 

## Delegate from bank
` mtcli tx staking delegate (microvaloperaddress) 1000000utick --from (microaddress) --chain-id microtickzone-a1`
Please note that chain-id is not explicitly required if this is set in the Microtick configuration files. 
