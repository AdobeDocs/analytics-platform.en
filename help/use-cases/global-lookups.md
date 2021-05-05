---
title: Add global lookups to your datasets
description: Use global lookups to augment reporting with useful dimensions in Customer Journey Analytics.
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
---
# Add global lookups to your datasets

Global lookups enhance the ability of Customer Journey Analytics to report on some dimensions/attributes that are not useful by themselves but are useful when joined with other data. Examples include attributes of mobile devices, and attributes of OS and Browser dimensions, such as browser version numbers. A 'Global Lookup' is very similar to a lookup data set (known as classifications in traditional Adobe Analytics). However, global lookups are applicable across Experience Cloud organizations. Global lookups are automatically applied to all event datasets that contain certain XDM schema fields (see below for the specific fields.)
For each schema location that Adobe is classifying, a global lookup dataset exists. You can use global lookup datasets with the Analytics Source Connector or with other custom datasets that can accept them.

In traditional Adobe Analytics, these dimensions show up on their own, whereas in CJA, you have to actively include these dimensions when you create data views. In the Connections workflow, you select a dataset that is flagged as one with a key for global lookup. The Data Views UI automatically knows to include all the global lookup dimensions as available for reporting. The lookup files are automatically kept up to date and available, across all regions and for all accounts. They are stored in region-specific organizations associated with the customer.

## Available global lookup fields

* `browser`
   * `browser`, `group_id`, `id`
* `browser_group`
   * `browser_group`, `id`
* `os`
   * `os`, `group_id`, `id`
* `os_group`
   * `os_group`, `id`
* `mobile_audio_support - multi`
* `mobile_color_depth`
* `mobile_cookie_support`
* `mobile_device_name`
* `mobile_device_number_transmit`
* `mobile_device_type`
* `mobile_drm - multi`
* `mobile_image_support - multi`
* `mobile_information_services`
* `mobile_java_vm - multi`
* `mobile_mail_decoration`
* `mobile_manufacturer`
* `mobile_max_bookmark_url_length`
* `mobile_max_browser_url_length`
* `mobile_max_mail_url_length`
* `mobile_net_protocols - multi`
* `mobile_os`
* `mobile_push_to_talk`
* `mobile_screen_height`
* `mobile_screen_size`
* `mobile_screen_width`
* `mobile_video_support - multi`

## Report on global lookup dimensions

In order to report on the global lookup dimensions, you have to add them when you create a data view in Customer Journey Analytics:

![](assets/global-lookup.png)

You can then see the lookup data in Workspace:

![](assets/gl-reporting.png)
