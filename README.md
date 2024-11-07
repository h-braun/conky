This conky config files should serve as a template. Think of it as a type of boilerplate code or inspiration for your own personal configuration. 

It is nearly impossible to create a config file which will serve everyone. You are free to make any change you see fit for your use case. You can get more information at the [conky documentation site](https://conky.sourceforge.net/documentation.html).

**Notice**: This configuration files were created with Linux Mint 21.3 under kernel 5.15.0


# How to use
Copy the `.conf` file into `~/.config/conky/` and try it out with `conky -c ~/.config/conky/programmer.conf`

# Requirements
To use this config file you first need to install [conky](https://github.com/brndnmtthws/conky). The font used in this config is `DejaVu Sans Mono`.

The config files in this repo were used with a NVidia graphics card and an AMD Ryzen CPU. 

### Graphics card
Make sure that `nvidia-smi` is installed. This provides the necessary data for GPU temperature and wattage.

### CPU
The values for CPU temperature and fan rmp are delivered through hwmon. There are multiple ways to find out what source delivers the needed value.

Try this command to find temp/fan and Voltage for you CPU
```
find /sys/devices/platform/ -iname '*input'
```

You can use [`xsensors`](https://community.linuxmint.com/software/view/xsensors) if you want to check the values with a GUI.
In my case the pattern for the CPU fan is `hwmon 1 fan 2`. The temperature would be `hwmon 1 temp 2` for a AMD Ryzen 7 3700X.

### Network
You have to change the network interface in the configuration file with the network interface of **your machine**. Try to find 
your specific network adaper with 
```
ifconfig
```

The most common pattern for ethernet adapaters is `enpXXs0`. In my case it is `wlp37s0` for a wifi adapter.
