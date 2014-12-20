---
layout: default
title: Features
---

This project has following features, which don't exist in original `traccar-web` project:

* converted traccar-web to maven project to simplify builds
* following device
* printing device name
* recording device trace
* printing time stamps at device trace points (frequency is configured in Settings >> Preferences) both for archive and recorded trace
* translations to
    * russian language (available via ?locale=ru URL parameters)
    * german language (available via ?locale=de URL parameter)
    * italian language (available via ?locale=it URL parameter)
    * spanish language (available via ?locale=es URL parameter)
    * polish language (available via ?locale=pl URL parameter)
    * tagalog language (available via ?locale=tl URL parameter)
    * hungarian language (available via ?locale=hu URL parameter)
* 'show server log' menu for viewing tracker-server.log file on Web
* speed filtering in archive view
* change default map center position, zoom, provider (Google, OSM, Bing) (in Settings >> Preferences)
* replaced 'current state' panel with popups. They appear either when you hover a row in 'devices' table or when you hover a marker on map
* archive panel is collapsed by default. There is a button in upper right hand corner to expand it
* new 'managers' functionality:
* added new role to traccar - manager. Managers can add users and can manage access between devices of their users. So they have access to their devices and to devices of all managed users.
* administrators have full access to everything. They can manage all devices, all users and access between devices and users
* there is a new menu item called 'Share' to manage access to selected device
* improved performance of positions loading when DB grows up
* fixed issue when devices are not updated between different instances of web browser
* moved DB transaction management and user rights checks outside of data service implementation (AOP) with [google guice](https://github.com/google/guice)
* possibility to detect 'offline' devices - when signal hasn't came for some time (set up in device settings). They will be shown on a map with a marker of different colour and there will be some sign in popup that they are actually offline.
* new device status - idle. It is shown in popup and also there will be a time of idling. Each device got new setting 'Idle when speed is <=', which is zero by default. It may be changed to some reasonable value, which is then used to consider device idle (for example to handle 'satelite drift compansation').
* possibility to restrict ordinary users to manage (i.e. add/edit/delete) devices. Configured in global application settings.
* save sort order in devices grid into browser cookies
* mobile web UI based on [framework7](http://www.idangero.us/framework7/) with general functions for GPS tracking, available at `m/` URL, i.e. `http://server-ip:8082/m/`
* RESTful API. Available at `/traccar/rest/{methodName}` - allows to call methods from `DataService` class. Full documentation will be available by request.
* 'Address' column in archive (hidden by default)
* 'Distance' column in archive with total distance at the bottom
* possibility to export archive to [CSV](http://en.wikipedia.org/wiki/Comma-separated_values) and [GPX](http://en.wikipedia.org/wiki/GPS_Exchange_Format)
* possibility to import archive from [GPX](http://en.wikipedia.org/wiki/GPS_Exchange_Format)
* possibility to log in via GET request to a separate servlet (for example, for integration on external sites) - `http://server-ip:8082/traccar/s/login?user=your_username&password=your_password`
* possibility to change other user's password for administrators and managers
* possibility to change device marker