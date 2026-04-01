# Optimize Windows 11

Optimized system to get the best results (with the least amount of tweaks):

* Better 1% lows (stutter)
* Better frame consistency
* Better input latency
* Debloated as many 'uneccessary' apps & background images
* Without breaking functionality for: Gaming & Cybersecurity
* More FPS if possible

# Warning/Disclaimer

All the changes & downloads done by you to the software & hardware is done at your own risk. Restart whenever you do apply changes to should require a restart of the Windows Operating System.

#### Under (heavy) load

Test on maximum settings (Cinematic , V-Sync On, Ray Tracing, Shadows, Volumetric fog and Lighting) with a game that is demanding: Crimson Desert.

* Max CPU Temps: < 90°c
* Max GPU Temps: < 85°C

#### Idle

* Ideal CPU Temps Goal: ~70°c
* Ideal GPU Temps Goal: ~70°c
* Memory:               20%
* CPU:                  Minimum

## Dependancies

### Hardware

* Laptop:          Legion Pro 7 16IRX8H
* MB:              LENOVO LNVNB161216
* CPU:             Intel Core i9-13900HX (Raptor Lake-HX 8+16)
* RAM:             32 GB DDR5-5600
* GPU:             Nvidea 4080 12 GB GDDR6 (NVIDIA GeForce RTX 4080 Laptop (AD104M/GN21-X9) [Lenovo])
* BIOS Version:    KWCN54WW

### Software

* Using Windows 11 25H2
* Lenovo Windows Image
* Lenovo Vantage
* EXM app
* MSI afterburner
* RivaTuner
* Nvidea App
* Nvidea Control panel

## Start

Start with a fresh/clean Windows install from the official Lenovo website. Don't make an local account since it will install Windows 11 22H2 which isn't supported since 10/2025.  Install the dependancies.

#### Windows

* Windows:               Windows 11 25H2
* Installed:             30/‎03/‎2026
* OSBuild:               26200.8039

Installed Windows 11 23H2 from the image provided by Lenovo. Lenovo uses custom images for their systems (comes with bloat and a couple of nice features). After installation of Windows 11 23H2 I downloaded Windows ISO from the official website and did a In-Place upgrade:

* Go to the Windows 11 website: https://www.microsoft.com/software-download/windows11
* Under "Download Windows 11 Disk Image (ISO)", select "Windows 11 (multi-edition ISO)".
* Once the ISO is downloaded, right-click on it and select "Mount", then click on "Setup.exe".
* You may be prompted by User Account Control, in which case, click on "Yes".
* In the "Install Windows 11" dialog, click "Next".
* Setup will check your PC and display a license agreement. Click on "Accept" to proceed.
* Wait for the setup program to check for available free space.
* On the "Ready to install" page, ensure that "Keep personal files and apps" is checked.
* Click "Install" and follow the prompts.
* Windows 11 will restart your device several times and lead you to the lock screen. Depending on the          options you set, it will keep all your files, apps, and user accounts.

### Dependancies hyperlinks

* Lenovo Windows Image:  https://support.lenovo.com/us/en/solutions/ht103653

* Lenovo Vantage:        https://www.lenovo.com/us/en/software/vantage

* HWiNFO:                https://www.hwinfo.com/

* EXM app:               https://exmtweaks.com/en-eu

* MSI Afterburner:       https://www.msi.com/Landing/afterburner/graphics-cards

* Rivatuner:             Mark the option checked during installation of MSI Afterburner

* Nvidea Drivers:        https://www.nvidia.com/en-us/geforce/drivers/

* Nvidea Control Panel:  Should be installed on your device

## EXM App

Configuration of options available and what they do.

https://exmtweaks.com/en-eu

plus [+] = toggled on in the app

minius [-] = toggled off in the app

### General

#### Core

Generic settings that you can toggle on and off to decrease background processes to optimize your Windows instance. Do note that it may break certain services.
----
* Disable All Notification                           = -

https://windowsreport.com/windows-11-disable-notifications/

Risks and trade‑offs — be deliberate​
Silencing reminders improves concentration, but be deliberate about which signals you block:

    Keep alarms and trusted calendar reminders enabled if you rely on them for time‑critical tasks.
    Be careful disabling Windows Security notifications — they often include actionable security warnings you shouldn’t miss.
    For professional or managed devices, make changes through formal admin channels (GPO/Intune) to avoid configuration drift and support issues.

