<h1 align="center">Github Dwains Dashboard Add-on (more_page)</h1>

<p align="center">
  <a href="https://dwainscheeren.github.io/dwains-lovelace-dashboard/">
    <img src="https://img.shields.io/badge/Dwains%20Dashboard-Default-299ec2.svg" />
  </a>
  <a href="https://github.com/custom-components/hacs">
    <img src="https://img.shields.io/badge/HACS-Default-orange.svg" />
  </a>
  <a href="https://github.com/LRvdLinden/github_dd_addon">
    <img src="https://img.shields.io/github/v/release/LRvdLinden/github_dd_addon" />
  </a>
      <a href="https://github.com/LRvdLinden/github_dd_addon">
    <img src="https://img.shields.io/github/downloads/LRvdLinden/github_dd_addon/latest/total?color=purple&label=%20release%20Downloads" />
  </a>
    <a href="https://github.com/LRvdLinden/">
    <img src="https://img.shields.io/github/followers/LRvdLinden?style=social" />
  </a>
    </a>
    <a href="https://discord.gg/7yt64uX">
    <img src="https://img.shields.io/discord/688401603811999885" />
  </a>
</p>
<p align="center">Github monitoring in Home Assistant Dwains Dashboard.
Shows issues, pull requests, and more from your github repositories</p>


<p align="center">Created by <a href="https://github.com/LRvdLinden">Léon van der Linden</a> based on <a href="https://github.com/LRvdLinden/github-flexi-card">github-flexi-card</a> created by <a href="https://github.com/maxwroc">Maxwroc</a>
</p> 


<p align="center">
  <img src="https://cryptonavia-showcase-production-media.s3.amazonaws.com/media/images/github-logo-770x515.original.width-1000.jpg" />
</p>



## Prerequisite
---
- Make sure you have installed the lovelace [github-flexi-card](https://github.com/LRvdLinden/github-flexi-card). This can be done manually or directly via hacs

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
           - path: 'LRvdLinden/automations_dd_addon' #path Github URL
             name: Automations Dashboard Dwains Add-on #custom name sensor
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
     - type: 'custom:github-flexi-card'
       title: Github LRvdLinden
       secondary_info: '{latest_release_tag}'
       url: true
       attribute_urls: true
       attributes:
         - views
         - stargazers
         - open_issues
         - clones
         - forks
         - open_pull_requests
      sort:
        - by: stargazers
        - by: views_unique
          ascending: true
      entities:
        - sensor.automations_dashboard_dwains_add_on
        - sensor.birthday_dwains_add_on
        - sensor.github_dwains_add_on
        - sensor.uptimerobot_dwains_add_on
        - sensor.uptimerobot_lovelace_card
```
- add the correct `sensor` to monitor


## Options
---

![image](https://user-images.githubusercontent.com/8268674/97019224-fad42300-1547-11eb-8153-46c401f50455.png)

### Entity
| Name | Type | Default | Since | Description |
|:-----|:-----|:-----|:-----|:-----|
| entity | string | **(required)** | v0.1.0 | Entity ID e.g. `sensor.my_github_project`


### Entity Properties
| Name | Type | Default | Since | Description |
|:-----|:-----|:-----|:-----|:-----|
| name | [KString](#keywordstring) | `friendly_name` | v0.1.0 | Name override
| secondary_info | [KString](#keywordstring) |  | v0.1.0 | String to display underneath the entity name
| attributes | list([Attribute](#attribute)) |  | v0.1.0 | Attributes to display
| url | [KString](#keywordstring) \| bool |  | v0.2.0 | Url to open on click/tap. (when `true` is used the target url becomes repo homepage)
| attribute_urls | bool |  | v0.2.0 | When set to `true` turns on default urls for all the displayed attributes
| icon | string | `"mdi:github"` | v0.2.0 | Override for entity icon
| compact_view | bool | `true` | v1.0.0 | When set to `false` big icons (and values) are displayed

### Attribute
| Name | Type | Default | Since | Description |
|:-----|:-----|:-----|:-----|:-----|
| name | string | **(required)** | v0.1.0 | Name of the attribute
| icon | string |  | v0.1.0 | Icon override (there are default icons for most of the available attributes)
| url | [KString](#keywordstring) \| bool |  | v0.2.0 | Url to open on click/tap. (there are default urls for most of the available attributes, so you can just use `true`)
| label | [KString](#keywordstring) |  | v0.5.0 | Label/text which will be shown instead of the icon

### Sort options

| Name | Type | Default | Since | Description |
|:-----|:-----|:-----|:-----|:-----|
| by | string | **(required)** | v1.0.0 | Name of the attribute
| ascending | bool | `false` | v1.0.0 | Whether to sort ascending or descending

## Result
---
![voorbeeld github](https://user-images.githubusercontent.com/77990847/114712144-0c94c700-9d30-11eb-8737-23c7891f5b56.png)


---
Enjoy my card? Help me out for a couple of :beers: or a :coffee:!

[![coffee](https://www.buymeacoffee.com/assets/img/custom_images/black_img.png)](https://www.buymeacoffee.com/LRvdLinden)
