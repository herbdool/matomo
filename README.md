# Matomo Analytics

Adds the Matomo tracking system to your website.

[Matomo](https://matomo.org/) is an Open Source analytics tool to track
website traffic.

This module is compatible with Matomo 3.x, 4.x and 5.x.

## Requirements

* Matomo installation
* Matomo website account


## Installation

- Install this module using the official [Backdrop CMS instructions](https://backdropcms.org/guide/modules)

## Usage

In the settings page enter your Matomo website ID.

You will also need to define what user roles should be tracked.
Simply tick the roles you would like to monitor.

![Settings page](https://raw.githubusercontent.com/backdrop-contrib/matomo/1.x-2.x/screenshots/settings-page.webp)

All pages will then have the required JavaScript added to the
HTML footer can confirm this by viewing the page source from
your browser.

### HTTP URL vs. HTTPS URL

If your website has https turned on, it is necessary that the Matomo install
 *also has https turned on*. This prevents "mixed content" warnings in browsers.

It's absolutely OK and actually recommended that both url settings use https -
 if your Matomo install has it.
Browsers load content via https from within a http page, but refuse to load http
 content from within a https page.

Example:

- Matomo HTTP URL: `https://matomo.example.com/`
- Matomo HTTPS URL: `https://matomo.example.com/`

## Custom variables

One example for custom variables tracking is the "User roles" tracking. Enter
the below configuration data into the custom variables settings form under
admin/config/system/matomo.

Slot: 1
Name: User roles
Value: [current-user:matomo-role-names]
Scope: Visitor

Slot: 1
Name: User ids
Value: [current-user:matomo-role-ids]
Scope: Visitor

More details about custom variables can be found in the Matomo API documentation
at https://matomo.org/docs/javascript-tracking/#toc-custom-variables.


## Advanced Settings

You can include additional JavaScript snippets in the advanced
textarea. These can be found on various blog posts, or on the
official Matomo pages.

An example for "Code snippet (before)": `_paq.push(['disableCookies']);`
This disables all tracking cookies for Matomo (GDPR, to avoid the necessity of a
 cookie consent banner).

To speed up page loading you may also cache the matomo.js
file locally. You need to make sure the site file system is in public
download mode.

## Issues

Bugs and Feature requests should be reported in the [Issue Queue](https://github.com/backdrop-contrib/matomo/issues)

## Current Maintainers

- Joseph Flatt (https://github.com/hosef)
- indigoxela (https://github.com/indigoxela)

## Credits

- Ported to Backdrop CMS by Joseph Flatt (https://github.com/hosef).
- Maintained for Drupal by Alexander Hass (https://www.drupal.org/u/hass).
- Initial Drupal development by Alexander Hass (https://www.drupal.org/u/hass).

## License

This project is GPL v2 software. See the LICENSE.txt file in this directory for
complete text.
