# clusterXL_monitor_arp

The **clusterXL_monitor_ips** script can be used to arping a list of predefined IP addresses and change the state of the cluster member to *Down* or *Up* based on the replies to these pings.

This shell script registers a pnote (called arp_monitor) and gracefully changes the state of the given cluster member to *Down* (by reporting the state of that pnote as *problem*), or gracefully reverts the state of the given cluster member to *Up* (by reporting the state of that pnote as *ok*).

The **clusterXL_monitor_arp** script should be located in **$FWDIR/bin/** directory on your cluster members (same as clusterXL_monitor_ips).

Configuration is located in **$FWDIR/conf/cpha_arp_hosts**. Configuration format is ```<ip> <interface>``` on separate line for each monitored host. File must not contain anything else.

Cluster member will go down even if one ping is not answered.

**Important** - You must do these changes on all cluster members.
