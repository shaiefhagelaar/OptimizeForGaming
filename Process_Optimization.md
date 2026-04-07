# Processes

List of processes that are active on Windows 11 instance (25H2). 200+ processes should be able to dial it down to double digits.

Source: https://windowsforum.com/threads/debloat-windows-11-practical-guide-to-remove-bloatware-safely.389080/


## System-wide, permanent removal (Advanced — DISM)​

Using the DISM method for package removement might cause issues and break certain packages. Do your due dilligence and research the packages that your PERMENANTLY removing. 

    Admin PowerShell or CMD: DISM /Online /Get-ProvisionedAppxPackages | select-string PackageName to identify full package names.
    Remove the provisioned package exactly: DISM /Online /Remove-ProvisionedAppxPackage /PackageName:FULL_PACKAGE_NAME
    Reboot and verify.

Important: If the package is already registered with existing user profiles, remove it from those profiles first with Remove-AppxPackage. DISM removal is for the image and future profiles.

## Troubleshooting and recovery​

* If an app removal breaks functionality, restore the System Restore Point or perform an in-place upgrade using the Media Creation Tool to repair system files without affecting personal data.
* If a required runtime (Visual C++/NET) is removed inadvertently, reinstall runtimes from Microsoft’s official download pages or reinstall affected apps to restore dependencies.
* If a DISM operation failed, double-check the package full name string — it must match exactly, including version/architecture/publisher suffixes. Microsoft’s DISM docs show exact syntax to avoid errors.




## List of services

Windows services can be running in the background and cause 'sluggish' feel to the Windows OS (operating system). So you have the option to 'turn off' a specific service: Start; stop; pause; resume; restart. ! Make sure to check what the service does before editing ! 

List of local Extended services running on the Laptop:

* ActiveX Installer (AxInstSV)

Essential, check the signature if needed be.

Source: https://malwaretips.com/blogs/service-host-activex-installer/
  
* Agent Activation Runtime_dc3ef

svchost.exe is a system process that hosts and manages Windows services running from DLL files rather than standalone executable files, allowing Windows to modularize and efficiently manage background tasks.

svchost.exe loads and runs Windows services, such as networking, Windows Update, audio, and many others. Multiple instances of svchost.exe can run simultaneously, each hosting different services. This helps with stability and security—if one service fails, it doesn't crash all services.

Source: https://www.smartpcutilities.com/windows-service.html?name=AarSvc&os=win11

* Aggregated Data Platform Service (Disabled)

Gathers telemetry you can disable it.

https://www.thewindowsclub.com/windows-10-telemetry

