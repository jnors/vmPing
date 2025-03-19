vmPing
======

vmPing (Visual Multi Ping) is a graphical ping utility for monitoring multiple hosts.  Numerous host monitors can be added and removed, and each monitor dynamically resizes with the application window.  Color-coding allows you to tell at a glance the status of each host.  In addition to standard ICMP pings, you can also perform a TCP 'port ping', where the application continuously connects to a specified port and displays whether or not the port is open.  A fast trace route utility and a basic packet generator / stress tester is also included. This is based on Ryan Smith work and I do not take any credit for everything done before 1.3.23.1.

**Downlad the latest release from the .exe on the Repo**
##### (1.3.23.2 released on March 19, 2025)

##### Notes
* There is no installer.  Just run the .exe.
* .NET 4.8 or greater is required.


Screenshots
-----------
##### Main Window
![Main Window](screenshots/vmPing-MainWindow02.png "Main Window")

##### Options
![Options Window](screenshots/vmPing-Options.gif)

##### Popup Notification
![Popup Notification](screenshots/vmPing-PopupNotification.gif)


Recent Changes
--------------
### Version 1.3.23.2
* Updated Ping Timeout to support millisecond intervals
* Updated Ping Timeout validation logic to compare against Roundtrip time

### Version 1.3.23.1
* Updated the application to use .NET Framework 4.8
* Added support for sub-second pings

### Version 1.3.23
* Fix: Force software rendering. This should fix high GPU usage on some video cards.
* Fix: Loading a favorite on startup was not using the column count for the favorite.
* Fix: Scroll indicator icon would unnecessarily display when the window was resized to small dimensions.
* The position and size of the status history window is now remembered rather than resetting each time it's opened.
* Switch to using SnapToDevicePixels on the main window. Previously, the pixel width for the black borders between probes would sometimes vary when the window was resized. The borders should now always be consistent.
* Removed gaps when hovering mouse between menu buttons (Add Host, Columns, Start/Stop All). Removed gap from right edge of main menu button.
* Some of the menu headers have been renamed on the options screen.



### Version 1.3.21
* If you scroll up in a ping window, automatic scrolling pauses. Automatic scrolling resumes when you scroll back to the bottom. While scrolled up, a small visual indicator appears in the bottom right corner of the ping window.
* Added _always on top_ option. This feature existed in early versions, and now it's back. Found under Options -> Display.
* Added _minimize to tray_ and _exit to tray_ options. Found under Options -> Display. At the moment, the tray icon doesn't do anything to indicate status. It's just a plain icon.
* When logging status changes to a text file, aliases are now included.
* Lots of minor visual changes:
  - On status change alerts, the text for _DOWN_ and _UP_ is now all lowercase _down_ and _up_.
  - On popup alerts, an arrow symbol replaces the word "is". For example _127.0.0.1 is down_ becomes _127.0.0.1 🠖 down_
  - All references to Popup Notifications have been renamed to Popup Alerts (to be consistent with email alerts and audio alerts).
  - Custom styling on the main dropdown menu. Added icons to most menu items.
  - Minor style changes and icons added to the alias and favorites windows.


### Version 1.3.19
* The _Status History_ window now has the ability to export. When exporting, you have three delimiter options: comma (CSV), tab, or space.
* The _Status History_ window has a new, cleaner look with a custom window border.
* Added a _clear_ button to the filter box on the _Status History_ window.
* Auto-scrolling now pauses while clicking (and holding) the scrollbar within each probe window. The ability to completely toggle auto-scrolling is planned.
* Various minor visual style updates.


### Version 1.3.18
* Fix for crashes and performance issues. Issue #70 and Issue #72. Ping output text is no longer selectable. Selectable text was added in version 1.3.15 and this has been causing problems. I will look for another way to reintroduce selectable text in a later version. For now, you can click the icon to open a probe in a separate window and the separate window has selectable text.
* Popup notification window now scales its size to match its contents. Issue #67.
* Add option to enable SSL/TLS for email notifications. Issue #73.


### Version 1.3.17
* Fix: Windows XP/7 would crash when opening the Status History window. This was due to an incompatible reference added in 1.3.16.
* Status History window now has filters. Type in the box to filter by name or address. The different status types are filterable as well: ups, downs, starts, and stops.
* When a system error is encountered while pinging (example: network interface disabled in Windows), vmPing will mark as lost and continue ping attempts. Previously, the pinging would stop entirely.
* Code signed! I purchased a 3-year certificate with your contributions. The pre-compiled binary on this release and all future releases should be code signed. This will get rid of Windows Smart Screen warnings, untrusted publisher errors, and false flagging by antivirus vendors that alert on unsigned executables. You might still see Smart Screen warnings for now since it's reputation-based and this is a brand new cert.


