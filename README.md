# Raspberry Pi 3 Odds and Ends

## Ping on the hour

You have a Pi on the Wifi but if it's not contacted for a while, it stops responding.
You have been told that maybe the Wifi goes into a low-power mode after inactivity. So
maybe if you just synthesize some activity once in a while, that won't happen.

### install

0. `sudo cp ./ping-verizon-nameserver /etc/cron.hourly/`
0. `sudo chown root:root /etc/cron.hourly/ping-verizon-nameserver`
0. `sudo chmod +x /etc/cron.hourly/ping-verizon-nameserver`

### operation

None. Any executable script you put into _/etc/cron.hourly/_ executes
once per hour.  That script just tries to reach out and touch a server.
It doesn't even have to succeed, really. Just the act of trying to use
the network should prevent the Wifi from turning off.

### thoughts

I'm not actually sure if 1 hour is the right period. Maybe it goes off
sooner than that. Time will tell (heh).

Also, maybe it's not such a good idea to keep the power high. If you are
on a battery, that sounds like a bad idea. The use case for this is to
keep the Pi available to outside-initiated connections. If you don't need
that, then you probably don't need this solution.