When in doubt, favor scheduled Focus sessions and per‑app controls — they balance quiet with safety.
Final analysis and best practices​
Windows 11’s notification architecture gives you granular control — and Microsoft continues to layer new engagement surfaces into thch is a pragmatic one:

    Use Focus Sessions / Do Not Disturb for temporary deep work; schedule them so quiet becomes automatic.
    Disable system tips and Cloud Content suggestions if you want to stop onboarding prompts and product nudges.
    Triage apps one by one rather than using the master kill switch.
    For privacy/ads, disable Advertising ID and Tailored experiences.
    For organizations, apply Cloud Content Group Policy values to enforce a consistent user experience, but test across SKUs and builds because behavior can vary.
-----  
* Disable Animations                                 = +

How Disabling Animation Fits into Broader Performance Tweaks​
Turning off animations should be viewed as one element in a toolkit for optimizing Windows 11. Other options—such as disabling transparency effects, pruning unnecessary background services, and tweaking visual settings—can yield further improvements in both perceived and real-world speed. For maximum benefit, users often combine multiple tweaks:

    Disable Transparency: Turning off transparency effects (via Settings > Personalization > Colors) further reduces graphical overhead.
    Background Apps: Managing which apps can run in the background (Settings > Privacy & Security > Background apps) can recover additional responsiveness, particularly on older PCs.
    Startup Programs: Pruning the startup list ensures a leaner boot and less contention for RAM and CPU cycles.

https://windowsforum.com/threads/boost-windows-11-performance-by-disabling-animations-for-snappier-user-experience.371135/

No single tweak can overcome fundamental hardware bottlenecks, but a combination of settings—including disabling animations—can bridge much of the perceived speed gap between Windows 10 and its successor.
Tweak	Effect	Where to Find
Disable Animations	Faster UI, less visual lag	Accessibility > Visual Effects
Turn Off Transparency	Reduces GPU load, boosts clarity	Personalization > Colors
Manage Background Apps	Frees resources, slows drain	Privacy & Security > Background Apps
Remove Startup Programs	Faster boot, more available RAM	Task Manager > Startup
Adjust Power Settings	Maximizes performance potential	System > Power & battery
----- 
* Disable Bluetooth Services                         = +

Security, battery life, and privacy: how much do you gain by disabling Bluetooth?​

    Battery benefit: Disabling Bluetooth reduces background radio usage and can save battery on laptops and tablets. The exact amount varies by device, usage, and whether peripherals stay connected — a precise percentage change can't be universally guaranteed and depends on hardware and usage patterns (this claim is practical rather than precisely quantifiable without device‑specific testing). Flag: unverifiable as a single number.
    Privacy and attack surface: Turning the radio off reduces the chance of unsolicited pairing requests and limits the local attack surface. That said, Wi‑Fi, USB, and other interfaces remain potential vectors; Bluetooth is just one part of an overall security strategy. Disabling Bluetooth is a pragmatic privacy step but not a complete security fix.
    Troubleshooting benefit: Cutting the radio or disabling the driver is a reliable diagnostic tool. If the problem follows the device (works on phone, not on PC), disabling and re‑enabling or reinstalling drivers helps isolate whether the issue is OS, driver, or peripheral side.

https://windowsforum.com/threads/how-to-disable-bluetooth-in-windows-11-quick-settings-to-services.387414/
-----
* Disable Driver Searching                           = -


-----
* Disable Exeprimental Features                      = +
* Disable Gamedvr                                    = +
* Disable Microsoft Edge                             = +
* Disable Scheduled Maintenance                      = +
* Disable Search Indexing                            = +
* Disable Start up Delay for Apps                    = +
* Enable Game Mode                                   = +
* Optimize Hung Apps                                 = +
* Optimize Visual Settings                           = -
* Optimize Windows Search                            = -
* Set Windows 32 Priority Seperation                 = Pick one that suits your need and do your research
* Configure Tsync Policy                             = Pick one that suits your need and do your research
* Disable Hypervisor                                 = -
* Disable Scheduled Tasks                            = -
* Remove AI intergration in Windows                  = +
* Tweak Latency Tolerance                            = +
  

---- 

#### Powerplan

