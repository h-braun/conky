These Conky configuration files are designed to serve as a template. A starting point or inspiration for creating your own personalized configuration.

It’s challenging to create a one-size-fits-all configuration that meets everyone’s needs, so feel free to modify anything to suit your own setup. You can find additional information in the Conky documentation.

**Note:** These configuration files were created using Linux Mint 21.3 with kernel 5.15.0.


# How to use
Copy the `.conf` file into `~/.config/conky/` and test it by running:
```
conky -c ~/.config/conky/programmer.conf
```

# Requirements
To use this configuration file, you’ll need to install [conky](https://github.com/brndnmtthws/conky). This config also requires the font `DejaVu Sans Mono`.

The configurations in this repository were tested with an NVIDIA graphics card and an AMD Ryzen CPU.

### Graphics card

#### NVidia
Ensure `nvidia-smi is` installed to provide GPU temperature and wattage data.


Currently, I have not tested this with an AMD graphics card.

### CPU
CPU temperature and fan speed are sourced from `hwmon`. There are multiple ways to find which source provides these values.

Run the following command to locate temperature, fan speed, and voltage data for your CPU:
```
find /sys/devices/platform/ -iname '*input'
```

You can also use [`xsensors`](https://community.linuxmint.com/software/view/xsensors) to check these values through a GUI. 
For example, with an AMD Ryzen 7 3700X, the CPU fan might be labeled as `hwmon 1 fan 2` and temperature as `hwmon 1 temp 2`.

### Network
Update the network interface in the configuration file to match your system’s network adapter. To identify your specific network adapter, use:
```
ifconfig
```

Ethernet adapters typically follow the pattern `enpXXs0`. In this example, `wlp37s0` is used for a Wi-Fi adapter.
