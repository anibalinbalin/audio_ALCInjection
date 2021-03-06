audio_ALCInjection
============
OS X Realtek ALC885 through ALC1150 Onboard Audio

This guide enables OS X Realtek ALC onboard audio on Intel based motherboards with OS X. The Realtek AppleHDA.kext only works with the codec the kext was edited for and patches the installed native AppleHDA.kext.  Realtek ALC AppleHDA.kext supports Mavericks (M) and Mountain Lion (ML).

Realtek ALC AppleHDA Guides:
[Guide] Add HDEF-Clover.pdf
[Guide] Add or Edit HDEF-dsdt.pdf
[Guide] Add HDEF-kext.pdf
[Guide] Add HDEF-ssdt.pdf
M-Realtek_ALC_AppleHDA_Capabilitiess.pdf.zip
M-Realtek_ALC_AppleHDA_Customization.pdf.zip
M-Realtek_ALC_AppleHDA_Screenshots.pdf.zip
M-Realtek_ALC_AppleHDA-No_Audio.pdf.zip

Realtek ALC AppleHDA Tools:
IORegistryExplorer_v2.1.zip
Property_List_Editor_v5.3.zip
zlib_terminal.zip

Note: ML-Realtek ALC AppleHDA docs moved to folder above

In OS X, The Realtek ALC AppleHDA.kext supports 7 Realtek audio codecs:
ALC885, ALC887, ALC888, ALC889, ALC892, ALC898, ALC1150/10.8.5 and newer

Three Realtek ALC AppleHDA.kext Audio_IDs, select one
Audio_ID: 1 supports 5 and 6 port ALC8xx onboard and/or HD5K/AMD/Nvidia HDMI audio  
Audio_ID: 2 supports 3 port ALC8xx onboard and/or HD5K/AMD/Nvidia HDMI audio
Audio_ID: 3 supports 3, 5 and 6 port ALC8xx onboard HD4K/HD3K HDMI audio
		with or without AMD/Nvidia HDMI audio
Audio_IDs: 1 and 2 support analog 5.1 surround sound, 3 does not
Audio_IDs: 1, 2 and 3 require HDMI audio dsdt edits for HDMI audio
Audio_ID: 3, not supported with ALC885 and ALC1150.

Note: The native AppleHDA.kext supports HDMI audio (dsdt edits required) even with an unsupported onboard audio codec using Audio ID: 1. 

Four Audio ID Injection techniques for the Realtek ALC AppleHDA.kext, select one
1. HDEF/kext/No dsdt/audio enabler = Audio_ID, see [Guide]_Add_HDEF-kext.pdf
https://github.com/toleda/audio_kext_enabler
1a. Audio_ID = 1/HDAEnabler1.kext.zip 
1b. Audio_ID = 2/HDAEnabler2.kext.zip
1c. Audio_ID = 3/NA
2. HDEF/dsdt/layout-id = Audio_ID, see [Guide]_Add_or_edit_HDEF-dsdt.pdf
https://github.com/toleda/audio_ALCInjection
2a. Audio_ID = 1/layout-id: 0x01, 0x00, 0x00, 0x00, 0x00
2b. Audio_ID = 2/layout-id: 0x02, 0x00, 0x00, 0x00, 0x00
2c. Audio_ID = 3, see dsdt/HD3K/HD4K HDMI audio
3. HDEF/lssdt/ayout-id = Audio_ID, see [Guide]_Add_HDEF-ssdt.pdf
https://github.com/toleda/audio_ssdt_enabler
3a. Audio_ID = 1/audio_ssdt-hdae-1.zip
3b. Audio_ID = 2/audio_ssdt-hdae-2.zip
3c. Audio_ID = 3, see ssdt/HD3K/HD4K HDMI audio
4. HDEF/Clover/Config.plist/Devices, see [Guide]_Add_HDEF-Clover.pdf
https://github.com/toleda/audio_ALCInjection
4a. Audio_ID = 1/Audio/Inject=1
4b. Audio_ID = 2/Audio/Inject=2
4c. Audio_ID = 3/Audio/Inject=3
5. Ghameleon/Customize/Setting/HDEF Layout/
https://github.com/toleda/audio_ALCInjection
5a. Audio_ID = 1/LayoutID=1
5b. Audio_ID = 2/LayoutID=2
5c. Audio_ID = 3/NA

Verification
1. Restart
2. IORegistryExplorer
2a. Search: HDEF
2b. Locate: layout-id (right pane, scroll down)
2c. Verify:
<01 00 00 00> or
<02 00 00 00>

Once the Realtek ALC AppleHDA audio is enabled, select the appropriate codec
1. https://github.com/toleda/audio_ALC885
2. https://github.com/toleda/audio_ALC887
3. https://github.com/toleda/audio_ALC888
4. https://github.com/toleda/audio_ALC889
5. https://github.com/toleda/audio_ALC892
6. https://github.com/toleda/audio_ALC898
7. https://github.com/toleda/audio_ALC1150
 
Problem Reporting
1. Motherboard/BIOS version/processor/graphics/OS and version
2. Copy of dsdt (if edited)
3. Copy of IORegistryExplorer

Troubleshooting/Post w/attachments 2 and 3, above
1. Mavericks/10.9
1a. http://www.tonymacx86.com/audio/112461-mavericks-no-audio-realtek-alc-applehda.html
1b. http://www.insanelymac.com/forum/topic/292999-mavericks-applehda-hdmi-audio/
2. Mountain Lion/10.8
2a.http://www.tonymacx86.com/audio/76309-mountain-lion-multibeast-no-audio-solutions-problem-reporting.html
2b. http://www.insanelymac.com/forum/topic/290797-mountain-lion-realtek-alc-applehda-audio/

Credit
THe KiNG 
VHC888
.:ErmaC:.
bcc9
RevoGirl

toleda
https://github.com/toleda/audio_ALCInjection
Patches
hdef0-add_dsdt-HDEF-1.txt
hdef1-alc8xx_audio-1.txt
hdef2-alc8xx_audio-2.txt
hdef3-alc8xx_audio-3.txt
hdef4-delete_HDEF-_DSM.txt
hdef5-rename_dsdt-AZAL-1.txt
Guides
[Guide] Add HDEF-Clover.pdf
[Guide] Add or Edit HDEF-dsdt.pdf
[Guide] Add HDEF-kext.pdf
[Guide] Add HDEF-ssdt.pdf
IORegistryExplorer_v2.1
Property_List_Editor_v5.3.zip
M-Realtek ALC AppleHDA Capabilities.pdf.zip
M-Realtek ALC AppleHDA Customization.pdf.zip
M-Realtek ALC AppleHDA Screenshots.pdf.zip
M-Realtek_ALC_AppleHDA-No_Audio.pdf.zip
ML-Customizing_the_Realtek_ALC_AppleHDA.pdf.zip
ML-Realtek_ALC_AppleHDA_Capabilities.pdf.zip
ML-Realtek_ALC_AppleHDA_Screenshots.pdf.zip
zlib_terminal
README.txt