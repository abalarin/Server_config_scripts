# Welcome to Automated Server Configuration Scripts!
This is a way to automate your server configuration

## Getting Started - ServerSetupAutomater`

Install expect mac: `brew install expect`

To start the automater run `ServerSetupAutomater.exp`

```
Usage: $./ServerSetupAutomater.exp <host> <ssh_user> <ssh_password> <config_script>

Example1: $./ServerSetupAutomater.exp 11.111.11.11

Example2: $./ServerSetupAutomater.exp 11.111.11.11 root password UbuntuConfig.sh`
```

### `ServerSetupAutomater.exp` is just a script loader

ServerSetupAutomater is not actually modifying any of your server configurations!

Its basically just allowing you to to start configuration from your local machine

* Line 12 - 58: Requests login credentials (if not already provided on command line)
* Line 60 - 95: Tests connectivity to host
* * If connection can't be established - exit script
* Line 101 - 118: Prompt for a `Server Config Script` (if not already provided on command line). You could use `UbuntuConfig.sh`
* Line 101 - 118: SCP `Server Config Script` to host
* Line 120 - 127: Prompt and SCP aliases if desired
* Line 133 - 157: SSH into host and run the `Server Config Script`

### Thats the whole script!

You could totally build off of this and add expects to automate your own bash scripts!

I tried to keep this as generic and simple to have as much flexibility as possible.

As it stands this only supports the loading of 1 setup script and 1 aliases file. Hopefully this can get updated in the future to load more setup scripts and increase error handling!