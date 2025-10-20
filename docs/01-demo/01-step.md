# Windows 365 Reserve — Hands‑On Lab

**Audience:** IT professionals and lab participants  
**Duration:** ~60 minutes  
**Prerequisites:** Lab VM with Edge; admin‑provided UPN/password; tenant with Windows 365 Reserve or trial license; Intune access.  
**Goal:** Configure a Reserve provisioning policy, provision/deprovision Reserve Cloud PCs, and validate the user experience.

@lab.Title

To begin, log into the virtual machine using the following credentials: +++@lab.VirtualMachine(Win11-Pro-Base).Password+++

**Note:** Text formatted as an +++example+++ represents type text. Clicking on this text will automatically insert it to prevent any typing errors.

Click **Next** to get Started!
===

## 1) Validate licensing (tenant‑level)

1. On the lab VM, open **Microsoft Edge** and go to `https://admin.microsoft.com/`.  
2. From the left menu, select **Show all** → **Billing** → **Your products**.  
3. Under **Your products**, locate **Windows 365 Reserve** or **Windows 365 Reserve Trial**. Confirm **Purchased quantity** and **Available quantity** are present.  
4. _Tip:_ If **Assigned licenses** shows 0, that's expected-user assignments are handled later.

> **Note:** The **Reserve** license is managed at the tenant level, not assigned directly to users.

===

## 2) Validate user group (Intune)

1. Go to `https://intune.microsoft.com/`.  
2. From the left menu, select **Groups**.  
3. Search for the **lab username** provided by your instructor.  
4. Open the group → **Members**. Confirm the lab user is the **only member**.

===

## 3) Create a Reserve provisioning policy (Intune)

1. In Intune: **Devices** → **Windows 365** → **Provisioning policies** → **Create policy**.  
2. Under **General** Provide the following:
   - **Name & Description** (e.g., UserName - Reserve Policy).  
   - **Experience:** *Access a full Cloud PC* (N/A if you only have Reserve licenses). 
   - **License type:** *Reserve* (N/A if you only have Reserve licenses).  
   - **Geography:** Select the geography that matches your user group and data residency requirements.  
3. Click **Next**
4. Under Image Click **Next**.
   - **(Optional):** Change the gallery image version if desired. *(Note: Windows 10 may appear but is not supported by Windows 365 Reserve.)*  
5. Under **Configurations** Click **Next**.
   - **Configuration (Optional):** Set **Language & region** and **Cloud PC naming** template (if needed). 
6.  Under **Scope Tags** Click **Next**.
   - **Scope tags (Optional):** Add as required.  
7. Under **Assignments:** Add user groups → select the lab user group you validated earlier → **Select** → **Next**.
8. Under **Review + create** Validate your inputs provided and select **Create**.
> **Note:** Reserve Cloud PCs are **not** auto‑provisioned; admins initiate provisioning on demand.

===

## 4) Provision a Reserve Cloud PC

1. In Intune: **Devices** → **Windows 365** → **Provisioning policies**
2. In the **Search box** search using your **%username%** or **policy name** and select you **Provisioning policiy**.
3. From **Provisioning policy** → **Cloud PC users** tab, select the **user(s)** to provision (use search/filters as needed).  
4. Click **Provision** on the toolbar → confirm in the pop‑up → **Provision** again.  
5. Watch for the **provisioning notification**; status changes from **Not provisioned** → **Provisioning** → **Provisioned** (typically ~30 minutes).

===

## 5) Deprovision a Reserve Cloud PC

1. In Intune: **Devices** → **Windows 365** → **Provisioning policies**
2. In the **Search box** search using your **%username%** or **policy name** and select you **Provisioning policiy**.
3. From **Devices** or **Cloud PC users**, select the **Provisioned** device row(s).  
4. Click **Deprovision now** → confirm in the pop‑up → **Deprovision now** again.  
5. Status updates to **De‑provisioned**; **days left** pauses until reprovisioned or expiry.

> **Best practice:** Deprovision when users return to their primary device to avoid data loss; ensure data is backed up to cloud storage before deprovisioning.

===

## 6) End‑user experience: Connect to a Reserve Cloud PC from a Web Browser

1. Launch **Windows App (web client)**: `https://windows.cloud.microsoft/#/devices`.  
2. Sign in with the **username/password**.  
3. Your **Reserve** Cloud PC should appears on the device card. 
4. Click the **3 dots** in the lower right corener of the card to display avaible options.
   - Use actions like **Restart**, **Reset**, **Stop usage**, **View details**.  
5. The **Reserve** tag shows **last date of access**; the timer refreshes every 24 hours and highlights at **3 days left**. In‑app notification appears on the **last day**.

> **Note:** **Days left** (per seat) is visible under **Devices** and **Cloud PC users**. The **annual expiration period** shows license validity from assignment date.

===

## 7) End‑user experience: Connect to a Reserve Cloud PC from The Windows App

1. Click the Start Button and Launch **Windows App**.  
2. Sign in with the **username/password**.  
3. Your **Reserve** Cloud PC should appears on the device card. 
4. Click the **3 dots** in the lower right corener of the card to display avaible options.
   - Use actions like **Restart**, **Reset**, **Stop usage**, **View details**.  
5. The **Reserve** tag shows **last date of access**; the timer refreshes every 24 hours and highlights at **3 days left**. In‑app notification appears on the **last day**.

> **Note:** **Days left** (per seat) is visible under **Devices** and **Cloud PC users**. The **annual expiration period** shows license validity from assignment date.

===

## 8) Congratulations

You have finished this hands! 

Click **End** to close this Lab







<!--
To edit the lab manual, click the hamburger menu in the top-right corner and select **"Edit Instructions"**. This will open the editor where you can modify the instructions.

Instructions are written in Markdown. For detailed guidance on syntax, please refer to the following documentation:

[Creating Instructions with Markdown Syntax](https://docs.skillable.com/docs/creating-instructions-with-markdown-syntax)

If you want to manage your instructions outside of Skillable Studio like Github, please refer to the following documentation:

[Manage Instructions Outside of Studio](https://docs.skillable.com/docs/manage-instructions-outside-of-studio)

For saving changes made to the virtual machine, please refer to this guide:  

[Committing Changes to a Virtual Machine](https://docs.skillable.com/docs/committing-changes-to-a-lab)

**Note:** When prompted, select **"Commit my changes and update this lab profile"** to ensure your changes are saved.

Changes made to the virtual machine will take effect immediately after committing. You may restart the lab instance if you wish to view these changes.

**Note:** Changes to the instructions will be saved automatically, so the commit process applies only to modifications to the virtual machine.

Should you require any assistance, feel free to contact us.

**Please remove this message once it is no longer needed.**

**TESTING**
-->



