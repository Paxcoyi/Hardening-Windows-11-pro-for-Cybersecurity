Windows 11 Security Baseline Implementation (Hardening)
Description: Configuration of a high-security workspace and deployment of a virtualized analysis laboratory.

1. Hardened OS Deployment
In this step, we install Windows 11 Pro, aiming to maximize the operating system's potential in a lightweight yet secure manner.

1.1 Windows 11 Pro Installation
Installation from the official website.

<img width="1291" height="982" alt="image" src="https://github.com/user-attachments/assets/4bb58ffa-6b5a-4d84-ab24-438c160213cd" />


1.2 Clean Installation
Used an official Windows 11 Pro ISO processed with Rufus.

<img width="472" height="662" alt="image" src="https://github.com/user-attachments/assets/fc8f1c31-7900-4c4d-86ef-7bd6f88285db" />


Privacy by Design: Policies were applied during the flashing process to:

Remove the mandatory Microsoft account requirement (Local Account only).

Disable telemetry and privacy data collection.

Skip unnecessary hardware requirements to improve performance.

This step prevents leaving personal data such as emails and telemetry in Windows, allowing us to skip unnecessary steps that clutter the OS. Note: BitLocker encryption activation is left as an optional consideration based on the sensitivity of the information or work environment.

Additional Step: During the network setup phase, we can disconnect from the internet for a clean installation by pressing Shift + F10 to open the terminal (CMD) and entering the command: OOBE\BYPASSNRO. After executing this command, the installation restarts, providing the "I don't have internet" option to continue.

<img width="1112" height="624" alt="image" src="https://github.com/user-attachments/assets/56aff743-78fb-4a2e-ba09-1bb1df010d30" />


2. Optimization and Cleaning (Debloating)
Initial Maintenance: Execution of a full Windows Update cycle and installation of critical drivers (GPU, Sound, Chipset).

Bloatware Removal: Manual uninstallation of unnecessary default applications (OneDrive, Sticky Notes, News Widgets) to reduce the attack surface and resource consumption.

3. System Hardening
Privilege Management: System configuration under the Principle of Least Privilege. A standard user account is used for daily tasks, requiring administrative credentials for any sensitive changes.

Active Security: Advanced Windows Defender configuration and maximum User Account Control (UAC) levels.

4. Virtualization and Testing Environments (Sandbox)
Hypervisor: Installation of VMware Workstation Pro. For the installation, the Pro version is recommended (currently free). To avoid spam, I recommend using TEMPMAIL for a temporary email address to protect sensitive personal data.

Guest Systems:

Windows 11 Pro: Configured as a controlled environment (Sandbox) with security hardening applied.

Linux Debian: Base installation updated and optimized for network tools.

Optimization: Installed VMware Tools for hardware acceleration and interface fluidity.

<img width="1683" height="901" alt="image" src="https://github.com/user-attachments/assets/20d4d358-e952-43b8-89dd-aba9d4a2abc9" />


5. Continuity and Recovery Strategy
Gold Images (Snapshots): Creation of initial Snapshots after reaching the optimal configuration state. This option allows you to save a copy from a specific point, enabling a rollback to a working state if anything fails.

Resilience: Capacity for immediate restoration against system failures or malware infections during security testing, guaranteeing laboratory persistence.
