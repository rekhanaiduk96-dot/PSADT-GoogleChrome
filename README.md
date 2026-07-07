# PSADT Deployment Package: Google Chrome Enterprise 🌐

This repository contains a standardized, enterprise-grade application deployment package for **Google Chrome Enterprise** utilizing the **PowerShell App Deployment Toolkit (PSADT)** framework. It is explicitly optimized for fully silent automated deployment workflows via **Microsoft Intune** or MECM (SCCM).

---

## 📋 Package Metadata & Architecture
- **Application Vendor:** Google
- **Application Name:** Chrome Enterprise
- **Target Operating System:** Windows 10 / Windows 11 (x64)
- **Installer Base Type:** Windows Installer (`.msi`)
- **Execution Delivery:** NonInteractive / Fully Silent (`/qn` execution parameters)

> 💡 **Repository Notice:** To maintain a compliant, lightweight portfolio footprint, this public repository tracks **custom deployment scripts and documentation logic only**. Raw commercial vendor installation binaries are intentionally excluded.

---

## 🚀 Deployment Command Lines

When configuring this application package within your Microsoft Intune Tenant or Endpoint Management console, utilize these standardized deployment string entries:

*   **Install Command:**
    ```cmd
    Invoke-AppDeployToolkit.exe -DeploymentType Install -DeployMode Interactive
    ```
*   **Uninstall Command:**
    ```cmd
    Invoke-AppDeployToolkit.exe -DeploymentType Uninstall -DeployMode Interactive
    ```

---

To compile and execute this deployment package locally for sandbox environment validation, you must assemble the full PSADT structure manually:

1. Clone or download this repository (containing `Invoke-AppDeployToolkit.ps1`) into your local workspace folder.
2. Download the standard, unedited **PSADT core framework toolkit (v4.x)** from the official PSADT community portal. 
3. Extract and place the standard PSADT core files and directories (like the `PSAppDeployToolkit` folder) directly alongside this `Invoke-AppDeployToolkit.ps1` script file.
4. Create a subdirectory named **`Files`** at the root level of your workspace.
5. Download the official, raw vendor installer binary (`googlechromestandaloneenterprise64.msi`) from the Google Enterprise portal and drop it inside that newly created `Files` folder.
6. Open an elevated, administrative PowerShell console session and run the following command to test the silent deployment:
   ```powershell
   .\Invoke-AppDeployToolkit.ps1
