# Rebooting your devices with IoT Edge

# Standard method
** This method perform an unsafe reboot of the system by using magic sysreq keys **
It has been tested on Ubuntu and Raspbian but should work for other linux distributions. Dockerfile is hosted on the same repo, to run it you can deploy on IoT Edge:

1. Deploy image `mandrx/reboot:1.0.1`  
2. Give the container privileged rights, under create options :
``` json
{
    "HostConfig": {
        "Privileged": true
    }
}
```
3. Select the restart policy 'never' or your device will keep restarting.