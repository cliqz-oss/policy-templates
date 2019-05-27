**IMPORTANT**: This is clone of Firefox's solution for Entreprise. Cliqz desktop browser have some changes on top of Firefox's policies. This document mostly copy of Firefox solution with changes related to Cliqz desktop browser. This is experimental now in Cliqz browser, please, create an issue if something doesn't work for you.

You can find releases compatible with Cliqz browser here: https://github.com/cliqz-oss/policy-templates/releases.

Policies can be specified using the Group Policy templates on Windows (https://github.com/cliqz-oss/policy-templates/tree/master/windows) or by creating a file called `policies.json`. On Windows, create a directory called `distribution` where the EXE is located and place the file there. On Mac, the file goes into `Cliqz.app/Contents/Resources/distribution`.  On Linux, the file goes into `cliqz/distribution`, where `cliqz` is the installation directory for cliqz, which varies by distribution.

The content of the JSON file should look like this:
```
{
  "policies": {
    ...POLICIES...
  }
}
```
Policies are documented below.


**Note**: though comments are used in this readme file for documentation, comments are not valid in actual JSON files. Remove all comments before attempting to deploy.

### AppUpdateURL
This policy is for changing the URL used for application update
```
{
  "AppUpdateURL": "http://yoursite.com"
}
```

### Authentication
This policy is for configuring sites that support integrated authentication. See https://developer.mozilla.org/en-US/docs/Mozilla/Integrated_authentication for more information.
```
{
  "policies": {
    "Authentication": {
      "SPNEGO": ["mydomain.com", "https://myotherdomain.com"],
      "Delegated": ["mydomain.com", "https://myotherdomain.com"],
      "NTLM": ["mydomain.com", "https://myotherdomain.com"],
      "AllowNonFQDN": {
        "SPNEGO": true,
        "NTLM": true
      }
    }
  }
}
```
### BlockAboutAddons
This policy removes access to about:addons.
```
{
  "policies": {
    "BlockAboutAddons": true
  }
}
```
### BlockAboutConfig
This policy removes access to about:config.
```
{
  "policies": {
    "BlockAboutConfig": true
  }
}
```
### BlockAboutProfiles
This policy removes access to about:profiles.
```
{
  "policies": {
    "BlockAboutProfiles": true
  }
}
```
### BlockAboutSupport
This policy removes access to about:support.
```
{
  "policies": {
    "BlockAboutSupport": true
}
```
### Bookmarks
This policy allows you to specify bookmarks. You can have any number of bookmarks, although only ten are specified in the ADMX file.
Placement can be specified as either toolbar or menu. If a folder is specified, it is automatically created and bookmarks with the
same folder name are grouped together.
```
{
  "policies": {
    "Bookmarks": [
      {
        "Title": "Example",
        "URL": "http://example.org",
        "Favicon": "http://example.com/favicon.ico",
        "Placement": ["toolbar", "menu"],
        "Folder": "FolderName"
      }
    ]
  }
}
```
### Certificates
This policy can be used to install certificates or to read certificates from the system certificate store on Mac and Windows.

The ImportEnterpriseRoots key will cause Cliqz to import from the system certificate store.

The Install Certificates key by default will search for certificates in the locations listed below.
Starting in Cliqz 1.27.0 you can specify a fully qualified path including UNC. (See cert3.der and cert4.pem, in example).

**Be advised if you wish to load a certificate from a UNC path you must use double backslahes.**
Example: \\SERVER\\CERTS\CERT5.PEM


If Cliqz does not find something at your fully qualified path, it will search the default directories.

Certificates can be located in the following locations:
- Windows
  - %USERPROFILE%\AppData\Local\Cliqz\Certificates
  - %USERPROFILE%\AppData\Roaming\Cliqz\Certificates
- macOS
  - /Library/Application Support/Cliqz/Certificates
  - ~/Library/Application Support/Cliqz/Certificates
- Linux
  - /usr/lib/cliqz/certificates
  - /usr/lib64/cliqz/certificates
  - ~/.cliqz/certificates


```
{
  "policies": {
    "Certificates": {
      "ImportEnterpriseRoots": true,
      "Install": ["cert1.der", "cert2.pem", "%SYSTEMDRIVE%\Company\cert3.der", "/Library/Company/cert4.pem", "\\server\\certs\\cert.pem"]
    }
  }
}
```
### Cookies
This policy controls various settings related to cookies.
```
{
  "policies": {
    "Cookies": {
      "Allow": ["http://example.org/"], /* Domains where cookies are always allowed */
      "Block": ["http://example.edu/"], /* Domains where cookies are always blocked */
      "Default": [true|false], /* This sets the default value for "Accept cookies from websites" */
      "AcceptThirdParty": ["always", "never", "from-visited"], /* This sets the default value for "Accept third-party cookies" */
      "ExpireAtSessionEnd":  [true|false], /* This determines when cookies expire */
      "RejectTracker": [true|false], /* Only reject trackers */
      "Locked": [true|false] /* If this is true, cookies preferences can't be changed */
    }
  }
}
```
### DNSOverHTTPS
This policy configures DNS over HTTPS.
```
{
  "policies": {
    "DNSOverHTTPS": {
      "Enabled": [true|false],
      "ProviderURL": "URL_TO_ALTERNATE_PROVIDER",
      "Locked": [true|false]
    }
  }
}
```
### DisableSetDesktopBackground
This policy removes the "Set As Desktop Background..." menuitem when right clicking on an image.
```
{
  "policies": {
    "DisableSetDesktopBackground": true
  }
}
```
### DisableMasterPasswordCreation
If this policy is set to true, the master password functionality is removed.
```
{
  "policies": {
    "DisableMasterPasswordCreation": [true|false]
  }
}
```
### DisableAppUpdate
This policy turns off application updates.
```
{
  "policies": {
    "DisableAppUpdate": true
  }
}
```
### DisableBuiltinPDFViewer
This policy disables the built in PDF viewer. PDF files are downloaded and sent externally.
```
{
  "policies": {
    "DisableBuiltinPDFViewer": true
  }
}
```
### DisableDeveloperTools
This policy removes access to all developer tools.
```
{
  "policies": {
    "DisableDeveloperTools": true
  }
}
```
### DisableFeedbackCommands
This policy disables the menus for reporting sites (Submit Feedback, Report Deceptive Site).
```
{
  "policies": {
    "DisableFeedbackCommands": true
  }
}
```
### DisableForgetButton
This policy disables the "Forget" button.
```
{
  "policies": {
    "DisableForgetButton": true
  }
}
```
### DisableFormHistory
This policy turns off the browser.formfill.enable preferences.
```
{
  "policies": {
    "DisableFormHistory": true
  }
}
```
### DisablePrivateBrowsing
This policy removes access to private browsing.
```
{
  "policies": {
    "DisablePrivateBrowsing": true
  }
}
```
### DisableProfileImport
This policy disables the "Import data from another browser" option in the bookmarks window.
```
{
  "policies": {
    "DisableProfileImport": true
  }
}
```
### DisableProfileRefresh
This policy disables the Refresh Cliqz button on about:support.
```
{
  "policies": {
    "DisableProfileRefresh": true
  }
}
```
### DisableSafeMode
This policy disables safe mode on Windows and macOS only.
```
{
  "policies": {
    "DisableSafeMode": true
  }
}
```
### DisableSecurityBypass
This policy prevents the user from bypassing security in certain cases.
```
{
  "policies": {
    "DisableSecurityBypass": {
      "InvalidCertificate": [true|false], /* Prevents adding an exception when an invalid certificate is shown */
      "SafeBrowsing": [true|false]        /* Prevents selecting "ignore the risk" and visiting a harmful site anyway */
    }
  }
}
```
### DisableSystemAddonUpdate
This policy prevents system add-ons from being updated or installed.
```
{
  "policies": {
    "DisableSystemAddonUpdate": true
  }
}
```
### DisableTelemetry
This policy prevents the upload of telemetry data.

Mozilla recommends that you do not disable telemetry. Information collected through telemetry helps us build a better product for businesses like yours.
```
{
  "policies": {
    "DisableTelemetry": true
  }
}
```
### DisplayBookmarksToolbar
This policy turns on the bookmarks toolbar by default. A user can still turn it off, and it will stay off.
```
{
  "policies": {
    "DisplayBookmarksToolbar": true
  }
}
```
### DisplayMenuBar
This policy turns on the menubar by default. A user can still turn it off, and it will stay off.
```
{
  "policies": {
    "DisplayMenuBar": true
  }
}
```
### DontCheckDefaultBrowser
This policy stops Cliqz from checking if it is the default browser at startup.
```
{
  "policies": {
    "DontCheckDefaultBrowser": true
  }
}
```
### Extensions
This policy controls the installation, uninstallation and locking of extensions. Locked extensions cannot be disabled or uninstalled.
For Install, you specify a list of URLs or paths.
For Uninstall and Locked, you specify extension IDs.
```
{
  "policies": {
    "Extensions": {
      "Install": ["https://addons.mozilla.org/firefox/downloads/somefile.xpi", "//path/to/xpi"],
      "Uninstall": ["addon_id@mozilla.org"],
      "Locked":  ["addon_id@mozilla.org"]
    }
  }
}
```
### HardwareAcceleration
This policy disables hardware acceleration by locking the preference layers.acceleration.disabled to true.
```
{
  "policies": {
    "HardwareAcceleration": false
  }
}
```
### NoDefaultBookmarks
This policy prevents the default bookmarks or the Smart Bookmarks (Most Visited, Recent Tags) from being created. Note: this policy is only effective if used before the first run of the profile.
```
{
  "policies": {
    "NoDefaultBookmarks": true
  }
}
```
### OfferToSaveLogins
This policy sets the signon.rememberSignons preference. It determines whether or not Cliqz offers to save passwords. It can either be enabled or disabled.
```
{
  "policies": {
    "OfferToSaveLogins": true
  }
}
```
### Startup
This policy sets the default startup options value: default start pages, restore session, etc. It can also be used to lock the startup options.
```
{
  "policies": {
    "Startup": {
      "RestoreLastSession": false,
      "ShowHomepage": true,
      "Locked": true,
      "URLs": ["http://example.org/",
               "http://example.edu/"],
      "Homepage": ["default", "urls", "blank"]
    }
  }
}
```
### PopupBlocking
This policy sets domains for which pop-up windows are allowed. It also sets the default pop-up policy.
```
{
  "policies": {
    "PopupBlocking": {
      "Allow": ["http://example.org/",
                "http://example.edu/"],
      "Default": [true|false], /* If this is set to false, pop-up window are enabled by default. */
      "Locked": [true|false]
    }
  }
}
```
### InstallAddonsPermission
This policy sets domains that can install extensions, as well as the default behavior.
```
{
  "policies": {
    "InstallAddonsPermission": {
      "Allow": ["http://example.org/",
                "http://example.edu/"],
      "Default": [true|false] /* If this is set to false, add-ons cannot be installed by the user */
    }
  }
}
```
### FlashPlugin
This policy sets the behavior of Flash on the specified domains, as well as the default behavior.
```
{
  "policies": {
    "FlashPlugin": {
      "Allow": ["http://example.org/"], /* Sites on the allow list do not override Flash being completely disabled */
      "Block": ["http://example.edu/"],
      "Default": [true|false], /* If this is set to true, Flash is always enabled. If it is set to false, Flash is never enabled */
      "Locked": [true|false]
    }
  }
}
```
### OverrideFirstRunPage
This policy allows you to override the first run page. If you leave the URL blank, the first run page will not be displayed.
```
{
  "policies": {
    "OverrideFirstRunPage": "http://example.org"
  }
}
```
### OverridePostUpdatePage
This policy allows you to override the upgrade page. If you leave the URL blank, the upgrade page will not be displayed.
```
{
  "policies": {
    "OverridePostUpdatePage": "http://example.org"
  }
}
```
### Permissions
This policy allows you to change the permissions associated with camera, microphone, location, and notifications
```
{
  "policies": {
    "Permissions": {
      "Camera": {
        "Allow": ["http://example.org/"], /* Origins where camera access is allowed by default */
        "Block": ["http://example.org/"], /* Origins where camera access is blocked by default */
        "BlockNewRequests": [true|false], /* Block new requests to access the camera */
        "Locked": [true|false] /* Don't allow the user to change the camera preferences */
      },
      "Microphone": {
        "Allow": ["http://example.org/"], /* Origins where microphone access is allowed by default */
        "Block": ["http://example.org/"], /* Origins where microphone access  is blocked by default */
        "BlockNewRequests": [true|false], /* Block new requests to access the microphone */
        "Locked": [true|false] /* Don't allow the user to change the microphone preferences */
      },
      "Location": {
        "Allow": ["http://example.org/"], /* Origins where location access is allowed by default */
        "Block": ["http://example.org/"], /* Origins where location access is blocked by default */
        "BlockNewRequests": [true|false], /* Block new requests to access location */
        "Locked": [true|false] /* Don't allow the user to change the location preferences */
      },
      "Notifications": {
        "Allow": ["http://example.org/"], /* Origins where sending notifications is allowed by default */
        "Block": ["http://example.org/"], /* Origins where sending notifications is blocked by default */
        "BlockNewRequests": [true|false], /* Block new requests to send notifications */
        "Locked": [true|false] /* Don't allow the user to change the notification preferences */
      }
    }
  }
}
```
### Proxy
This policy allows you to specify proxy settings. These settings correspond to the connection settings in Cliqz preferences.
To specify ports, append them to the hostnames with a colon (:). If Locked is set to true, the values can't be changed by the user.
```
{
  "policies": {
    "Proxy": {
      "Mode": ["none", "system", "manual", "autoDetect", "autoConfig"],
      "Locked": [true, false],
      "HTTPProxy": "hostname",
      "UseHTTPProxyForAllProtocols": [true, false],
      "SSLProxy": "hostname",
      "FTPProxy": "hostname",
      "SOCKSProxy": "hostname",
      "SOCKSVersion": [4, 5],
      "Passthrough": "List of passthrough addresses/domains",
      "AutoConfigURL": "URL_TO_AUTOCONFIG",
      "AutoLogin":  [true, false],
      "UseProxyForDNS": [true, false]
    }
  }
}
```
### SanitizeOnShutdown
If this policy is set to true, all data is cleared when Cliqz is closed. This includes Browsing & Download History, Cookies, Active Logins, Cache, Form & Search History, Site Preferences and Offline Website Data.
```
{
  "policies": {
    "SanitizeOnShutdown": [true|false]
  }
}
```
### WebsiteFilter
This policy blocks websites from being visited. The parameters take an array of Match Patterns, as documented in https://developer.mozilla.org/en-US/Add-ons/WebExtensions/Match_patterns. Only http/https addresses are supported at the moment. The arrays are limited to 1000 entries each.
```
{
  "policies": {
    "WebsiteFilter": {
      "Block": ["<all_urls>"],
      "Exceptions": ["http://example.org/*"]
    }
  }
}
```
### SecurityDevices
This policy allows you to add PKCS #11 Modules
```
{
  "policies": {
    "SecurityDevices": {
      "NAME_OF_DEVICE": "PATH_TO_LIBRARY_FOR_DEVICE"
    }
  }
}
```
### SSLVersionMin
This policy allows you to set the minimum TLS version.
```
{
  "policies": {
    "SSSLVersionMin": ["tls1", "tls1.1", "tls1.2",. "tls1.3"]
  }
}

```
### SSLVersionMax
This policy allows you to set the maximum TLS version.
```
{
  "policies": {
    "SSSLVersionMax": ["tls1", "tls1.1", "tls1.2",. "tls1.3"]
  }
}
```
