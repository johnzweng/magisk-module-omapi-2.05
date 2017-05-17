# Magisk Module: **Smartcard Service**

### What's this:

This is a module for the [Magisk Framework](http://forum.xda-developers.com/apps/magisk/official-magisk-v7-universal-systemless-t3473445). You need to have the Magisk framework (which is not made by me) installed on your phone.

### What this module does:
This module installs the **SmartcardService** system application, from this [Github account](https://github.com/johnzweng/platform_packages_apps_SmartCardService/releases/tag/jz_android_6.0_OMAPI-2.05).

SmartcardService is the implementation of the Open Mobile API which is not part
of the standard Android API (Google doesn't support it) but is needed by apps
which need to access the SIM card (for example to use the SIM card as Secure
Element).

### Contents:
This module adds the following files (and necessary directories):

- `/system/etc/permissions/org.simalliance.openmobileapi.xml`
- `/system/framework/org.simalliance.openmobileapi.jar`
- `/system/priv-app/SmartcardService/SmartcardService.apk`
