# Github Dwains Dashboard Add-on (more_page)
Github monitoring in Home Assistant Dwains Dashboard.
Shows issues, pull requests, and more from your github repositories
##### Created by [Léon van der Linden](https://github.com/LRvdLinden)
##### v1.0.0

![github](https://cryptonavia-showcase-production-media.s3.amazonaws.com/media/images/github-logo-770x515.original.width-1000.jpg)

## Prerequisite
---
- Make sure you have installed the lovelace [github-card](https://github.com/ljmerza/github-card). This can be done manually or directly via hacs

## Make Home Assistant integration 
---
- Make the integration with [Github in Home Assistant](https://www.home-assistant.io/integrations/github/)
- Restart Home Assistant
 ```yaml
     # Example configuration.yaml entry
     sensor:
       - platform: github
         access_token: !secret github_access_token
         repositories:
           - path: 'home-assistant/core'
```
- Restart Home Assistant

## Installation Add-on
---
- Copy the `github` folder in to the `dwains-dashboard/addons/more_page` directory.
- Open your `more_page.yaml` file in `dwains-dashboard/configs` and add the following;
 ```yaml
     - name: Github
       main_menu: 'true' #Show this addon in the main navigation bar!
       icon: mdi:github
       path: 'dwains-dashboard/addons/more_page/github/page.yaml'
```
- Reload the theme configuration via Theme Settings

## Replace the following
---
 ```yaml
   cards:
     - title: Github
       show_extended: true
       show_github_icon: true
       type: 'custom:github-card'
       entities:
         - sensor.path
         - sensor.path    
```
- add the correct `sensor` to monitor


## Options
---
| Name | Type | Requirement | `Default` Description
| :---- | :---- | :------- | :----------- |
| title | string | **Optional** | `Github` Change card title
| entities | list | **Required** | List of github sensors to display
| show_extended | boolean | **Optional** | `true` Show/hide tags, forks, and commits links
| show_github_icon | boolean | **Optional** | `true` Show/hide Github icon


## Result
---
![uptimerobot](https://)
