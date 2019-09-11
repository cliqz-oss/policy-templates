**IMPORTANT**: This is clone of Firefox's solution for Entreprise. Cliqz desktop browser have some changes on top of Firefox's policies. This document mostly copy of Firefox solution with changes related to Cliqz desktop browser. This is experimental now in Cliqz browser, please, create an issue if something doesn't work for you.

You can find releases compatible with Cliqz browser here: https://github.com/cliqz-oss/policy-templates/releases.

Policies can be specified using the Group Policy templates on Windows (https://github.com/cliqz-oss/policy-templates/tree/master/windows) or by creating a file called `policies.json`. On Windows, create a directory called `distribution` where the EXE is located and place the file there. On Mac, the file goes into `Cliqz.app/Contents/Resources/distribution`.  On Linux, the file goes into `cliqz/distribution`, where `cliqz` is the installation directory for Cliqz, which varies by distribution.

| Policy Name | Description
| --- | --- |
| **[`AppUpdateURL`](#AppUpdateURL)** | Change the URL for application update.
| **[`Authentication`](#Authentication)** | Configure sites that support integrated authentication.
| **[`BlockAboutAddons`](#blockaboutaddons)** | Block access to the Add-ons Manager (about:addons).
| **[`BlockAboutConfig`](#blockaboutconfig)** | Block access to about:config.
| **[`BlockAboutProfiles`](#blockaboutprofiles)** | Block access to About Profiles (about:profiles).
| **[`BlockAboutSupport`](#blockaboutsupport)** | Block access to Troubleshooting Information (about:support).
| **[`Bookmarks`](#bookmarks)** | Add bookmarks in either the bookmarks toolbar or menu.
| **[`CaptivePortal`](#captiveportal)** | Enable or disable the detection of captive portals.
| **[`Certificates`](#certificates)** |
| **[`Certificates -> ImportEnterpriseRoots`](#certificates--importenterpriseroots)** | Trust certificates that have been added to the operating system certificate store by a user or administrator.
| **[`Certificates -> Install`](#certificates--install)** | Install certificates into the Cliqz certificate store.
| **[`Cookies`](#cookies)** | Configure cookie preferences.
| **[`DisableSetDesktopBackground`](#disablesetdesktopbackground)** | Remove the "Set As Desktop Background..." menuitem when right clicking on an image.
| **[`DisableMasterPasswordCreation`](#disablemasterpasswordcreation)** | Remove the master password functionality.
| **[`DisableAppUpdate`](#disableappupdate)** | Turn off application updates.
| **[`DisableBuiltinPDFViewer`](#disablebuiltinpdfviewer)** | Disable the built in PDF viewer.
| **[`DisableDeveloperTools`](#disabledevelopertools)** | Remove access to all developer tools.
| **[`DisableFeedbackCommands`](#disablefeedbackcommands)** | Disable the menus for reporting sites.
| **[`DisableForgetButton`](#disableforgetbutton)** | Disable the "Forget" button.
| **[`DisableFormHistory`](#disableformhistory)** | Turn off saving information on web forms and the search bar.
| **[`DisablePrivateBrowsing`](#disableprivatebrowsing)** | Remove access to private browsing.
| **[`DisableProfileImport`](#disableprofileimport)** | Disables the "Import data from another browser" option in the bookmarks window.
| **[`DisableProfileRefresh`](#disableprofilerefresh)** | Disable the Refresh Cliqz button on about:support and support.mozilla.org
| **[`DisableSafeMode`](#disablesafemode)** | Disable safe mode within the browser.
| **[`DisableSecurityBypass`](#disablesecuritybypass)** | Prevent the user from bypassing security in certain cases.
| **[`DisableSystemAddonUpdate`](#disablesystemaddonupdate)** | Prevent system add-ons from being installed or update.
| **[`DisableTelemetry`](#disabletelemetry)** | DisableTelemetry
| **[`DisplayBookmarksToolbar`](#displaybookmarkstoolbar)** | Set the initial state of the bookmarks toolbar.
| **[`DisplayMenuBar`](#displaymenubar)** | Set the initial state of the menubar.
| **[`DNSOverHTTPS`](#dnsoverhttps)** | Configure DNS over HTTPS.
| **[`DontCheckDefaultBrowser`](#dontcheckdefaultbrowser)** | Don't check if Cliqz is the default browser at startup.
| **[`DefaultDownloadDirectory`](#defaultdownloaddirectory)** | Set the default download directory.
| **[`DownloadDirectory`](#downloaddirectory)** | Set and lock the download directory.
| **[`EnterprisePoliciesEnabled`](#enterprisepoliciesenabled)** | Enable policy support on macOS.
| **[`Extensions`](#extensions)** | Control the installation, uninstallation and locking of extensions.
| **[`ExtensionSettings`](#extensionsettings)** | Manage all aspects of extensions.
| **[`ExtensionUpdate`](#extensionupdate)** | Control extension updates.
| **[`FlashPlugin`](#flashplugin)** | Configure the default Flash plugin policy as well as origins for which Flash is allowed.
| **[`HardwareAcceleration`](#hardwareacceleration)** | Control hardware acceleration.
| **[`InstallAddonsPermission`](#installaddonspermission)** | Configure the default extension install policy as well as origins for extension installs are allowed.
| **[`LocalFileLinks`](#localfilelinks)** | Enable linking to local files by origin.
| **[`NetworkPrediction`](#networkprediction)** | Enable or disable network prediction (DNS prefetching).
| **[`NoDefaultBookmarks`](#nodefaultbookmarks)** | Disable the creation of default bookmarks.
| **[`OfferToSaveLogins`](#offertosavelogins)** | Control whether or not Cliqz offers to save passwords.
| **[`OverrideFirstRunPage`](#overridefirstrunpage)** | Override the first run page.
| **[`OverridePostUpdatePage`](#overridepostupdatepage)** | Override the upgrade page.
| **[`Permissions`](#permissions)** | Set permissions associated with camera, microphone, location, and notifications.
| **[`PopupBlocking`](#popupblocking)** | Configure the default pop-up window policy as well as origins for which pop-up windows are allowed.
| **[`Preferences`](#preferences)** | Set and lock some preferences.
| **[`PromptForDownloadLocation`](#promptfordownloadlocation)** | Ask where to save each file before downloading.
| **[`Proxy`](#proxy)** | Configure proxy settings.
| **[`SanitizeOnShutdown` (All)](#sanitizeonshutdown-all)** | Clear all data on shutdown.
| **[`SanitizeOnShutdown` (Selective)](#sanitizeonshutdown-selective)** | Clear data on shutdown.
| **[`SecurityDevices`](#securitydevices)** | Install PKCS #11 modules.
| **[`SSLVersionMax`](#sslversionmax)** | Set and lock the maximum version of TLS.
| **[`SSLVersionMin`](#sslversionmin)** | Set and lock the minimum version of TLS.
| **[`Startup`](#startup)** | Configure how Cliqz starts.
| **[`SupportMenu`](#supportmenu)** | Add a menuitem to the help menu for specifying support information.
| **[`WebsiteFilter`](#websitefilter)** | Block websites from being visited.

### AppUpdateURL

Change the URL for application update.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `app.update.url`

#### Windows
```
Software\Policies\Cliqz\AppUpdateURL = "https://yoursite.com"
```
#### macOS
```
<dict>
  <key>AppUpdateURL</key>
  <string>https://yoursite.com</string>
</dict>
```
#### JSON
```
{
  "policies": {
    "AppUpdateURL": "https://yoursite.com"
  }
}
```
### Authentication

Configure sites that support integrated authentication.

See https://developer.mozilla.org/en-US/docs/Mozilla/Integrated_authentication for more information.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `network.negotiate-auth.trusted-uris`, `network.negotiate-auth.delegation-uris`, `network.automatic-ntlm-auth.trusted-uris`, `network.automatic-ntlm-auth.allow-non-fqdn`, `network.negotiate-auth.allow-non-fqdn`

#### Windows
```
Software\Policies\Cliqz\Authentication\SPNEGO\1 = "mydomain.com"
Software\Policies\Cliqz\Authentication\SPNEGO\2 = "https://myotherdomain.com"
Software\Policies\Cliqz\Authentication\Delegated\1 = "mydomain.com"
Software\Policies\Cliqz\Authentication\Delegated\2 = "https://myotherdomain.com"
Software\Policies\Cliqz\Authentication\NTLM\1 = "mydomain.com"
Software\Policies\Cliqz\Authentication\NTLM\2 = "https://myotherdomain.com"
Software\Policies\Cliqz\Authentication\AllowNonFQDN\SPNEGO = 0x1 | 0x0
Software\Policies\Cliqz\Authentication\AllowNonFQDN\NTLM = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>Authentication</key>
  <dict>
    <key>SPNEGO</key>
    <array>
      <string>mydomain.com</string>
      <string>https://myotherdomain.com</string>
    </array>
    <key>Delegated</key>
    <array>
      <string>mydomain.com</string>
      <string>https://myotherdomain.com</string>
    </array>
    <key>NTLM</key>
    <array>
      <string>mydomain.com</string>
      <string>https://myotherdomain.com</string>
    </array>
    <key>AllowNonFQDN</key>
      <dict>
      <key>SPNEGO</key>
      <true/> | <false/>
      <key>NTLM</key>
      <true/> | <false/>
    </dict>
  </dict>
</dict>
```
#### JSON
```
{
  "policies": {
    "Authentication": {
      "SPNEGO": ["mydomain.com", "https://myotherdomain.com"],
      "Delegated": ["mydomain.com", "https://myotherdomain.com"],
      "NTLM": ["mydomain.com", "https://myotherdomain.com"],
      "AllowNonFQDN": {
        "SPNEGO": true | false,
        "NTLM": true | false
      }
    }
  }
}
```
### BlockAboutAddons

Block access to the Add-ons Manager (about:addons).

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `disableAddonsManager`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\BlockAboutAddons = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>BlockAboutAddons</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "BlockAboutAddons": true | false
  }
}
```
### BlockAboutConfig

Block access to about:config.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `disableAboutConfig`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\BlockAboutConfig = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>BlockAboutConfig</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "BlockAboutConfig": true | false
  }
}
```
### BlockAboutProfiles

Block access to About Profiles (about:profiles).

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `disableAboutProfiles`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\BlockAboutProfiles = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>BlockAboutProfiles</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "BlockAboutProfiles": true | false
  }
}
```
### BlockAboutSupport

Block access to Troubleshooting Information (about:support).

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `disableAboutSupport`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\BlockAboutSupport = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>BlockAboutSupport</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "BlockAboutSupport": true | false
  }
}
```
### Bookmarks

Add bookmarks in either the bookmarks toolbar or menu. Only `Title` and `URL` are required. If `Placement` is not specified, the bookmark will be placed on the toolbar. If `Folder` is specified, it is automatically created and bookmarks with the same folder name are grouped together.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `bookmarks.toolbar`,`bookmarks.menu`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\Bookmarks\1\Title = "Example"
Software\Policies\Cliqz\Bookmarks\1\URL = "https://example.com"
Software\Policies\Cliqz\Bookmarks\1\Favicon = "https://example.com/favicon.ico"
Software\Policies\Cliqz\Bookmarks\1\Placement = "toolbar" | "menu"
Software\Policies\Cliqz\Bookmarks\1\Folder = "FolderName"
```
#### macOS
```
<dict>
  <key>Bookmarks</key>
  <array>
    <dict>
      <key>Title</key>
      <string>Example</string>
      <key>URL</key>
      <string>https://example.com</string>
      <key>Favicon</key>
      <string>https://example.com/favicon.ico</string>
      <key>Placement</key>
      <string>toolbar | menu</string>
      <key>Folder</key>
      <string>FolderName</string>
    </dict>
  </array>
</dict>
```
#### JSON
```
{
  "policies": {
    "Bookmarks": [
      {
        "Title": "Example",
        "URL": "https://example.com",
        "Favicon": "https://example.com/favicon.ico",
        "Placement": "toolbar" | "menu",
        "Folder": "FolderName"
      }
    ]
  }
}
```
### CaptivePortal
Enable or disable the detection of captive portals.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `network.captive-portal-service.enabled`

#### Windows
```
Software\Policies\Cliqz\CaptivePortal = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>CaptivePortal</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "CaptivePortal": true | false
  }
}
```
### Certificates

### Certificates | ImportEnterpriseRoots

Trust certificates that have been added to the operating system certificate store by a user or administrator.

See https://support.mozilla.org/kb/setting-certificate-authorities-firefox for more detail.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `security.enterprise_roots.enabled`

#### Windows
```
Software\Policies\Cliqz\Certificates\ImportEnterpriseRoots = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>Certificates</key>
  <dict>
    <key>ImportEnterpriseRoots</key>
    <true/> | <false/>
  </dict>
</dict>
```
#### JSON
```
{
  "policies": {
    "Certificates": {
      "ImportEnterpriseRoots": true | false
    }
  }
}
```
### Certificates | Install

Install certificates into the Cliqz certificate store. If only a filename is specified, Cliqz searches for the file in the following locations:

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

Starting with Cliqz 1.27.0, a fully qualified path can be used, including UNC paths. You should use the native path style for your operating system. We do not support using %USERPROFILE% or other environment variables on Windows.

If you are specifying the path in the policies.json file on Windows, you need to escape your backslashes (`\\`) which means that for UNC paths, you need to escape both (`\\\\`). If you use group policy, you only need one backslash.

Certificates are installed using the trust string `CT,CT,`.

Binary (DER) and ASCII (PEM) certificates are both supported.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `certs.ca`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\Certificates\Install\1 = "cert1.der"
Software\Policies\Cliqz\Certificates\Install\2 = "C:\Users\username\cert2.pem"
```
#### macOS
```
<dict>
  <key>Certificates</key>
  <dict>
    <key>Install</key>
    <array>
      <string>cert1.der</string>
      <string>/Users/username/cert2.pem</string>
    </array>
  </dict>
</dict>
```
#### JSON
```
{
  "policies": {
    "Certificates": {
      "Install": ["cert1.der", "/home/username/cert2.pem"]
    }
  }
}
```
### Cookies
Configure cookie preferences.

`Allow` is a list of origins (not domains) where cookies are always allowed. You must include http or https.

`Block` is a list of origins (not domains) where cookies are always blocked. You must include http or https.

`Default` determines whether cookies are accepted at all.

`AcceptThirdParty` determines how third-party cookies are handled.

`ExpireAtSessionEnd` determines when cookies expire.

`RejectTracker` only rejects cookies for trackers.

`Locked` prevents the user from changing cookie preferences.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `network.cookie.cookieBehavior`,`network.cookie.lifetimePolicy`

#### Windows
```
Software\Policies\Cliqz\Cookies\Allow\1 = "https://example.com"
Software\Policies\Cliqz\Cookies\Block\1 = "https://example.org"
Software\Policies\Cliqz\Cookies\Default = 0x1 | 0x0
Software\Policies\Cliqz\Cookies\AcceptThirdParty = "always" | "never" |"from-visited"
Software\Policies\Cliqz\Cookies\ExpireAtSessionEnd = 0x1 | 0x0
Software\Policies\Cliqz\Cookies\RejectTracker = 0x1 | 0x0
Software\Policies\Cliqz\Cookies\Locked = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>Cookies</key>
  <dict>
    <key>Allow</key>
    <array>
      <string>http://example.com</string>
    </array>
    <key>Block</key>
    <array>
      <string>http://example.org</string>
    </array>
    <key>Default</key>
    <true/> | <false/>
    <key>AcceptThirdParty</key>
    <string>always | never | from-visited</string>
    <key>ExpireAtSessionEnd</key>
    <true/> | <false/>
    <key>RejectTracker</key>
    <true/> | <false/>
    <key>Locked</key>
    <true/> | <false/>
  </dict>
</dict>
```
#### JSON
```
{
  "policies": {
    "Cookies": {
      "Allow": ["http://example.org/"],
      "Block": ["http://example.edu/"],
      "Default": true | false,
      "AcceptThirdParty": "always" | "never" | "from-visited"],
      "ExpireAtSessionEnd": true | false,
      "RejectTracker": true | false,
      "Locked": true | false
    }
  }
}
```
### DisableSetDesktopBackground
Remove the "Set As Desktop Background..." menuitem when right clicking on an image.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `removeSetDesktopBackground`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\DisableSetDesktopBackground = 0x1 | 0x0
```

#### macOS
```
<dict>
  <key>DisableSetDesktopBackground</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "DisableSetDesktopBackground": true | false
  }
}
```
### DisableMasterPasswordCreation
Remove the master password functionality.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `noMasterPassword`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\DisableMasterPasswordCreation = 0x1 | 0x0
```

#### macOS
```
<dict>
  <key>DisableMasterPasswordCreation</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "DisableMasterPasswordCreation": true | false
  }
}
```
### DisableAppUpdate
Turn off application updates.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `disableCliqzUpdates`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\DisableAppUpdate = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>DisableAppUpdate</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "DisableAppUpdate": true | false
  }
}
```
### DisableBuiltinPDFViewer
Disable the built in PDF viewer. PDF files are downloaded and sent externally.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `disablePDFjs`\
**Preferences Affected:** `pdfjs.disabled`

#### Windows
```
Software\Policies\Cliqz\DisableBuiltinPDFViewer = 0x1 | 0x0
```

#### macOS
```
<dict>
  <key>DisableBuiltinPDFViewer</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "DisableBuiltinPDFViewer": true | false
  }
}
```
### DisableDeveloperTools
Remove access to all developer tools.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `removeDeveloperTools`\
**Preferences Affected:** `devtools.policy.disabled`

#### Windows
```
Software\Policies\Cliqz\DisableDeveloperTools = 0x1 | 0x0`
```

#### macOS
```
<dict>
  <key>DisableDeveloperTools</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "DisableDeveloperTools": true | false
  }
}
```
### DisableFeedbackCommands
Disable the menus for reporting sites (Submit Feedback, Report Deceptive Site).

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\DisableFeedbackCommands = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>DisableFeedbackCommands</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "DisableFeedbackCommands": true | false
  }
}
```
### DisableForgetButton
Disable the "Forget" button.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `disableForget`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\DisableForgetButton = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>DisableForgetButton</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "DisableForgetButton": true | false
  }
}
```
### DisableFormHistory
Turn off saving information on web forms and the search bar.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `disableFormFill`\
**Preferences Affected:** ` browser.formfill.enable`

#### Windows
```
Software\Policies\Cliqz\DisableFormHistory = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>DisableFormHistory</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "DisableFormHistory": true | false
  }
}
```
### DisablePrivateBrowsing
Remove access to private browsing.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `disablePrivateBrowsing`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\DisablePrivateBrowsing = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>DisablePrivateBrowsing</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "DisablePrivateBrowsing": true | false
  }
}
```
### DisableProfileImport
Disables the "Import data from another browser" option in the bookmarks window.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\DisableProfileImport = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>DisableProfileImport</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "DisableProfileImport": true | false
  }
}
```
### DisableProfileRefresh
Disable the Refresh Cliqz button on about:support and support.mozilla.org, as well as the prompt that displays offering to refresh Cliqz when you haven't used it in a while.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `disableResetCliqz`\
**Preferences Affected:** `browser.disableResetPrompt`

#### Windows
```
Software\Policies\Cliqz\DisableProfileRefresh = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>DisableProfileRefresh</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "DisableProfileRefresh": true | false
  }
}
```
### DisableSafeMode
Disable safe mode within the browser.

On Windows, this disables safe mode via the command line as well.

**Compatibility:** Cliqz 1.27.0 (Windows, macOS)\
**CCK2 Equivalent:** `disableSafeMode`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\DisableSafeMode = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>DisableSafeMode</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "DisableSafeMode": true | false
  }
}
```
### DisableSecurityBypass
Prevent the user from bypassing security in certain cases.

`InvalidCertificate` prevents adding an exception when an invalid certificate is shown.

`SafeBrowsing` prevents selecting "ignore the risk" and visiting a harmful site anyway.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `security.certerror.hideAddException`,`browser.safebrowsing.allowOverride`

#### Windows
```
Software\Policies\Cliqz\DisableSecurityBypass\InvalidCertificate = 0x1 | 0x0
Software\Policies\Cliqz\DisableSecurityBypass\SafeBrowsing = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>DisableSecurityBypass</key>
  <dict>
    <key>InvalidCertificate</key>
    <true/> | <false/>
    <key><SafeBrowsing/key>
    <true/> | <false/>
  </dict>
</dict>
```
#### JSON
```
{
  "policies": {
    "DisableSecurityBypass": {
      "InvalidCertificate": true false,
      "SafeBrowsing": true false
    }
  }
}
```
### DisableSystemAddonUpdate
Prevent system add-ons from being installed or update.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** N/A

#### Windows
```Software\Policies\Cliqz\DisableSystemAddonUpdate = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>DisableSystemAddonUpdate</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "DisableSystemAddonUpdate": true | false
  }
}
```
### DisableTelemetry
Prevent the upload of telemetry data.

Cliqz recommends that you do not disable telemetry. Information collected through telemetry helps us build a better product for businesses like yours.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `disableTelemetry`\
**Preferences Affected:** `datareporting.healthreport.uploadEnabled,datareporting.policy.dataSubmissionEnabled`

#### Windows
```
Software\Policies\Cliqz\DisableTelemetry = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>DisableTelemetry</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "DisableTelemetry": true | false
  }
}
```
### DisplayBookmarksToolbar
Set the initial state of the bookmarks toolbar. A user can still hide it and it will stay hidden.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `displayBookmarksToolbar`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\DisplayBookmarksToolbar = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>DisplayBookmarksToolbar</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "DisplayBookmarksToolbar": true | false
  }
}
```
### DisplayMenuBar
Set the initial state of the menubar. A user can still hide it and it will stay hidden.

**Compatibility:** Cliqz 1.27.0 (Windows, some Linux)\
**CCK2 Equivalent:** `displayMenuBar`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\DisplayMenuBar = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>DisplayMenuBar</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "DisplayMenuBar": true | false
  }
}
```
### DNSOverHTTPS
Configure DNS over HTTPS.

`Enabled` determines whether DNS over HTTPS is enabled

`ProviderURL` is a URL to another provider.

`Locked` prevents the user from changing DNS over HTTPS preferences.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `network.trr.mode`,`network.trr.uri`

#### Windows
```
Software\Policies\Cliqz\DNSOverHTTPS\Enabled = 0x1 | 0x0
Software\Policies\Cliqz\DNSOverHTTPS\ProviderURL = "URL_TO_ALTERNATE_PROVIDER"
Software\Policies\Cliqz\DNSOverHTTPS\Locked = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>DNSOverHTTPS</key>
  <dict>
    <key>Enabled</key>
    <true/> | <false/>
    <key>ProviderURL</key>
    <string>URL_TO_ALTERNATE_PROVIDER</string>
    <key>Locked</key>
    <true/> | <false/>
  </dict>
</dict>
```
#### JSON
```
{
  "policies": {
    "DNSOverHTTPS": {
      "Enabled":  true | false,
      "ProviderURL": "URL_TO_ALTERNATE_PROVIDER",
      "Locked": true | false
    }
  }
}
```
### DontCheckDefaultBrowser
Don't check if Cliqz is the default browser at startup.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `dontCheckDefaultBrowser`\
**Preferences Affected:** `browser.shell.checkDefaultBrowser`

#### Windows
```
Software\Policies\Cliqz\DontCheckDefaultBrowser = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>DontCheckDefaultBrowser</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "DontCheckDefaultBrowser": true | false
  }
}
```
### DefaultDownloadDirectory
Set the default download directory.

You can use ${home} for the native home directory.

**Compatibility:** Cliqz 1.28.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `browser.download.dir`,`browser.download.folderList`

#### Windows
```
Software\Policies\Cliqz\DefaultDownloadDirectory = "${home}\Downloads"
```
#### macOS
```
<dict>
  <key>DefaultDownloadDirectory</key>
  <string>${home}/Downloads</string>
</dict>
```
#### JSON (macOS and Linux)
```
{
  "policies": {
    "DefaultDownloadDirectory": "${home}/Downloads"
}
```
#### JSON (Windows)
```
{
  "policies": {
    "DefaultDownloadDirectory": "${home}\\Downloads"
}
```
### DownloadDirectory
Set and lock the download directory.

You can use ${home} for the native home directory.

**Compatibility:** Cliqz 1.28.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `browser.download.dir`,`browser.download.folderList`,`browser.download.useDownloadDir`

#### Windows
```
Software\Policies\Cliqz\DownloadDirectory = "${home}\Downloads"
```
#### macOS
```
<dict>
  <key>DownloadDirectory</key>
  <string>${home}/Downloads</string>
</dict>
```
#### JSON (macOS and Linux)
```
{
  "policies": {
    "DownloadDirectory": "${home}/Downloads"
}
```
#### JSON (Windows)
```
{
  "policies": {
    "DownloadDirectory": "${home}\\Downloads"
}
```
### EnterprisePoliciesEnabled
Enable policy support on macOS.

**Compatibility:** Cliqz 1.27.0 (macOS only)\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** N/A

#### macOS
```
<dict>
  <key>EnterprisePoliciesEnabled</key>
  <true/>
</dict>
```
### Extensions
Control the installation, uninstallation and locking of extensions.

`Install` is a list of URLs or native paths for extensions to be installed.

`Uninstall` is a list of extension IDs that should be uninstalled if found.

`Locked` is a list of extension IDs that the user cannot disable or uninstall.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `addons`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\Extensions\Install\1 = "https://addons.mozilla.org/firefox/downloads/somefile.xpi"
Software\Policies\Cliqz\Extensions\Install\2 = "//path/to/xpi"
Software\Policies\Cliqz\Extensions\Uninstall\1 = "bad_addon_id@mozilla.org"
Software\Policies\Cliqz\Extensions\Locked\1 = "addon_id@mozilla.org"
```
#### macOS
```
<dict>
  <key>Extensions</key>
  <dict>
    <key>Install</key>
    <array>
      <string>https://addons.mozilla.org/firefox/downloads/somefile.xpi</string>
      <string>//path/to/xpi</string>
    </array>
    <key>Uninstall</key>
    <array>
      <string>bad_addon_id@mozilla.org</string>
    </array>
    <key>Locked</key>
    <array>
      <string>addon_id@mozilla.org</string>
    </array>
  </dict>
</dict>
```
#### JSON


```
{
  "policies": {
    "Extensions": {
      "Install": ["https://addons.mozilla.org/firefox/downloads/somefile.xpi", "//path/to/xpi"],
      "Uninstall": ["bad_addon_id@mozilla.org"],
      "Locked":  ["addon_id@mozilla.org"]
    }
  }
}
```
### ExtensionSettings
Manage all aspects of extensions. This policy is based heavily on the [Chrome policy](https://dev.chromium.org/administrators/policy-list-3/extension-settings-full) of the same name.

This policy maps an extension ID to its configuration. With an extension ID, the configuration will be applied to the specified extension only. A default configuration can be set for the special ID "*", which will apply to all extensions that don't have a custom configuration set in this policy.

To obtain an extension ID, install the extension and go to about:support. You will see the ID in the Extensions section.

The configuration for each extension is another dictionary that can contain the fields documented below.

| Name | Description |
| --- | --- |
| `installation_mode` | Maps to a string indicating the installation mode for the extension. The valid strings are `allowed`,`blocked`,`force_installed`, and `normal_installed`.
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`allowed` | Allows the extension to be installed by the user. This is the default behavior.
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`blocked`| Blocks installation of the extension and removes it from the device if already installed.
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`force_installed`| The extension is automatically installed and can't be removed by the user. This option is not valid for the default configuration and requires an install_url.
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`normal_installed`| The extension is automatically installed but can be disabled by the user. This option is not valid for the default configuration and requires an install_url.
| `install_url`| Maps to a URL indicating where Cliqz can download a force_installed or normal_installed extension. If installing from the addons.mozilla.org, use the following URL (substituting SHORT_NAME from the URL on AMO), https://addons.mozilla.org/firefox/downloads/latest/SHORT_NAME/latest.xpi. If installing frmo the local file system, use a file:/// URL.
| `install_sources` | Each item in this list is an extension-style match pattern. Users will be able to easily install items from any URL that matches an item in this list. Both the location of the *.xpi file and the page where the download is started from (i.e.  the referrer) must be allowed by these patterns. This setting can be used only for the default configuration.
| `allowed_types` | This setting whitelists the allowed types of extension/apps that can be installed in Cliqz. The value is a list of strings, each of which should be one of the following: "extension", "theme", "dictionary", "langpack" This setting can be used only for the default configuration.
| `blocked_install_message` | This maps to a string specifying the error message to display to users if they're blocked from installing an extension. This setting allows you to append text to the generic error message displayed when the extension is blocked. This could be be used to direct users to your help desk, explain why a particular extension is blocked, or something else.

**Compatibility:** Cliqz 1.29.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\ExtensionSettings = '{"*": {"installation_mode": "blocked"}}'
```
#### macOS
```
<dict>
  <key>ExtensionSettings</key>
  <dict>
    <key>*</key>
    <dict>
      <key>blocked_install_message</key>
      <string>Custom error message.</string>
      <key>install_sources</key>
      <array>
        <string>https://addons.mozilla.org/</string>
      </array>
      <key>installation_mode</key>
      <string>blocked</string>
    </dict>
    <key>uBlock0@raymondhill.net</key>
    <dict>
      <key>installation_mode</key>
       <string>force_installed</string>
      <key>install_url</key>
      <string>https://addons.mozilla.org/firefox/downloads/latest/ublock-origin/latest.xpi</string>
    </dict>
  </dict>
</dict>
```
#### JSON
```
{
  "policies": {
    "ExtensionSettings": {
      "*": {
        "blocked_install_message": "Custom error message.",
        "install_sources": ["https://addons.mozilla.org/"],
        "installation_mode": "blocked"
      },
      "uBlock0@raymondhill.net": {
        "installation_mode": "force_installed",
        "install_url": "https://addons.mozilla.org/firefox/downloads/latest/ublock-origin/latest.xpi"
      }
    }
  }
}
```
### ExtensionUpdate
Control extension updates.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `extensions.update.enabled`

#### Windows
```
Software\Policies\Cliqz\ExtensionUpdate = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>ExtensionUpdate</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "ExtensionUpdate": true | false
  }
}
```
### FlashPlugin
Configure the default Flash plugin policy as well as origins for which Flash is allowed.

`Allow` is a list of origins where Flash are allowed.

`Block` is a list of origins where Flash is not allowed.

`Default` determines whether or not Flash is allowed by default.

`Locked` prevents the user from changing Flash preferences.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `permissions.plugin`\
**Preferences Affected:** `plugin.state.flash`

#### Windows
```
Software\Policies\Cliqz\FlashPlugin\Allow\1 = "https://example.org"
Software\Policies\Cliqz\FlashPlugin\Block\1 = "https://example.edu"
Software\Policies\Cliqz\FlashPlugin\Default = 0x1 | 0x0
Software\Policies\Cliqz\FlashPlugin\Locked = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>FlashPlugin</key>
  <dict>
    <key>Allow</key>
    <array>
      <string>http://example.org</string>
    </array>
    <key>Block</key>
    <array>
      <string>http://example.edu</string>
    </array>
    <key>Default</key>
    <true/> | <false/>
    <key>Locked</key>
    <true/> | <false/>
  </dict>
</dict>
```
#### JSON
```
{
  "policies": {
    "FlashPlugin": {
      "Allow": ["http://example.org/"],
      "Block": ["http://example.edu/"],
      "Default": true | false,
      "Locked": true | false
    }
  }
}
```
### HardwareAcceleration
Control hardware acceleration.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `layers.acceleration.disabled`

#### Windows
```
Software\Policies\Cliqz\HardwareAcceleration = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>HardwareAcceleration</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "HardwareAcceleration": true | false
  }
}
```
### InstallAddonsPermission
Configure the default extension install policy as well as origins for extension installs are allowed. This policy does not override turning off all extension installs.

`Allow` is a list of origins where extension installs are allowed.

`Default` determines whether or not extension installs are allowed by default.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `permissions.install`\
**Preferences Affected:** `xpinstall.enabled`

#### Windows
```
Software\Policies\Cliqz\InstallAddonsPermission\Allow\1 = "https://example.org"
Software\Policies\Cliqz\InstallAddonsPermission\Allow\2 = "https://example.edu"
Software\Policies\Cliqz\InstallAddonsPermission\Default = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>InstallAddonsPermission</key>
  <dict>
    <key>Allow</key>
    <array>
      <string>http://example.org</string>
      <string>http://example.edu</string>
    </array>
    <key>Default</key>
    <true/> | <false/>
  </dict>
</dict>
```
#### JSON
```
{
  "policies": {
    "InstallAddonsPermission": {
      "Allow": ["http://example.org/",
                "http://example.edu/"],
      "Default": true | false
    }
  }
}
```
### LocalFileLinks
Enable linking to local files by origin.

**Compatibility:** Cliqz 1.28.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `capability.policy.localfilelinks.*`

#### Windows
```
Software\Policies\Cliqz\LocalFileLinks\1 = "https://example.org"
Software\Policies\Cliqz\LocalFileLinks\2 = "https://example.edu"
```
#### macOS
```
<dict>
  <key>LocalFileLinks</key>
  <array>
    <string>http://example.org</string>
    <string>http://example.edu</string>
  </array>
</dict>
```
#### JSON
```
{
  "policies": {
    "LocalFileLinks": ["http://example.org/",
                       "http://example.edu/"]
  }
}
```
### NoDefaultBookmarks
Disable the creation of default bookmarks.

This policy is only effective if the user profile has not been created yet.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `removeDefaultBookmarks`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\NoDefaultBookmarks = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>NoDefaultBookmarks</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "NoDefaultBookmarks": true | false
  }
}
```
### NetworkPrediction
Enable or disable network prediction (DNS prefetching).

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `network.dns.disablePrefetch`,`network.dns.disablePrefetchFromHTTPS`

#### Windows
```
Software\Policies\Cliqz\NetworkPrediction = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>NetworkPrediction</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "NetworkPrediction": true | false
}
```
### OfferToSaveLogins
Control whether or not Cliqz offers to save passwords.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `dontRememberPasswords`\
**Preferences Affected:** `signon.rememberSignons`

#### Windows
```
Software\Policies\Cliqz\OfferToSaveLogins = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>OfferToSaveLogins</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "OfferToSaveLogins": true | false
  }
}
```
### OverrideFirstRunPage
Override the first run page. If the value is blank, no first run page is displayed.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `welcomePage`,`noWelcomePage`\
**Preferences Affected:** `startup.homepage_welcome_url`

#### Windows
```
Software\Policies\Cliqz\OverrideFirstRunPage = "http://example.org"
```
#### macOS
```
<dict>
  <key>OverrideFirstRunPage</key>
  <string>http://example.org</string>
</dict>
```
#### JSON
```
{
  "policies": {
    "OverrideFirstRunPage": "http://example.org"
}
```
### OverridePostUpdatePage
Override the upgrade page. If the value is blank, no upgrade page is displayed.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `upgradePage`,`noUpgradePage`\
**Preferences Affected:** `startup.homepage_override_url`

#### Windows
```
Software\Policies\Cliqz\OverridePostUpdatePage = "http://example.org"
```
#### macOS
```
<dict>
  <key>OverridePostUpdatePage</key>
  <string>http://example.org</string>
</dict>
```
#### JSON
```
{
  "policies": {
    "OverridePostUpdatePage": "http://example.org"
}
```
### Permissions
Set permissions associated with camera, microphone, location, and notifications

`Allow` is a list of origins where the feature is allowed.

`Block` is a list of origins where the feature is not allowed.

`BlockNewRequests` determines whether or not new requests can be made for the feature.

`Locked` prevents the user from changing preferences for the feature.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `permissions.default.camera`,`permissions.default.microphone`,`permissions.default.geo`,`permissions.default.desktop-notification`

#### Windows
```
Software\Policies\Cliqz\Permissions\Camera\Allow\1 = "https://example.org"
Software\Policies\Cliqz\Permissions\Camera\Block\1 = "https://example.edu"
Software\Policies\Cliqz\Permissions\Camera\BlockNewRequests = 0x1 | 0x0
Software\Policies\Cliqz\Permissions\Camera\Locked = 0x1 | 0x0
Software\Policies\Cliqz\Permissions\Microphone\Allow\1 = "https://example.org"
Software\Policies\Cliqz\Permissions\Microphone\Block\1 = "https://example.edu"
Software\Policies\Cliqz\Permissions\Microphone\BlockNewRequests = 0x1 | 0x0
Software\Policies\Cliqz\Permissions\Microphone\Locked = 0x1 | 0x0
Software\Policies\Cliqz\Permissions\Location\Allow\1 = "https://example.org"
Software\Policies\Cliqz\Permissions\Location\Block\1 = "https://example.edu"
Software\Policies\Cliqz\Permissions\Location\BlockNewRequests = 0x1 | 0x0
Software\Policies\Cliqz\Permissions\Location\Locked = 0x1 | 0x0
Software\Policies\Cliqz\Permissions\Notifications\Allow\1 = "https://example.org"
Software\Policies\Cliqz\Permissions\Notifications\Block\1 = "https://example.edu"
Software\Policies\Cliqz\Permissions\Notifications\BlockNewRequests = 0x1 | 0x0
Software\Policies\Cliqz\Permissions\Notifications\Locked = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>Permissions</key>
  <dict>
    <key>Camera</key>
    <dict>
      <key>Allow</key>
      <array>
        <string>https://example.org</string>
      </array>
      <key>Block</key>
      <array>
        <string>https://example.edu</string>
      </array>
      <key>BlockNewRequests</key>
      <true/>
      <key>Locked</key>
      <true/>
    </dict>
    <key>Microphone</key>
    <dict>
      <key>Allow</key>
      <array>
        <string>https://example.org</string>
      </array>
      <key>Block</key>
      <array>
        <string>https://example.edu</string>
      </array>
      <key>BlockNewRequests</key>
      <true/>
      <key>Locked</key>
      <true/>
    </dict>
    <key>Location</key>
    <dict>
      <key>Allow</key>
      <array>
        <string>https://example.org</string>
      </array>
      <key>Block</key>
      <array>
        <string>https://example.edu</string>
      </array>
      <key>BlockNewRequests</key>
      <true/>
      <key>Locked</key>
      <true/>
    </dict>
    <key>Notifications</key>
    <dict>
      <key>Allow</key>
      <array>
        <string>https://example.org</string>
      </array>
      <key>Block</key>
      <array>
        <string>https://example.edu</string>
      </array>
      <key>BlockNewRequests</key>
      <true/>
      <key>Locked</key>
      <true/>
    </dict>
  </dict>
</dict>
```
#### JSON
```
{
  "policies": {
    "Permissions": {
      "Camera": {
        "Allow": ["https://example.org"],
        "Block": ["https://example.edu"],
        "BlockNewRequests": true | false,
        "Locked": true | false
      },
      "Microphone": {
        "Allow": ["https://example.org"],
        "Block": ["https://example.edu"],
        "BlockNewRequests": true | false,
        "Locked": true | false
      },
      "Location": {
        "Allow": ["https://example.org"],
        "Block": ["https://example.edu"],
        "BlockNewRequests": true | false,
        "Locked": true | false
      },
      "Notifications": {
        "Allow": ["https://example.org"],
        "Block": ["https://example.edu"],
        "BlockNewRequests": true | false,
        "Locked": true | false
      }
    }
  }
}
```
### PopupBlocking
Configure the default pop-up window policy as well as origins for which pop-up windows are allowed.

`Allow` is a list of origins where popup-windows are allowed.

`Default` determines whether or not pop-up windows are allowed by default.

`Locked` prevents the user from changing pop-up preferences.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `permissions.popup`\
**Preferences Affected:** `dom.disable_open_during_load`

#### Windows
```
Software\Policies\Cliqz\PopupBlocking\Allow\1 = "https://example.org"
Software\Policies\Cliqz\PopupBlocking\Allow\2 = "https://example.edu"
Software\Policies\Cliqz\PopupBlocking\Default = 0x1 | 0x0
Software\Policies\Cliqz\PopupBlocking\Locked = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>PopupBlocking</key>
  <dict>
    <key>Allow</key>
    <array>
      <string>http://example.org</string>
      <string>http://example.edu</string>
    </array>
    <key>Default</key>
    <true/> | <false/>
    <key>Locked</key>
    <true/> | <false/>
  </dict>
</dict>
```
#### JSON
```
{
  "policies": {
    "PopupBlocking": {
      "Allow": ["http://example.org/",
                "http://example.edu/"],
      "Default": true | false,
      "Locked": true | false
    }
  }
}
```
### Preferences
Set and lock certain preferences.

**Compatibility:** See below\
**CCK2 Equivalent:** `preferences`\
**Preferences Affected:** See below

| Preference | Type | Compatibility | Default
| --- | --- | --- | ---
| app.update.auto | boolean | Cliqz 1.28.0 | true
| &nbsp;&nbsp;&nbsp;&nbsp;If false, Cliqz doesn't automatically install update.
| browser.cache.disk.enable | boolean | Cliqz 1.28.0 | true
| &nbsp;&nbsp;&nbsp;&nbsp;If false, don't store cache on the hard drive.
| browser.cache.disk.parent_directory | string | Cliqz 1.28.0 | Profile temporary directory
| &nbsp;&nbsp;&nbsp;&nbsp;If set, changes the location of the disk cache.
| browser.fixup.dns_first_for_single_words | boolean | Cliqz 1.28.0 | false
| &nbsp;&nbsp;&nbsp;&nbsp;If true, single words are sent to DNS, not directly to search.
| browser.search.update | boolean | Cliqz 1.28.0 | true
| &nbsp;&nbsp;&nbsp;&nbsp;If false, updates for search engines are not checked.
| browser.tabs.warnOnClose | boolean | Cliqz 1.28.0 | true
| &nbsp;&nbsp;&nbsp;&nbsp;If false, there is no warning when the browser is closed.
| browser.urlbar.suggest.bookmark | boolean | Cliqz 1.28.0 | true
| &nbsp;&nbsp;&nbsp;&nbsp;If false, bookmarks aren't suggested when typing in the URL bar.
| browser.urlbar.suggest.history | boolean | Cliqz 1.28.0 | true
| &nbsp;&nbsp;&nbsp;&nbsp;If false, history isn't suggested when typing in the URL bar.
| browser.urlbar.suggest.openpage | boolean | Cliqz 1.28.0 | true
| &nbsp;&nbsp;&nbsp;&nbsp;If false, open tabs aren't suggested when typing in the URL bar.
| datareporting.policy.dataSubmissionPolicyBypassNotification | boolean | Cliqz 1.28.0 | false
| &nbsp;&nbsp;&nbsp;&nbsp;If true, don't show the privacy policy tab on first run.
| dom.disable_window_flip | boolean | Cliqz 1.28.0 | true
| &nbsp;&nbsp;&nbsp;&nbsp;If false, web pages can focus and activate windows.
| dom.disable_window_move_resize | boolean | Cliqz 1.28.0 | false
| &nbsp;&nbsp;&nbsp;&nbsp;If true, web pages can't move or resize windows.
| dom.event.contextmenu.enabled | boolean | Cliqz 1.28.0 | true
| &nbsp;&nbsp;&nbsp;&nbsp;If false, web pages can't override context menus.
| dom.keyboardevent.keypress.hack.dispatch_non_printable_keys.addl | string | Cliqz 1.28.0 | N/A
| &nbsp;&nbsp;&nbsp;&nbsp;See https://support.mozilla.org/en-US/kb/dom-events-changes-introduced-firefox-66
| dom.keyboardevent.keypress.hack.use_legacy_keycode_and_charcode.addl | string | Cliqz 1.28.0 | N/A
| &nbsp;&nbsp;&nbsp;&nbsp;See https://support.mozilla.org/en-US/kb/dom-events-changes-introduced-firefox-66
| extensions.getAddons.showPane | boolean | Cliqz 1.28.0 | N/A
| &nbsp;&nbsp;&nbsp;&nbsp;If false, the Recommendations tab is not displayed in the Add-ons Manager.
| media.gmp-gmpopenh264.enabled | boolean | Cliqz 1.28.0 | true
| &nbsp;&nbsp;&nbsp;&nbsp;If false, the OpenH264  plugin is not downloaded.
| media.gmp-widevinecdm.enabled | boolean | Cliqz 1.28.0 | true
| &nbsp;&nbsp;&nbsp;&nbsp;If false, the Widevine plugin is not downloaded.
| network.dns.disableIPv6 | boolean | Cliqz 1.28.0 | false
| &nbsp;&nbsp;&nbsp;&nbsp;If true, IPv6 DNS lokoups are disabled.
| network.IDN_show_punycode | boolean | Cliqz 1.28.0 | false
| &nbsp;&nbsp;&nbsp;&nbsp;If true, display the punycode version of internationalized domain names.
| places.history.enabled | boolean | Cliqz 1.28.0 | true
| &nbsp;&nbsp;&nbsp;&nbsp;If false, history is not enabled.
| security.default_personal_cert | string | Cliqz 1.28.0 | Ask Every Time
| &nbsp;&nbsp;&nbsp;&nbsp;If set to Select Automatically, Cliqz automatically chooses the default personal certificate.
| security.ssl.errorReporting.enabled | boolean | Cliqz 1.28.0 | true
| &nbsp;&nbsp;&nbsp;&nbsp;If false, SSL errors cannot be sent to Mozilla.
| ui.key.menuAccessKeyFocuses | boolean | Cliqz 1.28.0 | true
| &nbsp;&nbsp;&nbsp;&nbsp;If false, the Alt key doesn't show the menubar on Windows.
#### Windows
```
Software\Policies\Cliqz\Preferences\boolean_preference_name = 0x1 | 0x0
Software\Policies\Cliqz\Preferences\string_preference_name = "string_value"
```
#### macOS
```
<dict>
  <key>Preferences</key>
  <dict>
    <key>boolean_preference_name</key>
    <true/> | <false/>
    <key>string_preference_name</key>
    <string>string_value</string>
  </dict>
</dict>
```
#### JSON
```
{
  "policies": {
    "Preferences": {
      "boolean_preference_name": true | false,
      "string_preference_name": "string_value"
    }
  }
}
```
### PromptForDownloadLocation
Ask where to save each file before downloading.

**Compatibility:** Cliqz 1.28.0\
**CCK2 Equivalent:** N/A
**Preferences Affected:** `browser.download.useDownloadDir`

#### Windows
```
Software\Policies\Cliqz\PromptForDownloadLocation = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>PromptForDownloadLocation</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "PromptForDownloadLocation": true | false
  }
}
```
### Proxy
Configure proxy settings. These settings correspond to the connection settings in Cliqz preferences.
To specify ports, append them to the hostnames with a colon (:).

`Mode` is the proxy method being used.

`Locked` is whether or not proxy settings can be changed.

`HTTPProxy` is the HTTP proxy server.

`UseHTTPProxyForAllProtocols` is whether or not the HTTP proxy should be used for all other proxies.

`SSLProxy` is the SSL proxy server.

`FTPProxy` is the FTP proxy server.

`SOCKSProxy` is the SOCKS proxy server

`SOCKSVersion` is the SOCKS version (4 or 5)

`Passthrough` is list of hostnames or IP addresses that will not be proxied. Use `<local>` to bypass proxying for all hostnames which do not contain periods.

`AutoConfigURL` is a  URL for proxy configuration (only used if Mode is autoConfig).

`AutoLogin` means do not prompt for authentication if password is saved.

`UseProxyForDNS` to use proxy DNS when using SOCKS v5.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `networkProxy*`\
**Preferences Affected:** `network.proxy.type`,`network.proxy.autoconfig_url`,`network.proxy.socks_remote_dns`,`signon.autologin.proxy`,`network.proxy.socks_version`,`network.proxy.no_proxies_on`,`network.proxy.share_proxy_settings`,`network.proxy.http`,`network.proxy.http_port`,`network.proxy.ftp`,`network.proxy.ftp_port`,`network.proxy.ssl`,`network.proxy.ssl_port`,`network.proxy.socks`,`network.proxy.socks_port`

#### Windows
```
Software\Policies\Cliqz\Proxy\Mode = "none", "system", "manual", "autoDetect", "autoConfig"
Software\Policies\Cliqz\Proxy\Locked = 0x1 | 0x0
Software\Policies\Cliqz\Proxy\HTTPProxy = https://httpproxy.example.com
Software\Policies\Cliqz\Proxy\UseHTTPProxyForAllProtocols = 0x1 | 0x0
Software\Policies\Cliqz\Proxy\SSLProxy = https://sslproxy.example.com
Software\Policies\Cliqz\Proxy\FTPProxy = https://ftpproxy.example.com
Software\Policies\Cliqz\Proxy\SOCKSProxy = https://socksproxy.example.com
Software\Policies\Cliqz\Proxy\SOCKSVersion = 0x4 | 0x5
Software\Policies\Cliqz\Proxy\Passthrough = <local>
Software\Policies\Cliqz\Proxy\AutoConfigURL = URL_TO_AUTOCONFIG
Software\Policies\Cliqz\Proxy\AutoLogin = 0x1 | 0x0
Software\Policies\Cliqz\Proxy\UseProxyForDNS = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>Proxy</key>
  <dict>
    <key>Mode</key>
    <string>none | system | manual | autoDetect| autoConfig</string>
    <key>Locked</key>
    <true> | </false>
    <key>HTTPProxy</key>
    <string>https://httpproxy.example.com</string>
    <key>UseHTTPProxyForAllProtocols</key>
    <true> | </false>
    <key>SSLProxy</key>
    <string>https://sslproxy.example.com</string>
    <key>FTPProxy</key>
    <string>https://ftpproxy.example.com</string>
    <key>SOCKSProxy</key>
    <string>https://socksproxy.example.com</string>
    <key>SOCKSVersion</key>
    <string>4 | 5</string>
    <key>Passthrough</key>
    <string>&lt;local>&gt;</string>
    <key>AutoConfigURL</key>
    <string>URL_TO_AUTOCONFIG</string>
    <key>AutoLogin</key>
    <true> | </false>
    <key>UseProxyForDNS</key>
    <true> | </false>
  </dict>
</dict>
```
#### JSON
```
{
  "policies": {
    "Proxy": {
      "Mode": "none", "system", "manual", "autoDetect", "autoConfig",
      "Locked": [true, false],
      "HTTPProxy": "hostname",
      "UseHTTPProxyForAllProtocols": [true, false],
      "SSLProxy": "hostname",
      "FTPProxy": "hostname",
      "SOCKSProxy": "hostname",
      "SOCKSVersion": 4 | 5
      "Passthrough": "<local>",
      "AutoConfigURL": "URL_TO_AUTOCONFIG",
      "AutoLogin":  [true, false],
      "UseProxyForDNS": [true, false]
    }
  }
}
```
### SanitizeOnShutdown (Selective)
Clear data on shutdown. Choose from Cache, Cookies, Download History, Form & Search History, Browsing History, Active Logins, Site Preferences and Offline Website Data.

**Compatibility:** Cliqz 1.28.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `privacy.sanitize.sanitizeOnShutdown`,`privacy.clearOnShutdown.cache`,`privacy.clearOnShutdown.cookies`,`privacy.clearOnShutdown.downloads`,`privacy.clearOnShutdown.formdata`,`privacy.clearOnShutdown.history`,`privacy.clearOnShutdown.sessions`,`privacy.clearOnShutdown.siteSettings`,`privacy.clearOnShutdown.offlineApps`
#### Windows
```
Software\Policies\Cliqz\SanitizeOnShutdown\Cache = 0x1 | 0x0
Software\Policies\Cliqz\SanitizeOnShutdown\Cookies = 0x1 | 0x0
Software\Policies\Cliqz\SanitizeOnShutdown\Downloads = 0x1 | 0x0
Software\Policies\Cliqz\SanitizeOnShutdown\FormData = 0x1 | 0x0
Software\Policies\Cliqz\SanitizeOnShutdown\History = 0x1 | 0x0
Software\Policies\Cliqz\SanitizeOnShutdown\Sessions = 0x1 | 0x0
Software\Policies\Cliqz\SanitizeOnShutdown\SiteSettings = 0x1 | 0x0
Software\Policies\Cliqz\SanitizeOnShutdown\OfflineApps = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>SanitizeOnShutdown</key>
  <dict>
    <key>Cache</key>
    <true/> | <false/>
    <key>Cookies</key>
    <true/> | <false/>
    <key>Downloads</key>
    <true/> | <false/>
    <key>FormData</key>
    <true/> | <false/>
    <key>History</key>
    <true/> | <false/>
    <key>Sessions</key>
    <true/> | <false/>
    <key>SiteSettings</key>
    <true/> | <false/>
    <key>OfflineApps</key>
    <true/> | <false/>
  </dict>
</dict>
```
#### JSON
```
{
  "policies": {
    "SanitizeOnShutdown": {
      "Cache": true | false,
      "Cookies": true | false,
      "Downloads": true | false,
      "FormData": true | false,
      "History": true | false,
      "Sessions": true | false,
      "SiteSettings": true | false,
      "OfflineApps": true | false
    }
  }
}
```
### SanitizeOnShutdown (All)
Clear all data on shutdown, including Browsing & Download History, Cookies, Active Logins, Cache, Form & Search History, Site Preferences and Offline Website Data.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `privacy.sanitize.sanitizeOnShutdown`,`privacy.clearOnShutdown.cache`,`privacy.clearOnShutdown.cookies`,`privacy.clearOnShutdown.downloads`,`privacy.clearOnShutdown.formdata`,`privacy.clearOnShutdown.history`,`privacy.clearOnShutdown.sessions`,`privacy.clearOnShutdown.siteSettings`,`privacy.clearOnShutdown.offlineApps`
#### Windows
```
Software\Policies\Cliqz\SanitizeOnShutdown = 0x1 | 0x0
```
#### macOS
```
<dict>
  <key>SanitizeOnShutdown</key>
  <true/> | <false/>
</dict>
```
#### JSON
```
{
  "policies": {
    "SanitizeOnShutdown": true | false
  }
}
```
### SecurityDevices

Install PKCS #11 modules.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** `certs.devices`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\SecurityDevices\NAME_OF_DEVICE = PATH_TO_LIBRARY_FOR_DEVICE
```
#### macOS
```
<dict>
  <key>SecurityDevices</key>
  <dict>
    <key>NAME_OF_DEVICE</key>
    <string>PATH_TO_LIBRARY_FOR_DEVICE</string>
  </dict>
</dict>
```

#### JSON
```
{
  "policies": {
    "SecurityDevices": {
      "NAME_OF_DEVICE": "PATH_TO_LIBRARY_FOR_DEVICE"
    }
  }
}
```
### SSLVersionMax

Set and lock the maximum version of TLS.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `security.tls.version.max`

#### Windows
```
Software\Policies\Cliqz\SSLVersionMax = "tls1" | "tls1.1" | "tls1.2" | "tls1.3"
```
#### macOS
```
<dict>
  <key>SSLVersionMax</key>
  <string>tls1 | tls1.1 | tls1.2 | tls1.3</string>
</dict>
```

#### JSON
```
{
  "policies": {
    "SSLVersionMax": "tls1" | "tls1.1" | "tls1.2" | "tls1.3"
  }
}
```
### SSLVersionMin

Set and lock the minimum version of TLS.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `security.tls.version.min`

#### Windows
```
Software\Policies\Cliqz\SSLVersionMin = "tls1" | "tls1.1" | "tls1.2" | "tls1.3"
```
#### macOS
```
<dict>
  <key>SSLVersionMin</key>
  <string>tls1 | tls1.1 | tls1.2 | tls1.3</string>
</dict>
```

#### JSON
```
{
  "policies": {
    "SSLVersionMin": "tls1" | "tls1.1" | "tls1.2" | "tls1.3"
  }
}
```
### Startup
Configure the default homepage and how Cliqz starts.

`Homepage` specify what you want to do on Cliqz startup with one of three possible options: open FreshTab is default option, open homepage(s) or open blank tab.

`RestoreLastSession` turn on if you need to restore last session on startup.

`ShowHomepage` turn on if you want to open homepage(s) on startup.

`Locked` prevents the user from changing startup preferences.

`URLs` specify list of URL(s) which will be counted as homepage(s).

**Compatibility:** Cliqz 1.27.0\
**Preferences Affected:** `browser.startup.homepage`,`browser.startup.restoreTabs`,`browser.startup.addFreshTab`

#### Windows
```
Software\Policies\Cliqz\Startup\Homepage ="default", "urls", "blank"
Software\Policies\Cliqz\Startup\Locked = 0x1 | 0x0
Software\Policies\Cliqz\Startup\RestoreLastSession = 0x1 | 0x0
Software\Policies\Cliqz\Startup\ShowHomepage = 0x1 | 0x0
Software\Policies\Cliqz\Startup\URLs\1 = "https://example.org"
Software\Policies\Cliqz\Startup\URLs\2 = "https://example.edu"
```
#### JSON
```
{
  "policies": {
    "Startup": {
      "RestoreLastSession": true | false,
      "ShowHomepage": true | false,
      "Locked": true | false,
      "URLs": ["http://example.org/",
               "http://example.edu/"],
      "Homepage": ["default", "urls", "blank"]
    }
  }
}
```
### SupportMenu
Add a menuitem to the help menu for specifying support information.

**Compatibility:** Cliqz 1.28.1\
**CCK2 Equivalent:** helpMenu\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\SupportMenu\Title = "Support Menu"
Software\Policies\Cliqz\SupportMenu\URL = "http://example.com/support"
Software\Policies\Cliqz\SupportMenu\Title = "S"
```
#### macOS
```
<dict>
  <key>SupportMenu</key>
  <dict>
    <key>Title</key>
    <string>SupportMenu</string>
    <key>URL</key>
    <string>http://example.com/support</string>
    <key>AccessKey</key>
    <string>S</string>
  </dict>
</dict>
```
#### JSON
```
{
  "policies": {
    "SupportMenu": {
      "Title": "Support Menu",
      "URL": "http://example.com/support",
      "AccessKey": "S"
    }
  }
}
```
### WebsiteFilter
Block websites from being visited. The parameters take an array of Match Patterns, as documented in https://developer.mozilla.org/en-US/Add-ons/WebExtensions/Match_patterns. Only http/https addresses are supported at the moment. The arrays are limited to 1000 entries each.

**Compatibility:** Cliqz 1.27.0\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Cliqz\WebsiteFilters\Block\1 = "<all_urls>"
Software\Policies\Cliqz\WebsiteFilters\Exceptions\1 = "http://example.org/*"
```
#### macOS
```
<dict>
  <key>WebsiteFilter</key>
  <dict>
    <key>Block</key>
    <array>
      <string><all_urls></string>
    </array>
    <key>Exceptions</key>
    <array>
      <string>http://example.org/*</string>
    </array>
  </dict>

</dict>
```
#### JSON
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