### Version 1.3.16
* Fix: Command line arguments now take precedence over your startup configuration.
* Fix: When changing the title of a favorite, you are now given a warning if the new title already exists.
* The text in each probe window is now selectable. Right-click or CTRL-C to copy. Scrolling is paused while text is selected. Select text from left to right. Selecting text from right to left will not work properly while the probe is active.
* Probe starts and stops are now recorded to the Status History window.
* New Status History window. The data is now displayed as a sortable grid. Filtering and additional options will be included in the next release.
* Keyboard shortcut, F12, opens the Status History window.
* Custom, slimmer, scroll bar style for the probe windows.
* The blinking animation on the stats line when a response is recorded is now much more subtle.
* Stats previously only updated when a response was received or lost. Stats now also update each time a probe is sent.
* Keyboard shortcuts for buttons on the Manage Aliases and Manage Favorites windows.
* Minor style changes to look of the Manage Aliases and Manage Favorites windows.
* Minor style changes to most Windows controls (tab items, drop down boxes, check boxes, radio buttons, text boxes, buttons, etc). Styles should now be more consistent throughout the application.


### Version 1.3.15
* __Startup mode__. You can now configure how vmPing starts. Choose between a blank window (this is the normal, default mode), show the list input window, or load a favorite. For the blank window, you can also set the number of blank probes and initial column count. You will find startup mode settings on the General tab in the Options window. Don't forget to select *Save as vmPing defaults* to make your settings persist.
* When you open the list input window, it now pre-populates with the addresses of the current pings.
* Forced uppercase has been removed from all text boxes.
* Dates and times should now display formatted according to your set region in Windows.


### Version 1.3.14
* __Portable mode.__ Previously, your configuration file had to be stored at %LocalAppData%\vmPing\vmPing.xml. The configuration file includes all favorites, aliases, and default settings for the application. Now vmPing.xml can reside in the same folder as the application, making everything easily portable. Additionally for new users, a simple prompt is displayed if you do anything that would require saving an initial config file. The prompt informs of config file creation, and gives an opportunity to select portable mode if you want your config file created alongside vmPing.exe.
* There's a whole new look to the traceroute window. Check it out. An MTR feature isn't there yet, but should follow in a future release.


### Version 1.3.12
* __New multi-address input.__ Access using the keyboard shortcut F2 or by clicking the option in vmPing's menu. This displays a window with a multi-line textbox. Type your target addresses one per line or comma-separated, click OK, and vmPing populates with your targets and immediately begins pinging. So simple. If you have a text file containing addresses, just drag and drop it onto the window.
* Column count can now be set to anything (within the limits). Previously the column count could never be set higher than the number of probes. This has always annoyed me. Now you can choose any column count and it'll stick. An example would be: Two probes. Set column count to four. vmPing displays two columns since there's only two probes. But as you add more probes, new columns will be made until the four column count is satisfied.
* Improved drag & drop re-ordering of probes. This was a little buggy when first introduced in v1.3.9, but should now perform well. Usage: Hovering your mouse over a probe displays the usual probe title bar. Click and hold in the title bar area, then drag to the desired new location, and release.
* Loading a favorite sets the application title bar to the title of the favorite.
* On the Create New Favorite Set window, you can now drag & drop a text file right onto the list of addresses.
* Minor UI style changes on the Manage Aliases and Manage Favorites window.


### Version 1.3.11
* The recent drag & drop feature was causing issues. Please update to this version if you downloaded 1.3.9-10. The drag & drop functionality is still there, but you must click and drag on the bar that appears across the top of each probe window.


### Version 1.3.10
* If you downloaded version 1.3.9, please replace it with version 1.3.10. The new drag & drop feature introduced a bug that disabled the button toolbar on each probe window. This is fixed in 1.3.10.
* __Drag & drop reordering.__ Click and hold anywhere on a probe, then drag to the desired new location, and release.
* Full control over creating and editing favorite sets. When creating or editing a favorite, you are now given a large multi-line textbox for entering hosts within the favorite. Hosts in the textbox can be one per line, comma-separated, or any combination of new lines and commas.
* Numerous minor UI changes.


### Version 1.3.8
* __New options window.__ The options window was given a minor makeover and now uses a vertical tab layout. This allows room for additional option screens in the future.
* New Notifications tab in the options window for configuring popup notifications. You can now save a default popup notification setting.
* New feature to auto-dismiss popup notifications. This is currently configured through the Notifications tab in the options window.
* New feature to play a sound when a host comes up (previously you could only play sounds when a host went down).
* If you have an alias set for a host, the alias is now shown in popup notifications and email alerts.
* Bug fix: TCP port pings to IPv6 targets now work. If pinging a port on an IPv6 address, wrap the address in brackets, such as *[::1]:443* where *::1* is the target IPv6 address and *443* is the target TCP port.


