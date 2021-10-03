## USAGE

The contents of this repo are only meant to be used on the HP Probook 450 G5 i5-8250u.
This is the only existing Opencore config for this model of the G5 and must only be used to boot Big Sur.

## PREPARATION
    
The following are required to prepare the Opencore config for use:
        
1. genSMBIOS - without it the Opencore config will not work.
2. ProperTree -  Needed to edit the config.plist file.
3. A lot of patience.

## INSTALLATION
    
This assumes that you are already running macOS and that you've already copied this repo to your EFI volume.

1. Download genSMBIOS. and geneate the details required for the Opencore config.
2. Download ProperTree.
3. Open the config.plist file in ProperTree and navigate to the `PlatformInfo` section.
4. Replace the `PlatformInfo` section with the data obtained from genSMBIOS.
For easy identification only chenage the sections hat say `GenerateYourOwn` in the config.plist file.



The section you're editing looks like this.

```
<key>PlatformInfo</key>
<dict>
<key>Automatic</key>
<true/>
<key>CustomMemory</key>
<false/>
<key>Generic</key>
<dict>
    <key>AdviseFeatures</key>
 	<false/>
 	<key>MLB</key>
 	<string>GenerateYourOwn</string>
 	<key>MaxBIOSVersion</key>
 	<false/>
 	<key>ProcessorType</key>
 	<integer>0</integer>
 	<key>ROM</key>
 	<data>GenerateYourOwn</data>
 	<key>SpoofVendor</key>
 	<true/>
 	<key>SystemMemoryStatus</key>
 	<string>Auto</string>
 	<key>SystemProductName</key>
 	<string>iMac18,1</string>
 	<key>SystemSerialNumber</key>
 	<string>GenerateYourOwn</string>
 	<key>SystemUUID</key>
	<string>GenerateYourOwn</string>
</dict>
```
         
6. After that take a snapshot of the OC folder by clicking `file` -> `OC snapshot` then saving and doing the same process again but this time choose `OC Clean snapshot`.

## WHAT WORKS
- WiFi
- Bluetooth
- Touchpad
- Volume control
- Keyboard
- Screen brightness
- Screen resolution
- iServices (SMBIOS dependant).

## WHAT DOES NOT WORK
- Airdrop
- Airplay