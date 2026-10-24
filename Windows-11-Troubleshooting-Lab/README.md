# Windows 11 Troubleshooting and System Repair Lab

## Overview

This hands-on lab documents a Windows 11 troubleshooting session performed on an Acer Nitro 5 laptop with 8 GB of RAM. The objective was to investigate system health, review Windows logs, check system resources, and diagnose and repair Windows system-file corruption using built-in troubleshooting tools.

## Environment

- **Operating System:** Windows 11
- **Device:** Acer Nitro 5
- **Installed RAM:** 8 GB
- **Tools:** Task Manager, Event Viewer, Command Prompt, DISM, System File Checker (SFC)

## Troubleshooting Process

### 1. System Resource Assessment

Used Task Manager to review system resource utilization.

**Findings**
- Memory usage was approximately 6.1–6.3 GB out of 7.8 GB available during observation.
- CPU usage was low while idle.
- Disk activity was low during the initial assessment.
- The highest-memory process was not recorded.

**Interpretation:** Memory usage was relatively high for an 8 GB system. Additional process-level investigation would be needed to identify the largest memory consumer.

### 2. Event Viewer Investigation

Reviewed Windows event logs and identified a TPM-WMI warning, Event ID 1803.

The warning indicated that a Platform Key-signed Key Exchange Key (KEK) could not be found for the device.

**Action:** Recorded the warning for further investigation. No BIOS, TPM, or Secure Boot settings were changed.

### 3. Disk Space and Network Configuration

Used built-in Command Prompt tools to inspect disk space and network configuration.

**Findings**
- Approximately 78 GiB of free space was available on the C: drive.
- An IPv4 address and default gateway were present in the network configuration.

**Interpretation:** These checks confirmed available disk space and basic network configuration. They did not independently verify internet connectivity or DNS resolution.

### 4. DISM Component Store Diagnosis and Repair

Ran the following command to scan the Windows component store:

`DISM /Online /Cleanup-Image /ScanHealth`

**Initial result:** The component store was reported as repairable.

Then ran:

`DISM /Online /Cleanup-Image /RestoreHealth`

The repair operation reached 100%. A subsequent health check was successful.

Verification command:

`DISM /Online /Cleanup-Image /CheckHealth`

**Final result:** No component store corruption detected.

### 5. System File Checker Repair

Initially ran:

`sfc /verifyonly`

**Initial result:** Windows Resource Protection found integrity violations.

Then ran:

`sfc /scannow`

**Result:** Windows Resource Protection found corrupt files and successfully repaired them.

Finally, ran:

`sfc /verifyonly`

**Final result:** Windows Resource Protection did not find any integrity violations.

## Final Outcome

- Identified Windows component store corruption.
- Successfully completed the system-file repair process.
- Confirmed that the component store check reported no corruption.
- Verified that SFC no longer detected system-file integrity violations.
- Practiced documenting findings and interpreting diagnostic results.

## Skills Demonstrated

- Windows 11 troubleshooting
- Task Manager resource monitoring
- Windows Event Viewer investigation
- Command-line diagnostics
- DISM component store servicing
- System File Checker (SFC)
- Technical documentation and troubleshooting notes

## Limitations and Follow-up

This lab verified Windows component-store and system-file integrity. It did not establish that the TPM-WMI warning caused a performance issue, nor did it measure system performance before and after the repairs.

Potential follow-up work includes reviewing startup applications, identifying the highest-memory processes, checking network connectivity and DNS resolution, and comparing system behavior after the repairs.
