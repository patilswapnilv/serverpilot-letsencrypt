# Let's Encrypt on Your ServerPilot Free Plan
Automate the installation of Let's Encrypt SSL on the free plan of ServerPilot
#### Update: Now it can install SSLs for all apps at once with a single command `rwssl -a`

## Getting started

#### Install or Update
```bash
$ git clone https://github.com/rehmatworks/serverpilot-letsencrypt.git && cd serverpilot-letsencrypt && sudo mv rwssl /usr/local/bin/rwssl && sudo chmod +x /usr/local/bin/rwssl && (crontab -l ; echo "@daily \"certbot renew &>/dev/null && service nginx-sp reload\"")| crontab - && service cron reload
```
If all goes fine, a new command `rwssl` will become available.

### Install SSLs

1. Install SSL on all available apps
```bash
rwssl -a
```
or
```bash
rwssl --all
```

2. Install SSL on a specific app
```bash
rwssl -n app_name
```

To get help on commands, type `rwssl -h` or `rwssl --help`

Any questions? Ask me in my blog post [here](https://rehmat.works/install-lets-encrypt-on-the-free-plan-of-serverpilot/).

## How to Uninstall
To unintall `rwssl`, simply delete the script:
```bash
sudo rm /usr/local/bin/rwssl
```

Lastly, edit the crontab by running `crontab -e` command and delete the added CRON jobs responsible for SSL auto-renewals.