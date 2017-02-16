[![Say Thanks](https://img.shields.io/badge/Say%20Thanks-!-1EAEDB.svg?style=flat)](https://saythanks.io/to/deadbits) [![Donate](https://img.shields.io/badge/donate-BTC-blue.svg?style=flat)](https://www.coinbase.com/deadbits)

# Palioxis - Linux "kill-switch" utility
Palioxis was the Greek personification of the backrush or retreat from battle. It seems fitting in the scenarios that would surround the needed use of this script.

## Disclaimer
* This script does **not** negate all potential threats and the use of it in your geographical location may be illegal depending on the circumstances of it's use. Please refer to your local laws before using this script.
* Do not use this as a serious application or means of privacy/security. Palioxis is **not** production ready and there is the potential for data loss, security flaws, and other unknown issues. 
* **Do not operate while under the influence of drugs or alcohol. You might lose data and stuff.**
 
## Documentation 
### Running in 'Server' mode:
**usage:** `./palioxis.py --mode server --host 127.0.0.1 --port 44524 --key OHSNAP`

This will start Palioxis as a server, meaning it will listen on the given host and port for the 'destroy key'. Once received, it will proceed to shred the specified files and truecrypt drives.
  
Once the server starts, it will run in the background as a daemon process until you either reboot or kill the process.

Note: **It's good idea to run the Palioxis server as system service**

### Running in 'Client' mode:
**usage:** `./palioxis.py --mode client --list /etc/palioxis/nodes.txt`
  
This will start Palioxis as the master client. It will read server hosts from the file specified with the --list argument and attempt to send the kill signal to each of these hosts that are running another Palioxis instance. 
 
#### Example server list file:
This is an example of the `nodes.txt` file from the usage case above:

```
192.168.56.102 44524 OHSNAP
192.168.56.104 44524 FREEDOM
192.168.56.105 44524 L33T
```