### Version 1.3.4
* Bug fix: A crash would occur if popup notifications were set to display only when minimized and a host status change occurred.  Thanks @chuckbales for the bug report!


### Version 1.3.3
* Improved handling of loading hosts from a text file to account for empty lines and comments.  Thanks @larntz for adding this feature!
* Added a __Test__ button to the __Email Alerts__ tab so that you can validate and test email alerting.  Thanks @bodagetta for the suggestion.
* Added a __Test__ button to the __Audio Alerts__ tab that plays the audio file you've selected.
* Added simple informational text to the __Email Alerts__ and __Audio Alerts__ tabs.
* Bug fix:  Logging status changes would fail if multiple hosts changed status at the same time.  This has been corrected.  Thanks @Sola1991 for the bug report.
* Bug fix:  When setting a default configuration that includes email alerts with authentication, the config write would fail.  This has been corrected.  Thanks @WNDNCG for the bug report.
* Bug fix:  Aliases would not show when loading hosts from the command line or after selecting a favorite set.  This has been corrected.  Thanks @MeatyFresh for the bug report.
* Bug fix:  Added error checking to audio alert playback.


### Version 1.3.2
* New option to trigger playing a sound when a host goes down.  The setting is found under the Audio Alerts tab on the options window.  Thanks @larntz for adding this feature!
* Bug fix:  Using the log file feature would not work on IPv6 hosts or hosts doing a TCP port ping due to invalid characters in the file name that was being generated.  This is now checked and logging will work in those situations.


### Version 1.3.1
* __New traceroute probe!__  In the hostname box, type __'T/name_or_ip'__ and it'll perform a traceroute right in a probe window.  This feature will become more apparent in a future release, and additional probe types are planned.  Eventually, the old separate traceroute window will go away.
* New option to log status changes to a text file.  This option only writes to the log when a host goes down or up.  The output is in a tab delimited format that is suitable for Excel or database imports.  Note: vmPing does not lock the file, so logging will fail if the file is opened by Excel and vmPing tries to write to the file.
* Fix for vmPing no longer reading hostnames from the command line.
* New command line option to specify a file containing a list of hostnames.  One host per line.  The file is read at startup and vmPing immediately begins pinging each host.  Remember to use quotes if your file path contains spaces.  Usage:  __'vmPing.exe <path_to_file>'__
* Darkened the default color for DNS and traceroute probes.  This is not yet customizable.
* The control bar that appears when you hover over a probe window is now darker (50% black with 50% transparency).  The icons are now darker and the highlight style was changed to accommodate the new colors.
* Re-styled the custom dialog window so it's wider and uses a smaller font.
* Extra tooltips explaining the options under Options -> Log Output.


Features
--------
* Quickly and easily ping multiple hosts.
* Color coding allows you to instantly determine the status of each host.  Green means up.  Red means down.  Orange means error.
* Each host monitor dynamically resizes and scales with the applications window.
* Options to configure the interval between each ping, the timeout, TTL, and message size.
* Monitor TCP ports.  vmPing will continuously connect to a given TCP port and will display whether the port is open or closed.  Enter _HOSTNAME:PORT_ for the hostname.  Example -  _WebserverA:80_
* Option to log everything to a text file.
* Option to log only status changes to a text file.  A status change is when a host you are pinging goes down, or a down host comes back up.
* Popup notifications to alert you of status changes.
* Email notifications on status changes.
* All colors can be customized.
* Favorites.  Easily save a collections of hosts to be recalled instantly at a later time.
* Aliases.  You can assign a friendly display name for any given host.
* Traceroute.  For the hostname, enter _T/HOSTNAME_ to perform a traceroute.
* DNS forward and reverse lookups.  For the hostname, enter _D/NAME_OR_IP_ to perform a DNS lookup.
* Specify any number of hosts from the command line to instantly begin pinging when the application opens.
* Specify a file containing a list of hosts to load and instantly ping when the application launches.
* Command line usage:
  * vmPing.exe [-i interval] [-w timeout] [`<target_host>`...] [`<file_to_load>`...]


Donations
---------
If this tool has been useful to you, consider donating to Ryan Smith using PayPal.
[![Donate to this project using PayPal](https://img.shields.io/badge/Donate-PayPal-green.svg?style=flat)](https://paypal.me/SmithRyn/15)