----
* Disable All Power Telemetry                        = +
* Diable Energy Estamation                           = +
* Disable Fast Startup                               = +
* Disable Hibernation                                = +
* Disable Hybrid Sleep                               = -
* Disable Fast Startup                               = +
* Disable Sleep Timeout                              = +
* Disable Standby                                    = +
* Disable Powersaving                                = +
* Optimize S3 Sleepstates                            = +
* Set Timer Resolution                               = Let the app optimize the timing

----


#### Privacy

----
This is personal preference adjust to your liking
----

#### QOL

----
This is personal preference adjust to your liking
----

#### Apps

----
This is personal preference adjust to your liking
----

#### Powerplan

----
EXM Premium Laptop Powerplan                       = Applied
----

### Hardware

#### GPU

----
* Advanced NVIDIA GPU Driver Installer             = !!!Don't Debloat!!!
* EXM Laptop Nvidia Profile                        = Applied
* EXM Desktop Nvidia Profile                       = Not Applied
* Disable Geforce Driver Update                    = -
* Disable HDCP                                     = +
* Disable Nvidia Disable Logging                   = +
* Disable Nvidia DMA Remapping                     = +
* Disable Nvidia Uvm                               = -
* Force Contigous Memory Allocation                = +
* Optimize GPU Idle Thresholds                     = +
* Optimize Memoery Latency Settings                = +
* Optimize Nvidia Flip & VRR                       = +
* Optimize Nvidia Fame Scheduling                  = +
* Optimize Nvidia Geforce Experience Telemetery    = -
* Disable Nvidia Aspm                              = -
* Disable Nvidia Display Power Saving              = +
* Disable Nvidia ECC                               = -
* Disable Nvidia Gc5 Caching                       = +
* Disable Nvidia Misc Power                        = -
* Disable Nvidia Thermal Throttle                  = -
* Disable TCC                                      = -
* Force P0-State                                   = -
* Keep Nvidia Dram Active                          = +
* Optimize Nvidia Acpi & D3                        = +
* Optimize Nvidia Bus Clocks                       = +
* Optimize Nvidia Elpg                             = +
* Optimize Nvidia Engine Clocks                    = +
* Optimize Nvidia Gc6 Ilde                         = -
* Optimize Nvidia Interrupts                       = -
* Optimize Nvidia PCI Latency Control              = +
* Optimzie Nvidia Power Features                   = -
* Reduce Nvidia Polling Latency                    = +
* Set Unrestricted Clock Policy                    = +
* Streamline Nvidia Watchdog                       = +
* Tune Nvidia Low-Power                            = -
* Unlock Nvidia Perf Limits                        = +
-----

#### CPU

----

* Disable Basic C-states                           = -
* Disable Coalescable Timer                        = -
* Disable CPU Core Parking                         = -
* Disable CPU Power Throttling                     = -
* Disable Modern Standby                           = -
* Set Energy Performance Preference                = -
* Set Minimum And Maximum Processor State          = -
* Disable Eventprocessor                           = +
* Set Kernel Worker Threads                        = +
* Set Scheduling Reserve                           = +
* Delete Inter Microcode                           = Applied

#### RAM

-----
* Clear Page File At Shutdown                      = +
* Disable Memory Compression                       = +
* Disable Prefetcher                               = +
* Disable RAM Diagnostics                          = +
* Enable Superfetch                                = +
* Optimize And Group Svchost                       = +
* Disable Diagnostic Execution On RAM Erros        = +
* Disable Kernel Paging Executive                  = +
* Disable Page Combining                           = +
* Disable Tracking Of Memory Diagnostics History   = +
-----


#### Peripherals

#### Keyboard and Mouse
-----
* Disable Idle and sleep states                    = -
* Disable Mouse Acceleration                       = -
* Disable Sticky Keys                              = -
* Disable Toggle Keys                              = -
* Enable 1:1 Pixel Mouse Movement                  = -
* Reduce Keyboard Repeat Delay & Rate              = -
-----

#### USB
-----
* Apply a custom USB Overclocking Driver           = -
* Disable USB Selective Suspend                    = +
* Set Debug Poll interval                          = +
* Disable all hidden USB Power Saving Functions    = +
* Optimize USB Ports & Drivers for Keyboard & Mouse= Applied
-----

#### Storage

