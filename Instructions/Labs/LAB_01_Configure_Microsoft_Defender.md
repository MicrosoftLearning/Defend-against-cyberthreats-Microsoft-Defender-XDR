---
lab:
  title: Configure Microsoft Defender
  module: Configure the Microsoft Defender XDR environment
  description: In this exercise you will provision your Microsoft Defender XDR environment, onboard client workstations in Defender for Endpoint and perform a simulated attack scenario on a client workstation.
  duration: 5 minutes
  level: 300
  islab: true
  primarytopics:
    - Microsoft Defender
    - Microsoft Defender XDR
---

You're a Security Operations Analyst working at a company that is implementing Microsoft Defender XDR. Your role is to
guide the company’s IT team in defending against threats with Microsoft Defender (XDR). The company’s executives are very concerned that all guidelines are followed and that all requirements are met when you complete the activities in their environment.

# Configure the Microsoft Defender XDR environment

In this exercise you will provision your Microsoft Defender XDR environment, onboard client workstations in Defender for Endpoint and perform a simulated attack scenario on a client workstation.

This exercise should take approximately **10 - 15** minutes to complete.

>**Important:**
> You'll need to have access to a Microsoft 365 E5 Tenant with a Microsoft Defender for Endpoint P2 license to perform the following exercises. You will also need to have Microsoft Windows 10 or 11 client workstations to onboard and perform simulated attacks on.

## Task 1- Preparing the Microsoft Defender XDR workspace

1. In the Microsoft Edge browser, go to the Microsoft Defender portal at (<https://security.microsoft.com>).
1. On the **Microsoft Defender** portal, from the navigation menu, select **Home** from the left.

    >**Note:** You may need to scroll all the way to the menu top.

1. Scroll down the menu items to **Assets** and select **Devices**.

1. The process to deploy the Defender XDR workspace should start and you should see messages saying *loading and Initializing* briefly displayed at the top of the page, and then you're going to see an image of a coffee mug and a message that reads: **Hang on! We're preparing new spaces for your data and connecting them.** It takes approximately 5 minutes to finish. *Leave the page open and make sure it finishes since it's required for the next Lab.*

    >**Note:** Disregard pop-up error messages saying *Some of your data cannot be retrieved*. If the message "Hang on! We're preparing new spaces for your data and connecting them" does not appear, or the "Settings > Microsoft Defender XDR > Account" page opens, but you see the message *Failed to load data storage location. Please try again later*, select "Alert service settings" from the "General" menu.

1. When the new workspace initialization completes successfully, the **Home** portal page will display a **Get your SIEM and XDR in one place** banner. And, in **Settings**, the Microsoft Defender XDR General settings for Account, Email notifications, **Preview Features**, Alert service settings, Permissions and roles and Streaming API are now turned on.

### Task 2: Apply Microsoft Defender for Office 365 preset security policies

In this task, you'll assign preset security policies for Exchange Online Protection (EOP) and Microsoft Defender for Office 365 in the Microsoft 365 security portal.

1. Log in to WIN1 virtual machine as Admin with the password: **Pa55w.rd**.  

1. Start the Microsoft Edge browser.

1. In the Microsoft Edge browser, go to the Microsoft Defender XDR portal at (<https://security.microsoft.com>).

1. In the **Sign in** dialog box, copy, and paste in the tenant Email account for the admin username provided by your lab hosting provider and then select **Next**.

1. In the **Enter password** dialog box, copy, and paste in the admin's tenant password provided by your lab hosting provider and then select **Sign in**.

    >**Note:** If you receive a message "The operation could not be completed. Please try again later. If the problem persists, contact Microsoft support." just click **OK** to continue.  

1. If shown, close the Microsoft Defender XDR quick tour pop-up window. **Hint:** Later in this lab, you'll need to wait until the Defender workspace is provisioned, you can take this time to navigate through the guided tours to learn more about Microsoft Defender XDR.

1. From the navigation menu, under *Email & Collaboration* area, select **Policies & rules**.

1. On the *Policy & rules* dashboard, select **Threat policies**.

1. On the *Threat policies* dashboard, select **Preset Security Policies**.

    >**Note:** If you receive the message *"Client Error - Error when getting bip rule"* select **OK** to continue. The error is due to the hydration status of your tenant at Office 365 which is not enabled by default.

    >**Note:** If you receive the message *"Client Error - An error occurred when retrieving preset security policies. Please try again later."* select **OK** to continue. Refresh your browser using **Ctrl+F5**.

1. On the **Learn about preset security policies** *pop-out* page, select **Close**.

1. Under *Standard protection*, select **Manage protection settings**. **Hint:** If you see this option grayed out, refresh your browser using **Ctrl+F5**.

1. In the *Apply Exchange Online Protection* section, select **Specific recipients** and under **Domains** start writing your tenant's domain name, select it, and then select **Next**.

    >**Hint:** Your tenant's domain name is the same name that you have for your admin account, it might be something like *WWLx######.onmicrosoft.com*. Notice that this configuration applies policies for anti-spam, outbound spam filter, anti-malware, anti-phishing.

1. In the *Apply Defender for Office 365 protection* section, apply the same configuration as the previous step and select **Next**. Notice that this configuration applies policies for anti-phishing, Safe Attachments, Safe Links.

1. In the *Impersonation protection* section, select **Next** four times (4x) to continue.

1. In the *Policy mode* section, make sure the **Turn on the policy when finished** radio button is selected, and then select **Next**.

1. Read the content under *Review and confirm your changes* and select **Confirm** to apply the changes and then select **Done** to finish.

    >**Note:** If you receive the message *"The URI '<https://outlook.office365.com/psws/service.svc/AntiPhishPolicy>' is not valid for PUT operation. The URI must point to a single resource for PUT operations."* just select **OK** and then select **Cancel** to return to the main page. You will see that *Standard protection is on* option enabled.

1. Under *Strict protection*, select **Manage protection settings**. **Hint:** *Strict protection* is found under "Email & Collaboration - Policies & rules - Threat policies - Preset security policies".

1. In the *Apply Exchange Online Protection*, select **Specific recipients** and under **Groups** start writing **Leadership**, select it, and then select **Next**. Notice that this configuration applies policies for anti-spam, outbound spam filter, anti-malware, anti-phishing.

1. In the *Apply Defender for Office 365 protection* section, apply the same configuration as the previous step and select **Next**. Notice that this configuration applies policies for anti-phishing, Safe Attachments, Safe Links.

1. In the *Impersonation protection* section, select **Next** four times (4x) to continue.

1. In the *Policy mode* section, make sure the **Turn on the policy when finished** radio button is selected, and then select **Next**.

1. Read the content under *Review and confirm your changes* and select **Confirm** to apply the changes and then select **Done** to finish.

    >**Note:** If you receive the message *"The URI '<https://outlook.office365.com/psws/service.svc/AntiPhishPolicy>' is not valid for PUT operation. The URI must point to a single resource for PUT operations."* just select **OK** and then select **Cancel** to return to the main page. You will see the *Strict protection is on* option enabled.

## You have completed the lab
