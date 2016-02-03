HDMI Audio AppleHDA [Guides]_v4.0  
![alt text](https://github.com/toleda/audio_RealtekALC/blob/master/sound.jpeg)
#HDMI Audio AppleHDA [Guides]

**OS X Intel HD Graphics/AMD/Nvidia HDMI audio**  

Clover HDMI audio enables HDMI, DP and DVI audio with patched or native OS X AppleHDA.kext. HDMI audio ACPI edits are enabled with dsdt edits, edited ssdts or Clover injection/dsdt patching.  Clover provides audio and graphic binary patching while preserving native kext installation.  Supports Intel HD Graphics and/or AMD or Nvidia HDMI audio.

cloverHDMI detects and installs the correct ssdt(s) and patches the Intel framebuffer for the connected display(s) enabling OS X HDMI audio.

**Updates**  
**1/15/16 - El Capitan support, cloverHDMI script**  
12/2/14 - Yosemite, 9series support   
Credit: TimeWalker/10.10+/HD4600 codec patch

# Methods
Install one method, uninstall before installing another method  

**I.		cloverHDMI** (script)  

1. detects and installs appropriate ssdt(s)
2. detects and installs appropriate Intel connector patches  

**II.		ssdt** (user)  

1. install appropriate ssdt
2. install appropriate Intel connector patches (as required)
3. install appropriate AMD connector patches (as required)  

**III.		dsdt** (user)  

1. edit dsdt (MaciASL) and install edited dsdt
2. install appropriate Intel connector patches (as required)
3. install appropriate AMD connector patches (as required)

**IV.		Bootloader HDMI audio** (user)

1. no dsdt/ssdt/kext edits

Repo downloads: select link, select View Raw
# HDMI Audio Installation
# I.	cloverHDMI  
Beta  

1. [cloverHDMI](https://github.com/toleda/audio_CloverHDMI/) 


# II - ssdt injection
 Most systems; install ssdt and restart  

1. Download [[Guide] HDMI audio/ssdt](https://github.com/toleda/audio_hdmi_guides/blob/master/%5BGuide%5D-OSX-hdmi_audio-hdef_audio-ssdt.pdf.zip)
2. Note - BIOS/OS X updates do not effect ssdts
3. edited ssdts, see dsdt/ssdt HDMI audio Guides below
	1. [HD6000+/Desktop/BRIX/NUC](https://github.com/toleda/audio_hdmi_9series/tree/master/ssdt_hdmi-hd6000%2B)
	2. [HD4600+/Desktop/BRIX/NUC](https://github.com/toleda/audio_hdmi_8series/tree/master/ssdt_hdmi-hd4600%2B)
	3. [HD4000/Desktop/BRIX/NUC](https://github.com/toleda/audio_hdmi_hd4000/tree/master/ssdt_hdmi-hd4000)
	4. [HD3000/Desktop](https://github.com/toleda/audio_hdmi_hd3000/tree/master/ssdt_hdmi-hd3000)
	5. [AMD HDMI audio](https://github.com/toleda/audio_hdmi_amd-nvidia/tree/master/ssdt_hdmi-amd)
	6. [Nvidia HDMI audio](https://github.com/toleda/audio_hdmi_amd-nvidia/tree/master/ssdt_hdmi-nvidia)
	5. [ALC/HDEF audio](https://github.com/toleda/audio_ALCInjection/tree/master/ssdt_hdef)
4. kext edits, if required, see **II/III - dsdt/ssdt HDMI audio Guides** below  

# III - dsdt edits
All systems: extract dsdt, patch, install edited dsdt.

1. Download [[Guide] HDMI audio/dsdt](https://github.com/toleda/audio_hdmi_guides/blob/master/%5BGuide%5D-OSX-hdmi_audio-hdef_audio-dsdt.pdf.zip)
2. Notes
	1. BIOS update require same dsdt edits on new installed BIOS
	2. OS X updates do not effect dsdts
	3. All Intel systems have a dsdt
	4. AMD/Nvidia HDMI audio is installed
3. dsdt edits/MaciASL, see **II/III - dsdt/ssdt HDMI audio Guides** below
4. kext edits, if required, see **II/III - dsdt/ssdt HDMI audio Guides** below

# II/III - dsdt/ssdt HDMI audio Guides
Download appropriate guide from repo

1. [HD6000+/Desktop/BRIX/NUC](https://github.com/toleda/audio_hdmi_9series)
2. [HD4600+/Desktop/BRIX/NUC](https://github.com/toleda/audio_hdmi_8series)
3. [HD4000/Desktop/BRIX/NUC](https://github.com/toleda/audio_hdmi_hd4000)
4. [HD3000/Desktop](https://github.com/toleda/audio_hdmi_hd3000/tree/master/ssdt_hdmi-hd3000)
5. [5 Series/X58/X79/X99/Desktop](https://github.com/toleda/audio_hdmi_5series) (dsdt edits only)
6. Discrete Graphics (if installed)
	1.	[AMD HDMI audio](https://github.com/toleda/audio_hdmi_guides/blob/master/%5BGuide%5D-OSX-AMD-hdmi_audio.pdf.zip)
	2.	[Nvidia HDMI audio](https://github.com/toleda/audio_hdmi_guides/blob/master/%5BGuide%5D-OSX-Nvidia-hdmi_audio.pdf.zip)

# IV - Bootloader HDMI audio

1.	HD4000/HD3000
	1.	Clover/EFI/CLOVER/Config.plist
		1.	Devices/Audio/Inject/3
		2.	Devices/UseIntelHDMI/YES
		3.	Graphics/Inject/Intel/YES

# HDMI Audio Details 

**V - Before You Start**

1.	OS X does not provide HDMI audio controls (No volume, no mute, no balance, etc.)
2.	The connected HDMI device (TV, receiver, etc.) provides any and all audio control

**VI - Additional Information**

1.	[HDMI audio](https://github.com/toleda/audio_hdmi_guides)  
2.	[HDEF audio](https://github.com/toleda/audio_ALC_guides)

**VII - Requirements**  

1.  OS X Versions (+ all)
    1.  10.11+/El Capitan 
    2.  10.10+/Yosemite
    3.  10.9+/Mavericks
    4.  10.8+/Mountain Lion
2.	Intel Desktop Motherboards
	1.	9 Series - Z97, H97, B95
	2.	8 Series - Z87, H87, B85, H81 ...
	3.	7 Series - Z77, H77, B75 ...
	4.	6 Series - Z68, P67, H67, H61 ...
	5.	5 Series - P55, H55 ...
3.	Graphics
	1.	Intel HD Graphics (1st generation and prior, not supported)
		1.	HD6000+ (BDW framebuffer edits required)
		2.	HD4600+ (Azul framebuffer edits required)
		3.	HD4000 (Capri framebuffer edits may be required)
		4.	HD3000 (SNB framebuffer edits may be required)
		5.	BDW/Azul/Capri/SNB kext edits
			1.	Kext/binary patch/ [Intel graphics kext edits](https://github.com/toleda/graphics_Intel_framebuffers)
			2.	Clover/kext patch [config-hdmi_HD ... plist edits](https://github.com/toleda/audio_CloverHDMI)
	2.	AMD HD R7-R9 3xx/R7-R9 2xx/HD 7xxx/HD 6xxx/HD 5xxx (default framebufer)
		1.	AppleHDAController and AMD70000Controller/AMD60000Controller/AMD50000Controller edits may be required, see [Editing custom personalities for ATI Radeon HD[45]xxx](http://www.insanelymac.com/forum/topic/249642-editing-custom-personalities-for-ati-radeon-hd45xxx/)
		2.	AMD TrueAudio supported 10.10.4 and newer
			1.	AMD9000Controller.kext/GCN1.2/Tonga/TrueAudio
				⁃	HDMI/DP working
			2.	AMD8000Controller.kext/GCN1.1/Hawaii/Bonaire/TrueAudio
			⁃	HDMI/DP not working
	3.	Nvidia 9xx/7xx/6xx/5xx/4xx (750 and 9xx require Nvidia Web driver)
		1.	GTS 450, GTX 550, GTX 560 not supported natively
			1.	550/560 fix available

**VIII - Notes**

1. Boot Flags/Boot failure may result if ignored
	1.	10.11+/Disable SIP/set, restart, install, enable SIP, restart
		1.	CLOVER/config.plist/
			1. ACPI/DSDT/Fixes/NO (all or remove)
			2.	RtVariables/BooterConfig/0x28
			3.	RtVariables/CsrActiveConfig/0x3
	2.	10.10+/Allow unsigned kexts/set, restart, install
		1. Clover/config.plist/
			1. ACPI/DSDT/Fixes/NO (all or remove)
			2. Boot/Arguments/kext-dev-mode=1
2.	HD4600/HD4400/Mobile - no native support
	1. README: [RehabMan OS-X-Fake-PCI-ID](https://github.com/RehabMan/OS-X-Fake-PCI-ID)
	1. Downloads: [RehabMan OS-X-Fake-PCI-ID](https://bitbucket.org/RehabMan/os-x-fake-pci-id/downloads)
3.	S/L/E/AppleHDA.kext
	1.	Native S/L/E/AppleHDA.kext
	2.	HD4600/Desktop HDMI audio codec
		1.	Kext/binary patch: [HD4600/Desktop/AppleHDA edit](https://github.com/toleda/audio_hdmi_8series/blob/master/audio_hdmi_hd4600-hda-110.command.zip)
		2.	Clover/kext patch: [HD4600/Desktop/AppleHDA edit](https://github.com/toleda/audio_CloverHDMI/blob/master/config-hdmi_hd4600-100.plist.zip)
4.	HD2000/HD2500 not supported

**IX.** [Problem Reporting](https://github.com/toleda/audio_ALC_guides/blob/master/Problem%20Reporting.md)  

1.	Problem Reporting/Post to: 
2.	Problem Reporting/Attached requested files

Credit  
[TimeWalker75a Post #118](http://www.insanelymac.com/  forum/topic/290783-intel-hd-graphics-4600-haswell-working-displayport/page-6#entry1949558)  
[PikeRAlpha](https://pikeralpha.wordpress.com/2013/09/19/haswell-hdau-solution/)  
[bcc9 Post #11](http://www.insanelymac.com/forum/topic/290783-intel-hd-graphics-4600-haswell-working-displayport/?p=1934889)

toleda
https://github.com/toleda/audio_cloverHDMI