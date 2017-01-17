# Networks-Mininet

* [Install Mininet VM image](http://mininet.org/download/)
* Install virtualbox - `sudo apt-get install virtualbox`

 Alternatively, search for `mininet_networks` on DC++. Username - `temporary_username` . Contains both required files. Downloading Mininet VM may consume upto 98% of your CPU, so personal advice not to download on Windows (because Windows is shit.)

[Mininet on GitHub](https://github.com/mininet/mininet/wiki/FAQ).

# Syntax and Execution

Run virtualbox with - `$ virtualbox` on your terminal.
Once inside virtualbox, browse to `File > Execution`. Search for mininet. Some settings need to be altered first.

* `Virtualbox > File > Network > host-only network >` select vboxnet0
* `.. Network > Adapter 1 >` Attached to NAT (selected by default).
* `.. Network > Adapter 2 > Attached to > host-only adapter name` > vboxnet0

Once your mininet OS is installed, a terminal fires up. Login credentials - user : mininet, password : mininet

<pre style="background: rgb(238, 238, 238); border: 1px solid rgb(204, 204, 204); padding: 5px 10px;">$ sudo mn # start mininet # this is in virtualbox
mininet > nodes # show available nodes
mininet > dump # dump node info
mininet > ifconfig # available physical interfaces connected to device
mininet > # switch through multiple terminals (tty) with Alt + left/right arrow keys
mininet > h1 ping h2 # ping from one host to other
mininet > h1 cmd # to execute command cmd on host1
mininet > iperf # TCP bandwidth check
mininet > exit # exit mininet process</pre>


Now in original OS, execute these commands in a terminal **May be Incomplete**.
<pre style="background: rgb(238, 238, 238); border: 1px solid rgb(204, 204, 204); padding: 5px 10px;">$ ssh - X mininet@IP_ADDR # IP_ADDR obtained from ifconfig eth0 in mininet (192.168.56.101)
$ xterm h1 # get into h1
$ ping h2_IP # in xterm (h2_IP = 10.0.0.2)

$ sudo mn -c # kill all mininet processes # in virtualOS
(original OS) > mininet > iperf
(original OS) > mininet > sudo mn --link tx,bw=1000

$ ssh -X mininet@192.168.56.101 #(original OS)(another ssh instance)
(original OS) > mininet > sudo wireshark &
</pre>

Finally, in the wireshark launchable, `Interface List > eth0 > start`


If you feel this is incomplete and you have the missing, send a PR.
