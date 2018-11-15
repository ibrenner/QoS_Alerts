# QoS_Alerts
Alerting on volumes that are near QoS limits
The user sets a threshold for alert and warning, and upon execution the script samples from infinimetrics all the volumes that are assigned to a QoS policy. If the amount of IOPS for any of the volumes is reaching one of the thresholds it will create an event in the infinibox.
If a QoS policy has burst factor enabled, the limit is being being adjusted and checked accordingly.

# qos_imx_alert
## Prerequisites
this script uses python 3

## Authentication
Please make sure to create a credentials file for the relevant ibox and infinimetrics sserver you want the script to manage. the file contents should be as follows:
```
ibox ibox1
user adminuser
password MTIzNDU2
infinimetrics infinimetrics.local
warning 0.8
alert 0.9
```
password value should be encrypted using base64

## Usage

```
usage: qos_imx_alert.py [-h] -c CREDFILE

Script for managing snap groups.

optional arguments:
  -h, --help            show this help message and exit
  -c CREDFILE, --credfile CREDFILE
                        Credentials file name
```
## Example
```
python qos_imx_alert.py -c .testing.sec
```


example alert on infinibox:
![alt text](
        https://raw.githubusercontent.com/ibrenner/QoS_Alerts/master/Screen%20Shot%202018-11-15%20at%2014.35.47.jpg
       "alert")
