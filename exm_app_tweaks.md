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


Removing hidden ghost drivers is a legitimate and effective optimization for Windows 11 systems under heavy load. The biggest wins come from old GPU drivers, old network drivers, and USB device bloat. Always create a restore point first, never remove entries under the Non-Plug and Play Drivers node, and use DDU when switching GPU brands for the cleanest possible result.

https://windowsforum.com/threads/the-ultimate-guide-to-removing-old-hidden-device-drivers-in-windows-11.360680/

DPC Latency increase: Ghost drivers can execute Deferred Procedure Calls, adding latency spikes — devastating for frame pacing and real-time audio

https://windowsforum.com/threads/latencymon-guide-identify-driver-latency-causing-stutters-in-windows.386112/

IRQ / Resource conflicts: Old entries may reserve interrupt lines or memory ranges, starving your active GPU or NVMe controller

https://learn.microsoft.com/en-us/windows-hardware/drivers/debugger/checking-for-resource-conflicts

Non-paged pool memory waste: Some residual drivers allocate kernel memory that is permanently locked in RAM

https://techcommunity.microsoft.com/blog/askperf/memory-management---understanding-pool-resources/372321

Driver conflicts: A previous GPU driver (e.g., from an old NVIDIA card) can clash with your current one (e.g., AMD), causing stutters, crashes, or BSODs. Driver conflicts can lead to system instability, hardware malfunctions, and crashes. When multiple drivers interfere with each other, devices may stop working properly. This guide provides step-by-step solutions to fix driver conflicts effectively.

https://tech-now.io/en/it-support-issues/software/how-to-resolve-driver-conflicts-step-by-step-guide-to-fixing-driver-issues

https://learn.microsoft.com/en-us/answers/questions/4037530/how-to-prevent-automatic-windows-11-updates-from-o

-----
* Disable Experimental Features                      = +

In Windows 11, "experimental features" typically refer to hidden components or features being tested in the Windows Insider Program. For gaming and heavy workloads, these features can cause instability, higher latency, or "stuttering" because they are not yet optimized for general hardware.

1. Exit the Windows Insider Program

The most direct way "experimental" features end up on your system is through the Insider Program. If you are on a Dev or Canary channel, you are effectively a beta tester for unoptimized code.

https://www.microsoft.com/en-us/windowsinsider/leave-program

2. Disable "Experimental" Security Features (VBS/HVCI)

While not labeled "experimental" in the menu, Virtualization-Based Security (VBS) and Memory Integrity are often cited by hardware experts as the biggest performance drains (up to 25% FPS loss in some scenarios). These features create a virtualized environment that can interfere with high-speed CPU scheduling.

https://windowsforum.com/threads/windows-11-gaming-tuning-guide-2026-safe-consistent-performance.401517/
   
3. Manage Hidden Features with ViVeTool

Advanced users often use a third-party, open-source tool called ViVeTool to manually disable specific "Feature IDs" that Microsoft may have enabled silently on your system for A/B testing.

https://4sysops.com/archives/vivetool-enable-hidden-windows-features/#:~:text=ViVeTool%20is%20an%20open%2Dsource,immediately%20visible%20to%20all%20users.

4. Optimize "Heavy Workload" Settings

Instead of hunting for hidden experiments, ensure the following High Performance features are correctly configured to prevent Windows from "experimenting" with your power management.

https://windowsforum.com/threads/windows-11-gaming-tuning-guide-2026-safe-consistent-performance.401517/#:~:text=Microsoft%20itself%20has%20acknowledged%20that,the%20security%20trade%2Doffs).

To keep your system stable for work, the best practice is to stay on the Windows 11 Home/Pro "Stable" branch and avoid the Insider Program entirely.

-----
* Disable Gamedvr                                    = +

Disabling Game DVR in Windows 11 is a common step for users looking to reclaim system resources, as the feature constantly monitors and records your screen in the background to enable "instant replays." This background recording consumes CPU cycles, GPU encoding power, and disk I/O, which can cause micro-stutters or reduced FPS in heavy workloads.

Why this matters for Performance

    Reduced Overhead: Disabling the "Background Recording" feature frees up your GPU's hardware encoder (NVENC/AMF), which is better utilized by your actual game or professional rendering software.

    Reduced Input Lag: By stopping the OS from constantly "hooking" into your display output to capture frames, many users report a "snappier" feel and lower system latency.

    Disk Activity: Game DVR writes temporary video files to your drive constantly. Disabling it reduces unnecessary SSD wear and I/O saturation during heavy file transfers.

The Registry Edit (Full Disable)

If you want to ensure the recording engine (Game DVR) is completely inactive, you can use the Registry Editor.

    Note: Always back up your registry before making changes.

    Press Win + R, type regedit, and hit Enter.

    Navigate to: HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\GameDVR

    Find AppCaptureEnabled. Double-click it and set the value to 0.

    If it doesn't exist, right-click > New > DWORD (32-bit) Value, name it exactly that, and set it to 0.

    Navigate to: HKEY_CURRENT_USER\System\GameConfigStore

    Find GameDVR_Enabled. Double-click it and set the value to 0.

    Restart your PC for changes to take effect.

A quick tip: If you are disabling this for gaming, ensure "Game Mode" (Settings > Gaming > Game Mode) is actually ON. While it sounds counter-intuitive, in Windows 11, Game Mode prioritizes your game’s process and prevents Windows Update from installing drivers in the background while you work or play.

https://iqondigital.com/learn/pc-optimization/game-bar-dvr

