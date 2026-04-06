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
