# Home-Assistant

These instructions are for setting up [Home Assistant OS](https://www.home-assistant.io/hassio/installation/) on a dedicated raspberry pi

## Installation
Download the release image that matches your specific raspberry pi from [here](https://github.com/home-assistant/operating-system/releases/)

Download and install [Balena Etcher](https://www.balena.io/etcher/).

Use Balena Etcher to flash the downloaded image to your SD card.

Insert the SD card into your raspberry pi, connect to ethernet, then connect power cord.

On first boot, it downloads the latest version of Home Assistant which takes around 20 minutes (slower/faster depending on the platform and your internet connection). 

You will be able to reach your installation at [http://homeassistant.local:8123](http://homeassistant.local:8123) if your router supports mDNS. If your router doesn’t support mDNS, then you’ll have to use the IP address of your Pi instead of homeassistant.local. For example, http://192.168.0.9:8123. You should be able to find the IP address of your Pi from the admin interface of your router.

## Updates

Be smart about updating the Home Assistant software. See recommended approach [here](https://www.home-assistant.io/hassio/installation/#updating-a-home-assistant-installation)

## Configuration

### Authentication

Setup user account

## Addons

Click Supervisor on the left sidebar

Click Add-On Store

Install the following addons
    - [Check Home Assistant configuration](http://homeassistant.local:8123/hassio/addon/core_check_config/info)
    - [Let's Encrypt](http://homeassistant.local:8123/hassio/addon/core_letsencrypt/info) (if exposing raspberry pi to external internet traffic)

Once installed, make sure to Start each of the addons (if required)

### Configure automatic backup

Given that you'll likely spend hours and hours over time configuring and tweaking your setup, this is the most critical thing to set up first.

I choose to go with [Hass.io Google Drive Backup](https://github.com/sabeechen/hassio-google-drive-backup)

First, add the repository as a source to install addons from. Click 3-dots menu at upper right, select Repositories, then add the following repository URL: https://github.com/sabeechen/hassio-google-drive-backup

Then, install the  Home Assistant Google Drive Backup addon from the addon store

Start the app and allow it to access Google Drive.

Finally, configure the backup settings to your liking.