* App Readiniss
* Application Identity
* Application Information
* Application Layer Gateway Service
* Appx Deployment Service (AppxSVC)
* Auto Time Zone Updater
* AVCTP Service
* Background Intelligent Transfer Service
* Background Tasks Infrastructure Service
* Base Filtering Engine
* Bitlocker Drive Encryption Service
* Block Level Backup Engine Service
* Bluetooth Audio Gateway Service
* Bluetooth Support Service
* Bluetooth USer support Service_dc3ef
* brlapi
* Capability Access Manger Service
* CaptureService_dc3ef
* Celluar Time
* Certificate Propagation
* Client License Service (ClipSVC)
* Clipboard User Service_dc3ef
* Cloud Backup and Restore Service_dc3ef
* Cloud Backup and Restore Service_dc3ef
* CNG Key Isolation
* COM+ Event System
* COM+ System Application
* Connected Devices Platform Service
* Connected Devices Platform User Service_dc3ef
* Connected User Experiences and Telemetry
* ConsentUX User Service_dc3ef
* Contact Data_dc3ef
* CoreMessaging
* Credential Manager
* CredentialEnrollmentMangerUserSvc_dc3ef
* Critical Service for Lenovo Vantage
* Cryptographic Services
* Data Sharing Service
* Data Usage
* DCOM Server Process Launcher
* Declared Configuration(DC) service
* Delivery Optimization
* Device Association Service
* Device Install Service
* Device Management Enrollment Service
* Device Management Wireless Application Protocol (WAP) Push message Routing Service
* Device Setup Manager
* Device AssociationBroker_dc3ef
* DevicePicker_dc3ef
* DevicesFlow_dc3ef
* DevQuery Background Discovery Broker
* DHCP Client
* Diagnostic Execution Service
* Diagnostic Policy Service
* Diagnostic Service Host
* Diagnostic System Host
* Discord System Helper
* Display Enhancement Service
* Display Policy Service
* Distributed Link Tracking Client
* Distributed Transaction Coordinator
* DNS Client
* Downloaded Maps Manager
* Elevoc Control Service
* Embedded Mode
* Encrypting File System (EFS)
* Enterprise App Management Service
* EXM Tweaks Service
* Extensible Authentication Protocol
* File History Service
* Function Discovery Provider Host
* Function Discovery Resource Publication
* GameDVR and Broadcast User Service_dc3ef
* GameInput Service
* Geolocation Service
* GraphicsPerfSvc
* Group Policy Client
* Host Network SErvice
* Hotpatch Monitoring Service
* Human Interface Device Service
* HV Host Service
* Hyper-V Data Exchange Service
* Hyper-V Guest Service Interface
* Hyper-V Guest Shutdown Service
* Hyper-V Heartbeat Service
* Hyper-V Host Compute Service
* Hyper-V Powershell Direct Service
* Hyper-V Remote Desktop Virtualization Service
* Hyper-V Time Synchronization Service
* Hyper-V Volume Shadow Copy Reuquestor
* IKE and AuthIP IPsec Keying Modules
* Intel(R) Audio Service
* Intel(R) Dynamic Application Loader Host Interface Service
* Intel(R) Dynamic Tuning Technology Telemetry Service
* Intel(R) Innocation Platform Framework Service
* Intel(R) Management Engine WMI Provider Registration
* Intel(R) Platform License Manager Service
* Internet Connection Sharing (ICS)
* Inventory and Compatibility Appraisal service
* IP Helper
* IP Translation Configuration Service
* IPsec Policy Agent
* Kerberos Local Key Distribution Center
* Killer Analytics Service
* Kerberos Local Key Distribution Center
* Killer Network Service
* Killer Provider Data Helper Service
* Killer Smart AP Selection Service
* KtmRm for Distributed Transaction Coordinator
* Language Experience Service
* Lenovo Experience Service
* Lenovo Fn and function keys service
* Lenovo Whisper Mode Service
* Link-Layer Topology Discovery Mapper
* Local Profile Assistant Service
* Local Session Manager
* McpManagementService
* MessagingService_dc3ef
* Microsoft Account Sign-in Assistant
* Microsoft Defender Antivirus Network Inspection Service
* Microsoft Defender Antivirus Service
* Microsoft Defender Core Service
* Microsoft iSCSI Initiator Service
* Microsoft Passport
* Microsoft Passport Container
* Microsoft Software Shadow Copy Provider
* Microsoft Storage Spaces SMP
* Microsoft Store Install Service
* Microsoft Usage and Quality Insights
* Microsoft Windows SMS Router Service
* Mobile Connectivity Management Service
* Mozilla Maintenance Service
* Nahimic service
* Natural Authentication
* Net.Tcp Port Sharing Service
* Netlogon
* Network Connected Devices Auto-Setup
* Network Connection Broker
* Network Connections
* Network Connectivity Assistant
* Network List Service
* Network Location Awareness
* Network Setup Service
* Network Store Interface Service
* Now Playing Session Manager Service_dc3ef
* NVIDIA Display Container LS
* NVIDIA FrameView SDK service
* NVIDIA LocalSystem Container
* OpenSSH AUthentication agent
* Optimize drives
* P9RdrService_dc3ef
* Prental Controls
* Patments and NFC/SE Manager
* PenService_dc3ef
* Performance Counter DLL Host
* Performance Log & Alerts
* Phone Service
* Plug and Play
* Protable Device Enumerator Service
* Power
* Print Device Configuration Service
* Print Spooler
* Printer Extensions and Notifications
* PrintScanBrokerService
* PrintWorkflow_dc3ef
* Problem Reports Control Panel Support
* Program Compatibility Assistant Service
* Quality Windows Audio Video Experience
* Radio Management Service
* Realtek Audio Universal Service
* Recommended Troubleshooting Service
* ReFS Dedup Service
* Remote Access Auto Connection Manager
* Remote Access Connection Manager
* Remote Desktop Configuration
* Remote Desktop Services
* Remote Desktop Services UserMode Prot Redirector
* Remote Procedure Call (RPC)
* Remote Procedure Call (RPC) Locator
* Remote Registry
* Retail Demo Service
* Routing and Remote Access
* RPC Endpoint Mapper
* Secondary Logon
* Secure Socket Tunneling Protocol Service
* Security Accounts Manager
* Security Center
* Sensor Data Service
* Sensor Monitoring Service
* Sensor Service
* Server
* Shared PC Account Manager
* Shell Hardware Detection
* Smart Card
* Smart Card Device Enumeration Service
* Smart Card Removal Policy
* SNMP Trap
* Software Protection
* SpitCameraEventService
* Spot Verifier
* SSDP Discovery
* State Repository Service
* Steam Client Servie
* Still Image Acquisition Events
* Storage Service
* Storage Tiers Management
* Sync Host_dc3ef
* SysMain
* System Event Notification Service
* System Events Broker
* System Interface Foundation Service
* Task Scheduler
* TCP/IP NetBIOS Helper
* Telephony
* Text INput Management Service
* Themes
* Thunderbolt(TM) Application Launcher
* Thenderbolt(TM) Peer to Peer Shortcut
* Time Broker
* Tobii Runtime Service
* Tobii Runtime Service
* Tobii Runtime Service
* Tobii Service
* Udk User Service_dc3ef
* Universal Device Client Service
* Update Orchestrator Service
* UPnP Device Host
* User Data Access_dc3ef
* User Data Storage_dc3ef
* User Manager
* User Profile Service
* Virtual Disk
* Visual Studio Installer Elevation Service
* Visial Studio Standard Collector Service 150
* Volume Shadow Copy
* WaaSMedicSvc
* WalletService
* Warp JIT Service
* Web Account Manager
* Web Threat Defendse Service
* Web Threat Defense User Service_dc3ef
* WebClient
* Wi-Fi Direct Services Connection Manager Service
* Windows Audio
* Windows Audio Endpoint Builder
* Windows Backup
* Windows Biometirc Service
* Windows Camera Frame Server Windows Frame Server Monitor
* Windows Connect now - Config Registrar
* Windows Connection Manager
* Windows Defender Firewall
* Windows Encryption Provider Host Service
* Windows Error Reporting Service
* Windows Event Collector
* Windows Event Log
* Windows Font Cache Service
* Windows Helath and Optimized Experiences
* Windows Image Acquisition (WIA)
* Windows Insider Service
* Windows Installer
* Windows License Manager Service
* Windows Management Instrumentation
* Windows Management Service
* Windows Media Player Network Sharing Service
* Windows MIDI Service
* Windows Mobile Hotspot Service
* Windows Modules Installer
* WIndows Perception Simulation Service
* Windows Push Notification System Service
* Windows Push Notifications User Service_dc3ef
* Windows PushToInstall Service
* Windows Remote Management (WS-Management)
* Windows Search
* Windows Security Service
* Windows Time
* Windows Update
* Windows Virtual AUdio Device Proxy Service
* WinHTTP Web Proxy Auto-Discovery Service
* Wired AutoConfig
* WLAN AutoConfig
* WMI Performance Adapter
* Work Folders
* Workstation
* WSAIFabricSvc
* WWAN AutoConfig
* XBox Acccessory Management Service
* XBox Live Auth Manager
* Xbox Live Game Save
* Xbox Live Networking Service
* XTUOCDriverService
