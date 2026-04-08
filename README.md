# Optimize Windows 11

Optimized system to get the best results (with the least amount of tweaks):

* Better 1% lows (stutter)
* Better frame consistency
* Better input latency
* Debloated as many 'uneccessary' apps & background images
* Without breaking functionality for: Gaming & Cybersecurity
* More FPS if possible

Quick read up on different aspects to optimize your system for gaming:

https://generalistprogrammer.com/tutorials/game-optimization-complete-performance-guide-2025

https://exmtweaks.com/en-eu/free-tweaks/how-get-lower-processes-windows

## Issues (Unresolved)

* Windows DPC Watchdogs Violation (turned on settings in EXM App)

## To do list

* Uninstall Cap Frame X
* Fix RTTS overlay for MSI Afterburner
* Baseline tests (just to be safe)
* Test each setting/toggle
* Describe each setting/toggle
* Managed Display Mode in Nvidia Control Panel missing

## Notes

* Restart your system when you change settings (Cap Frame X; EXM App; Windows Settings; Overlays)
* Disable any overlays (Discord; Steam; HWiNFO etc.)
* Cap Frame X requires you to click the process in the GUI to start capturing the metrics
* Cap Frame X seems unreliable high amount of FPS to test metrics for the FPS counter: 

       1. System > Display > Graphics turn the following toggles off:
          Optimizations for windowed games
          Hardware-accelerated GPU scheduling
          Variable refresh rate
  
* Make sure to run a effective system (disable as many processes without breaking the system)
* Leave security features on!


# Warning/Disclaimer

All the changes & downloads done by you to the software & hardware is done at your own risk. Restart whenever you do apply changes to should require a restart of the Windows Operating System.

#### Under (heavy) load

Test on maximum settings (Cinematic , V-Sync On, Ray Tracing, Shadows, Volumetric fog and Lighting) with a game that is demanding: Crimson Desert (uses Black Space Engine see : https://thegameswiki.com/crimson-desert/wiki/blackspace-engine).

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
* Cap Frame X
* .Net Framework 9.0.14
* Nvidea App
* Nvidea Control panel
* Cap Frame X
* .Net Framework 9.0.14
* Msi Utility v3
* Winhance
* 

## Start

Start with a fresh/clean Windows install from the official Lenovo website. Don't make an local account since it will install Windows 11 22H2 which isn't supported since 10/2025. Install the dependancies.

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
* Windows 11 will restart your device several times and lead you to the lock screen. Depending on the options you set, it will keep all your files, apps, and user accounts.

### Dependancies hyperlinks

* Lenovo Windows Image      https://support.lenovo.com/us/en/solutions/ht103653

* Lenovo Vantage            https://www.lenovo.com/us/en/software/vantage

* HWiNFO                    https://www.hwinfo.com/

* EXM app                   https://exmtweaks.com/en-eu

* MSI Afterburner           https://www.msi.com/Landing/afterburner/graphics-cards

* Rivatuner                 Mark the option checked during installation of MSI Afterburner

* Nvidea Drivers            https://www.nvidia.com/en-us/geforce/drivers/

* Nvidea Control Panel      Should be installed on your device

* Cap Frame X               https://www.capframex.com/
                 
* .Net Framework 9.0.14     https://dotnet.microsoft.com/en-us/download/dotnet/9.0

* Msi Utility v3            https://github.com/Sathango/Msi-Utility-v3

* Winhance                  https://winhance.net/

## EXM App

Configuration of options available and what they do.

https://exmtweaks.com/en-eu

plus [+] = toggled on in the app

minius [-] = toggled off in the app

## Cap Frame X

If you have ever looked at game benchmarks on the internet, you might have come across all these terms. But what exactly is hidden behind them is probably not clear to everyone and that's why we want to provide some clarity.Explanation Metrics:

https://www.capframex.com/blog/post/Explanation%20of%20different%20performance%20metrics

Also make sure to download & install the Beta version listed on their github releases page (at the time of writing beta_1.8.4)

#### Metrics used for Cap Frame X

* GPU Core (MHz)
* GPU Memory (MHz)
* GPU Core (%)
* GPU Hot Spot (°C)
* GPU Memory (%)
* GPU Memory Junction (°C)
* GPU Active Time Average (ms)
* Framerate (FPS)
* Frametime Average (ms) 
* Frametime 'Graph'
* CPU Package (°C)
* CPU Total (%)
* RAM Usage (%)



## MSI Afterburner & RivaTuner

https://www.msi.com/Landing/afterburner/graphics-cards

### 

### Nvidea App

### Nvidea Control Panel

