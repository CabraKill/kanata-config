## Stopping Kanata Manually

To kill the running Kanata process:

```
sudo pkill kanata
```

This will terminate all running Kanata processes.
## Kanata macOS Launchctl Management

### Enable Kanata Auto-Start (system-wide)

```
sudo launchctl bootstrap system /Library/LaunchDaemons/com.example.kanata.plist
sudo launchctl enable system/com.example.kanata.plist
```

Kanata will start automatically on reboot.

### Disable Kanata Auto-Start (system-wide)

```
sudo launchctl disable system/com.example.kanata.plist
```

This will prevent Kanata from starting automatically on reboot.

### Manually Start Kanata (even if auto-start is off)

```
sudo launchctl start com.example.kanata
```

This will start Kanata immediately, regardless of the auto-start setting.
# Kanata Configurations

This repository contains configuration files for Kanata, a keyboard remapping tool.

## run

```bash
sudo kanata -c kanata.kbd
```

## kill scenarios

```bash
pgrep kanata

sudo kill 511

```

## Troubleshooting

### Mouse issues

For some reason, both kanata and karabiner had issue with my bluetooth mouse from keychron.
To fix both I had to:
* Mark the device as ignored on the main config for karabiner
* add the device to the exclude list of devices on the kanata file

### Installation

The 'main' installation didn't work from kanata suggested link.
What truly did work was follow the order bellow of the links and only do the truly necessary remaining step that were not covered on the first link

* https://github.com/jtroo/kanata/issues/1264#issuecomment-2763085239
* https://github.com/jtroo/kanata/discussions/1537

### Fn keys

Right the fn keys are not working even thought they are not declared.
Redeclaring it may fix it but not done yet.

Issue with some examples:
* https://github.com/jtroo/kanata/issues/1311

### Documentation

* [Typeractive base 5 columnar layout](https://docs.typeractive.xyz/build-guides/corne-wireless/firmware)
* [General kanata key documentation](https://github.com/jtroo/kanata/blob/main/docs/config.adoc)
* [Kanata key definitions source code](https://github.com/jtroo/kanata/blob/main/parser/src/keys/mod.rs)