https://www.kingston.com/en/blog/gaming/windows-11-pc-performance-features-for-gamers#:~:text=Windows%2011's%20Game%20Mode%2C%20which,tasks%20like%20updates%20and%20notifications.
-----

* 
# Disable Microsoft Edge                             = +

To maximize system resources for gaming and heavy workloads, you don't necessarily need to "uninstall" Microsoft Edge (which can be risky since it’s deeply integrated into Windows 11). Instead, you can effectively neutralize its background resource consumption.

  
* Disable Scheduled Maintenance                      = -

Scheduled Maintenance in Windows 11 is a built-in feature designed to run tasks like software updates, security scans, and system diagnostics when you aren't using your PC. While helpful for the average user, these tasks can trigger during heavy workloads or gaming sessions, causing CPU spikes, disk latency, and "micro-stutters."

To prevent Windows from automatically starting maintenance entirely, you can use the Registry Editor.

    Note: Always back up your registry before making changes.

    Press Win + R, type regedit, and hit Enter.

    Navigate to: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\Maintenance

    Right-click in the right pane, select New > DWORD (32-bit) Value.

    Name it MaintenanceDisabled.

    Double-click it and set the Value data to 1.

    Restart your computer.

* Disable All Notification                           = -
* Disable Animations                                 = +
* Disable Bluetooth Services                         = +
* Disable Driver Searching                           = -
* Disable Experimental Features                      = +
* Disable Gamedvr                                    = +   
* Disable Scheduled Maintenance                      = -
* Disable Search Indexing                            = +
* Disable Scheduled Maintenance                      = -
* Disable Search Indexing                            = +  
* Disable Start up Delay for Apps                    = +
* Disable Transparency Effects                       = +
* Disable Windows Updates                            = -
* Disable Xbox Services                              = +
* Enable Game Mode                                   = +
* Optimize Hung Apps                                 = +
* Optimize Visual Settings                           = +
* Optimize Windows Search                            = +
* Set Windows 32 Priority Seperation                 = (26 Hex) Pick one that suits your need and do your research
* Configure Tsync Policy                             = (Legacy) Pick one that suits your need and do your research
* Disable Hypervisor                                 = -
* Disable Scheduled Tasks                            = +
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

EXM Premium Desktop Powerplan                      = + 
Premium Laptop Powerplan                           = -
----

### Hardware

#### GPU

----
* Advanced NVIDIA GPU Driver Installer             = !!!Don't Debloat!!!
* EXM Laptop Nvidia Profile                        = Not Applied
* EXM Desktop Nvidia Profile                       = Applied
* Disable Geforce Driver Update                    = -
* Disable HDCP                                     = +
* Disable Nvidia Disable Logging                   = -
* Disable Nvidia DMA Remapping                     = +
* Disable Nvidia Uvm                               = -
* Force Contigous Memory Allocation                = -
* Optimize GPU Idle Thresholds                     = +
* Optimize Memoery Latency Settings                = +
* Optimize Nvidia Flip & VRR                       = +
* Optimize Nvidia Fame Scheduling                  = +
* Optimize Nvidia Geforce Experience Telemetery    = -
* Disable Nvidia Aspm                              = -
* Disable Nvidia Display Power Saving              = +
* Disable Nvidia ECC                               = +
* Disable Nvidia Gc5 Caching                       = +
* Disable Nvidia Misc Power                        = +
* Disable Nvidia Thermal Throttle                  = -
* Disable TCC                                      = +
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

* Disable Basic C-states                           = +
* Disable Coalescable Timer                        = +
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
* Disable RAM Diagnostics                          = -
* Enable Superfetch                                = +
* Optimize And Group Svchost                       = -
* Disable Diagnostic Execution On RAM Erros        = -
* Disable Kernel Paging Executive                  = +
* Disable Page Combining                           = -
* Disable Tracking Of Memory Diagnostics History   = -
-----


#### Peripherals

#### Keyboard and Mouse
-----
* Disable Idle and sleep states                    = +
* Disable Mouse Acceleration                       = +
* Disable Sticky Keys                              = +
* Disable Toggle Keys                              = -
* Enable 1:1 Pixel Mouse Movement                  = +
* Reduce Keyboard Repeat Delay & Rate              = +
* Optimized for Mouse & Keyboard                   = +
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
* Disable DIPM Parking                             = -
* Disable HDD Parking                              = -
* Disable HIPM Parking                             = -
* Disable SSD Powersaving                          = -
* Disable Write Cache Buffer Flushing              = -
* Optimise SSD Sleep                               = -
* Disable I/O latencycap                           = +
* Disable NVMe Idle Power States                   = -
* Disable Storage Idle Timeout                     = -
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
* Optimize Packet Coalescing                         = -
* Optimize Winsock Buffer Behaviour                  = +
* Reduce Network Background Interruptions            = +


-----
* Set Stabilize Network Routing                      = +

https://learn.microsoft.com/en-us/windows-365/enterprise/optimization-of-rdp
-----
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
* Ultra Low Bufferbloat                              = -
* Disable Communication Ports                        = -
* Disable Eusa Programmable Interrupt Controller     = -
* Disable High Precision Event Timer                 = -
* Disable Microsoft Gs Wavetable Synth               = -
* Disable Microsoft Hyper-v infrastructure Driver    = -
* Disable Remote Desktop Device Redirector Bus       = -
* Disable Serial Ports                               = +
-----

#### MSI Mode

-----
* GPU                                                = +
* High Definition Audio Controllers                  = +
* Network Adapter                                    = +
* NVMe                                               = +
* SATA                                               = +
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
