---
lab:
  title: Configure Microsoft Defender
  module: Configure the Microsoft Defender XDR environment
  description: In this exercise you will provision your Microsoft Defender XDR workspace and apply the built-in Standard and Strict preset security policies to protect your tenant.
  duration: 15 minutes
  level: 200
  islab: true
  primarytopics:
    - Microsoft Defender
    - Microsoft Defender XDR
---

You're a Security Operations Analyst working at a company that is implementing Microsoft Defender XDR. Your role is to
guide the company’s IT team in defending against threats with Microsoft Defender (XDR). The company’s executives are very concerned that all guidelines are followed and that all requirements are met when you complete the activities in their environment.

# Configure the Microsoft Defender XDR environment

In this exercise you will provision your Microsoft Defender XDR workspace and apply the built-in Standard and Strict preset security policies to protect your tenant.

This exercise should take approximately **10 - 15** minutes to complete.

>**Important:**
> You'll need access to a Microsoft 365 E5 tenant with a Microsoft Defender for Endpoint P2 license to complete these exercises.

### Task 1: Preparing the Microsoft Defender XDR workspace

In this task, you'll provision the Microsoft Defender XDR workspace so that it's ready to collect data and surface security insights for the rest of the lab.

1. Sign in to the **WIN1** virtual machine as **Admin** with the password **Pa55w.rd**.

1. Open Microsoft Edge and navigate to the **Microsoft Defender XDR** portal at `https://security.microsoft.com`. Sign in with the Global Administrator account provided by your authorized lab hosting provider (ALH).

    >**Note:** If you receive the message *The operation could not be completed. Please try again later. If the problem persists, contact Microsoft support.*, select **OK** to continue.

1. If a quick tour pop-up window appears, close it. **Hint:** Later in this lab you'll need to wait while the Defender workspace is provisioned. You can use that time to explore the guided tours and learn more about Microsoft Defender XDR.

1. In the left navigation menu, select **Show navigation**, and then select **Home**.

1. Still in the left navigation menu, expand **Assets**, and then select **Devices**. This action triggers the workspace deployment.

1. Watch the top of the page for the *Loading* and *Initializing* messages. Shortly after, an image of a coffee mug appears with the message: **Hang on! We're preparing new spaces for your data and connecting them.** Provisioning takes about 5 minutes.

    >**Important:** Leave this page open until provisioning completes. The workspace is required for the remaining tasks in this lab.

    >**Note:** Disregard any pop-up errors that say *Some of your data cannot be retrieved*. If the *Hang on! We're preparing new spaces for your data and connecting them* message doesn't appear, or the **Settings > Microsoft Defender XDR > Account** page opens with the message *Failed to load data storage location. Please try again later*, select **Alert service settings** from the **General** menu.

1. When provisioning finishes, the **Home** page displays a **Get your SIEM and XDR in one place** banner. In **Settings**, the Microsoft Defender XDR General settings for **Account**, **Email notifications**, **Preview features**, **Alert service settings**, **Permissions and roles**, and **Streaming API** are now enabled.

### Task 2: Apply Microsoft Defender for Office 365 preset security policies

In this task, you'll assign the built-in **Standard** and **Strict** preset security policies for Exchange Online Protection (EOP) and Microsoft Defender for Office 365 from the Microsoft Defender portal.

1. In Microsoft Edge, return to the **Microsoft Defender XDR** portal tab and continue using the existing signed-in session.

1. In the navigation menu, under the **Email & Collaboration** area, select **Policies & rules**.

1. On the **Policies & rules** page, select **Threat policies**.

1. On the **Threat policies** page, select **Preset security policies**.

    >**Note:** If you receive the message *"Client Error - Error when getting bip rule"* select **OK** to continue. The error is due to the hydration status of your tenant at Office 365 which is not enabled by default.

    >**Note:** If you receive the message *"Client Error - An error occurred when retrieving preset security policies. Please try again later."* select **OK** to continue. Refresh your browser using **Ctrl+F5**.

1. On the **Learn about preset security policies** *pop-out* page, select **Close**.

1. Under **Standard protection**, select **Manage protection settings**. **Hint:** If you see this option grayed out, refresh your browser using **Ctrl+F5**.

1. In the **Apply Exchange Online Protection** section, select **Specific recipients** and under **Domains** start writing your tenant's domain name, select it, and then select **Next**.

    >**Hint:** Your tenant's domain name is the same name that you have for your admin account, it might be something like *WWLx######.onmicrosoft.com*. Notice that this configuration applies policies for anti-spam, outbound spam filter, anti-malware, anti-phishing.

1. In the **Apply Defender for Office 365 protection** section, apply the same configuration as the previous step and select **Next**. Notice that this configuration applies policies for anti-phishing, Safe Attachments, Safe Links.

1. In the **Impersonation protection** section, select **Next** four times (4x) to continue.

1. In the **Policy mode** section, make sure the **Turn on the policy when finished** radio button is selected, and then select **Next**.

1. In the **Review and confirm your changes** section, read the content and select **Confirm** to apply the changes, and then select **Done** to finish.

    >**Note:** If you receive the message *"The URI '<https://outlook.office365.com/psws/service.svc/AntiPhishPolicy>' is not valid for PUT operation. The URI must point to a single resource for PUT operations."* just select **OK** and then select **Cancel** to return to the main page. You will see that *Standard protection is on* option enabled.

1. Under **Strict protection**, select **Manage protection settings**. **Hint:** *Strict protection* is found under "Email & Collaboration - Policies & rules - Threat policies - Preset security policies".

1. In the **Apply Exchange Online Protection**, select **Specific recipients** and under **Groups** start writing **Leadership**, select it, and then select **Next**. Notice that this configuration applies policies for anti-spam, outbound spam filter, anti-malware, anti-phishing.

1. In the **Apply Defender for Office 365 protection** section, apply the same configuration as the previous step and select **Next**. Notice that this configuration applies policies for anti-phishing, Safe Attachments, Safe Links.

1. In the **Impersonation protection** section, select **Next** four times (4x) to continue.

1. In the **Policy mode** section, make sure the **Turn on the policy when finished** radio button is selected, and then select **Next**.

1. In the **Review and confirm your changes** section, read the content and select **Confirm** to apply the changes, and then select **Done** to finish.

    >**Note:** If you receive the message *"The URI '<https://outlook.office365.com/psws/service.svc/AntiPhishPolicy>' is not valid for PUT operation. The URI must point to a single resource for PUT operations."* just select **OK** and then select **Cancel** to return to the main page. You will see the *Strict protection is on* option enabled.

## Summary

In this lab, you provisioned the Microsoft Defender XDR workspace and applied the built-in **Standard** and **Strict** preset security policies to protect your tenant.

## You have completed the lab
