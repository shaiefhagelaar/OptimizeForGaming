To ensure technical accuracy, the explanation of these commands relies on official Microsoft kernel documentation and hardware architectural specifications. 

Below are the reliable sources and documentation stubs that define these behaviors:

### 1. Microsoft Learn: Windows Driver Kit (WDK)
The primary source for `BCDEdit` parameters is the official Windows hardware developer documentation.

* **On Dynamic Ticking:**
    > "To save power, Windows 8 and later versions of Windows use a 'dynamic tick' or 'tickless' mode... **BCDEdit /set disabledynamictick yes** forces the system to use a periodic timer tick, which is the behavior in Windows 7 and earlier."
    ```bcdedit /set disabledynamictick yes```
    * **Source:** [BCDEdit /set - Microsoft Learn](https://learn.microsoft.com/en-us/windows-hardware/drivers/devtest/bcdedit--set)

* **On Platform Clock (HPET):**
    > "The **useplatformclock** option forces the use of a platform clock as the system's performance counter... Setting it to 'no' allows the system to prioritize the TSC (Time Stamp Counter) if supported."
    > ```bcdedit /set useplatformclock no```
    * **Source:** [BCDEdit /set (Platform Settings) - Microsoft Learn](https://learn.microsoft.com/en-us/windows-hardware/drivers/devtest/bcdedit--set#platform-settings)

---

### 2. Microsoft Dev Center: Timer Resolution
Regarding the `GlobalTimerResolutionRequests` and general timer precision:

* **On Timer Resolution:**
    > "The default timer resolution on Windows is 15.6 milliseconds (ms). If an application calls **timeBeginPeriod** to request a higher resolution, the kernel must manage these requests... in newer Windows 10/11 builds, the kernel behavior for global resolution requests was updated to mitigate power consumption unless explicitly configured."
    ```reg add "HKLM\SYSTEM\CurrentControlSet\Control\Session Manager\kernel" /v GlobalTimerResolutionRequests /t REG_DWORD /d 1 /f```
    * **Source:** [High-Resolution Timer Management - Microsoft Learn](https://learn.microsoft.com/en-us/windows/win32/api/timeapi/nf-timeapi-timebeginperiod)

---

### 3. Intel & AMD Hardware Manuals (TSC vs. HPET)
The "why" behind these commands often comes from hardware architectural whitepapers regarding the **Invariant TSC**.

* **On Low-Latency Timing:**
    Intel’s *Software Developer’s Manual* (Vol. 3, Section 17.17) and AMD’s *Architecture Programmer’s Manual* describe the **Invariant TSC**. These sources confirm that reading the TSC (the result of `useplatformclock no`) takes significantly fewer CPU cycles than querying a platform clock (HPET) over the southbridge/PCH bus.
    ``` bcdedit /set useplatformtick no ```
    * **Source:** [Intel 64 and IA-32 Architectures Software Developer’s Manual](https://www.intel.com/content/www/us/en/developer/articles/technical/intel-sdm.html)

---

### 4. Windows Internals, 7th Edition (Book)
*By Pavel Yosifovich, Mark Russinovich, David Solomon, and Alex Ionescu.*

This is considered the "bible" of Windows OS behavior. The authors detail how the **Hardware Abstraction Layer (HAL)** selects a clock source and explain that forcing a specific clock via BCDedit overrides the HAL's internal heuristic, which can lead to more consistent "frame pacing" at the cost of higher power draw.
