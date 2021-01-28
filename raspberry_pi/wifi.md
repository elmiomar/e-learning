## Configure WIFI on Raspberry Pi

### Using raspi-config tool:

The easiest way to enable wireless networking on your RPi is to use the command line tool `raspi-config`.

```
sudo raspi-config
```

Select the **Localisation Options** from the menu, then **Change wireless country** option. Set the SSID and password of the network, and you are good to go.

### Using wpa-supplicant:

Open the `wpa-supplicant` configuration file with a text editor:

```
sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
```

Change the following to match your network settings:

```
network={
    ssid="wifi_ssid"
    psk="wifi_password"
}
```

To scan for the available wireless networks, use the command `sudo iwlist wlan0 scan`.

Restart the networking service or reboot the RPi.
