# About

This is a PHP CLI to enable/disable pfSense gateways. It was inspired by [this Netgate forum post](https://forum.netgate.com/topic/198960/wireguard-service-fails-to-start-after-reboot-across-all-our-netgate-devices/17).

The script uses native methods of updating the firewall's configuration, so the changes are persistent, and reflected in the GUI.

# How to use

1. Download `gwctl` to your firewall (`/root` or `/root/bin` are sensible locations)
2. Make it executable (`chmod +x gwctl`)
3. Run the script (it will output help if run with no args or with `-h`, `--help`)

# Help

```
Usage: gwctl <gateway> <action> [--force]
  <gateway>  can be index# or name
  <action>   one of: enable, disable
  --force    apply action even if gateway is already in desired state

  configured gateways:
    [0] WAN1 - 1.2.3.4 (ix0)
    [1] WAN2 - 5.6.7.8 (ix1)
    [2] WG0 - 172.16.40.201 (tun_wg0)
    [3] WAN6_TUNNELV6 - 2001:dead:beef::1 (gif0)
```
# Examples

Enable the `WAN1` gateway:

```
/root/gwctl WAN1 enable
```

Disable the `WG0` gateway:

```
/root/gwctl 2 disable
```
