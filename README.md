# Abeta for Shopware 6

The official Shopware 6 plugin for Abeta.
Offer OCI and cXML PunchOut quickly and easily with Abeta. Connect with procurement systems / ERPs such as Coupa, Oracle and Sap Ariba. 
Increase the turnover of existing customers or acquire new customers with the help of B2B connections.

## Requirements

- Shopware 6.6

## Installation

#### Install via Composer

1. Go to your Shopware 6 root folder

2. Enter the following command to install the plugin:

   ```
   composer require abeta-io/shopware6
   ```

3. Enter the following commands to install and activate the plugin:

   ```
   bin/console plugin:refresh
   bin/console plugin:install --activate AbetaPunchOut
   bin/console cache:clear
   ```

4. Compile the storefront theme so the plugin's storefront assets are loaded:

   ```
   bin/console theme:compile
   ```

#### Install from GitHub

1. Download the zip package from https://github.com/abeta-io/shopware6 by clicking "Code" and selecting "Download ZIP" from the dropdown.

2. Create a custom/plugins/AbetaPunchOut directory in your Shopware 6 root folder.

3. Extract the contents from the "shopware6" zip and copy or upload everything to custom/plugins/AbetaPunchOut

4. Run the following commands from the Shopware 6 root folder to install and activate the plugin:

   ```
   bin/console plugin:refresh
   bin/console plugin:install --activate AbetaPunchOut
   bin/console cache:clear
   bin/console theme:compile
   ```

## Upgrading from MagmodulesAbeta
 
> **Important:** The plugin's technical name has changed from `MagmodulesAbeta` to `AbetaPunchOut`. Shopware treats this as a completely new plugin, so it is **not** a regular update. Follow the steps below on every existing shop before installing the new version. Skipping them can cause the migrations to fail and leaves the old configuration behind.
 
1. **Write down your current settings.** Open the MagmodulesAbeta plugin configuration in the Shopware Administration and note all values (API key, etc.). These settings are **not** carried over and must be entered again after the upgrade.
2. **Fully uninstall MagmodulesAbeta, without keeping its data.** Do this *before* installing or updating to the new package.
   Via the command line (by default this removes all plugin data; do **not** add `--keep-user-data`):
```
   bin/console plugin:uninstall MagmodulesAbeta
   bin/console cache:clear
```
 
   Or via the Administration: go to *Extensions > My extensions*, uninstall MagmodulesAbeta and make sure the option to keep the plugin data is **not** selected.
 
3. **Remove the old plugin files.** If the plugin was installed manually, delete the `custom/plugins/MagmodulesAbeta` directory. If it was installed via Composer, the old files are replaced when you install the new version in the next step.
4. **Install AbetaPunchOut** by following the [Installation](#installation) steps below.
5. **Re-enter your settings** in the AbetaPunchOut plugin configuration using the values you noted in step 1.
