---
layout: page
title: "Updater"
description: "Details what the updater component is reporting about your Home Assistant instance."
date: 2016-10-22 08:00
sidebar: false
comments: false
sharing: true
footer: true
---

Starting with 0.31 the [updater component](/components/updater/) sends an optional report about Home Assistant instance.

We are only collecting this information to better understand our user base to provide better long term support and feature development.

| Name                  | Description                                | Example                            | Data Source    |
|-----------------------|--------------------------------------------|------------------------------------|----------------|
| `arch`                | CPU Architecture                           | `x86_64`                           | Local Instance |
| `distribution`        | Linux Distribution name (only Linux)       | `Ubuntu`                           | Local Instance |
| `docker`              | True if running inside Docker              | `false`                            | Local Instance |
| `first_seen_datetime` | First time instance ID was submitted       | `2016-10-22T19:56:03.542Z`         | Update Server  |
| `geo_city`            | GeoIP determined city                      | `Oakland`                          | Update Server  |
| `geo_country_code`    | GeoIP determined country code              | `US`                               | Update Server  |
| `geo_country_name`    | GeoIP determined country name              | `United States`                    | Update Server  |
| `geo_latitude`        | GeoIP determined latitude                  | `37.8047`                          | Update Server  |
| `geo_longitude`       | GeoIP determined longitude                 | `-122.2124`                        | Update Server  |
| `geo_metro_code`      | GeoIP determined metro code                | `807`                              | Update Server  |
| `geo_region_code`     | GeoIP determined region code               | `CA`                               | Update Server  |
| `geo_region_name`     | GeoIP determined region name               | `California`                       | Update Server  |
| `geo_time_zone`       | GeoIP determined time zone                 | `America/Los_Angeles`              | Update Server  |
| `geo_zip_code`        | GeoIP determined zip code                  | `94602`                            | Update Server  |
| `last_seen_datetime`  | Most recent time instance ID was submitted | `2016-10-22T19:56:03.542Z`         | Update Server  |
| `os_name`             | Operating system name                      | `Darwin`                           | Local Instance |
| `os_version`          | Operating system version                   | `10.12`                            | Local Instance |
| `python_version`      | Python version                             | `3.5.2`                            | Local Instance |
| `timezone`            | Timezone                                   | `America/Los_Angeles`              | Local Instance |
| `user_agent`          | User agent used to submit analytics        | `python-requests/2.11.1`           | Local Instance |
| `uuid`                | Unique identifier                          | `10321ee6094d4a2ebb5ed55c675d5f5e` | Local Instance |
| `version`             | Home Assistant version                     | `0.31.0`                           | Local Instance |
| `virtualenv`          | True if running inside virtualenv          | `true`                             | Local Instance |

In addition to the above collected data, the server will also use your IP address to do a geographic IP address lookup to determine a general geographic area that your address is located in. To be extremely, extremely clear about this bit: __The Home Assistant updater does not: store your IP address in a database and also does not submit the location information from your `configuration.yaml`.__

Our tests showed that at best, we get 4 digits of accuracy on your IP address location which is a 5 mile radius of your actual IP location, assuming that it is even correct in the first place (geo IP lookups are very hit or miss).

The server also adds two timestamps to the data:

- the original date your instance UUID was first seen
- the timestamp of the last time we have seen your instance

There are currently no plans to publicly expose any of this information. If we did do such a thing in the future we would of course notify you in advance. It must also be stated that we will never sell or allow the use of this information for non-Home Assistant purposes.
