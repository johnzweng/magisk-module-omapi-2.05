# Magisk Module: **Smartcard Service**

### What's this:

This is a module for the [Magisk Framework](http://forum.xda-developers.com/apps/magisk/official-magisk-v7-universal-systemless-t3473445). You need to have the Magisk framework (which is not made by me) installed on your phone.

### What this module does:
This module installs the **SmartcardService** system application, from this [Github release](https://github.com/johnzweng/platform_packages_apps_SmartCardService/releases/tag/jz_android_6.0_OMAPI-2.05).

SmartcardService is the implementation of the Open Mobile API which is not part
of the standard Android API (Google doesn't support it) but is needed by apps
which need APDU access to the UICC (for example to use the UICC as Secure
Element).

### Contents:
In detail this module adds the following files (and necessary directories):

- `/system/etc/permissions/org.simalliance.openmobileapi.xml`
- `/system/framework/org.simalliance.openmobileapi.jar`
- `/system/priv-app/SmartcardService/SmartcardService.apk`

----

#### Side Note regarding NFC config:
To make NFC offhost transaction work (so that NFC transactions get routed
directly to the UICC and not to the android system) on some phones configuration
files for the NFC chip need to be modified.

These files normally (on most phones) are placed under `/system/etc/` and
are often named like this:

- libnfc-brcm.conf
- *and/or:* libnfc-nxp.conf
- *and/or:* libnfc-brcm-20795a10.conf
- ... (*or similiar*)

Look through these files and look for settings regarding offhost routing
to the UICC (SIM card).

But these files are specific per device, so **these files are NOT included
in this module**.

Also the device **must have a physical SWP connection between the NFC chipset
and the UICC slot**, otherwise NFC offhost transaction using a a SWP enabled
UICC can never work (no matter what you change in the NFC config files).