-----
* Disable DIPM Parking                             = +
* Disable HDD Parking                              = +
* Disable HIPM Parking                             = +
* Disable SSD Powersaving                          = +
* Disable Write Cache Buffer Flushing              = +
* Optimise SSD Sleep                               = +
* Disable I/O latencycap                           = +
* Disable NVMe Idle Power States                   = +
* Disable Storage Idle Timeout                     = +
* Optimize NFTS Settings                           = +
* TRIM & Defragment Optimize Drives                = +
-----

#### Debloat

#### System Cleaner

-----
* Do a system clean up as you see fit
-----

#### Services

-----
* Basic                                            = -
* Advanced                                         = +
-----

#### Autoruns

-----
* Do check what services you can and cannot disable
-----


#### Autoruns

-----
* Uninstall any apps you see fit and know what will break if you do uninstall them
-----

#### Network

-----

Tweaks

-----

* Disable Automatic TCP Adjustment                   = -
* Disable IPv6                                       = -
* Disable Ipv6 Transistion Services                  = -
* Disable Security Profiles                          = -
* Enable Weak Host Send/Recieve                      = -
* Enhance Connection Stability                       = +
* Improve Network Packet Acknowlegdement             = +
* Optimize IPv6 Address Handeling                    = -
* Optimize MTU Size                                  = +
* Optimize Neighbor Cache                            = +
* Optimize Offloading Features                       = -
* Optimize Packet Coalescing                         = +
* Optimize Winsock Buffer Behaviour                  = +
* Set Stabilize Network Routing                      = +
* Disable Heuristics                                 = -
* Optimize MPP                                       = -

----

Adapter Tuner

----

Pick what applies for your system:

* Optimize WiFi Adapter                              = -
* Optimize Ethernet Adapter                          = +


-----

#### BufferBloat

-----

Pick what applies for your system:

* Normal Mode                                        = -
* Ultra Low Bufferbloat                              = +

#### Network Priority

You can toggle the on/off button to add a game for a more stable network connection

#### Advanced

#### Devices

-----
* Ultra Low Bufferbloat                              = +
* Disable Communication Ports                        = -
* Disable Eusa Programmable Interrupt Controller     = +
* Disable High Precision Event Timer                 = -
* Disable Microsoft Gs Wavetable Synth                = -
* Disable Microsoft Hyper-v infrastructure Driver    = -
* Disable Remote Desktop Device Redirector Bus       = +
* Disable Serial Parts                               = +
-----

#### MSI Mode

-----
* GPU                                                = +
* High Definition Audio Controllers                  = +
* Network Adapter                                    = +
* NVMe                                               = +
* SATA                                               = -
* USB Controller                                     = +
-----

#### Security

-----

* Allow Dynamic Code                                 = -
* Disable Bottomup/highentropy ASLR                  = -
* Disable Control Flow Guard (cfg)                   = -
* Disable Core Isolation (memory integrity)          = -
* Disable Extension Point isolation                  = -
* Disable Fault Tolerant Heap                        = -
* Disable Forcelocateimages                          = -
* Disable Kernel Stack Randomization                 = -
* Disable Nonsystem Fonts                            = -
* Disable ROP Mitigations                            = -
* Disable Sehop                                      = -
* Disable Smartscreen Filter                         = -
* Disable Smbv1 & SMB Signing                        = -
* Disable Stricthandle Checks                        = -
* Disable Uac                                        = -
* Disable Win32k System Call Disable                 = -
* Virtualization-based Security (vbs)                = -

-----

UVM Nvidea

What does it do?

https://docs.nvidia.com/cuda/cuda-programming-guide/04-special-topics/unified-memory.html

https://docs.nvidia.com/cuda/cuda-programming-guide/04-special-topics/unified-memory.html#um-legacy-devices

https://docs.nvidia.com/cuda/cuda-programming-guide/02-basics/understanding-memory.html#table-unified-memory-levels

NVIDIA "Gc5" caching usually refers to the
NVIDIA GL Cache (often found in folders named GLCache or combined with DXCache), which is a component of the NVIDIA Shader Cache system. It is a storage mechanism on your hard drive that stores pre-compiled shaders for OpenGL and DirectX applications (mostly games) to improve rendering performance and reduce stuttering.

DLL & PLL

https://www.rambus.com/dllpll-on-a-dram/

## MSI Afterburner & RivaTuner

https://www.msi.com/Landing/afterburner/graphics-cards

### 

### Nvidea App

### Nvidea Control Panel

