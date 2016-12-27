# Raspberry Pi 3 Bits

## Ping on the hour

Have a Pi on the Wifi but if it's not contacted for a while, it stops responding.
Have been told that maybe the Wifi goes into a low-power mode after inactivity. So
maybe if I just fabricate some activity once in a while, that won't happen.

0. copy 'ping-verizon-nameserver' into _/etc/cron.hourly/_
0. `sudo chown root:root /etc/cron.hourly/ping-verizon-nameserver`
0. `sudo chmod +x /etc/cron.hourly/ping-verizon-nameserver`

That last step is only needed if copying cleared the _execute_ bit.


