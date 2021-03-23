---
title: Consentire ai dispositivi di Teams Rooms di partecipare a riunioni di terze parti
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Questo articolo illustra come configurare l'organizzazione e i dispositivi di Teams Rooms per supportare la partecipazione a riunioni di terze parti a Cisco WebEx e Zoom.
ms.openlocfilehash: ac4c57dc5cc743fb7b141ecaaaf3531b35912e77
ms.sourcegitcommit: 2eaf80bca6dfad367283e57662d81a809c9437e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2021
ms.locfileid: "50997434"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="d1286-103">Abilitare i dispositivi di Teams Room per partecipare a riunioni di terze parti</span><span class="sxs-lookup"><span data-stu-id="d1286-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="d1286-104">I dispositivi Microsoft Teams Rooms supportano un'esperienza con un solo tocco per partecipare a riunioni online di terze parti, detta anche partecipazione guest diretta.</span><span class="sxs-lookup"><span data-stu-id="d1286-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings, also referred to as Direct guest join.</span></span> <span data-ttu-id="d1286-105">Se abilitata, è possibile usare un dispositivo Teams Rooms per partecipare a riunioni ospitate su Cisco WebEx e Zoom con la facilità con cui è possibile partecipare alle riunioni ospitate in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d1286-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="d1286-106">Prima di poter partecipare a riunioni di terze parti da un dispositivo Teams Rooms, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1286-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="d1286-107">Configurare la cassetta postale della chat room di Exchange Online del dispositivo Teams Rooms per elaborare gli inviti per riunioni di terze parti.</span><span class="sxs-lookup"><span data-stu-id="d1286-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings.</span></span>
2. <span data-ttu-id="d1286-108">Assicurarsi che l'organizzazione non abbia criteri che impediscono la connessione a servizi di riunione di terze parti.</span><span class="sxs-lookup"><span data-stu-id="d1286-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services.</span></span>
3. <span data-ttu-id="d1286-109">Configurare i dispositivi di Teams Rooms per consentire riunioni di terze parti.</span><span class="sxs-lookup"><span data-stu-id="d1286-109">Configure your Teams Rooms devices to allow third-party meetings.</span></span>

<span data-ttu-id="d1286-110">Le sezioni seguenti illustrano come eseguire ognuno di questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="d1286-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="d1286-111">Passaggio 1: Consentire l'elaborazione degli inviti al calendario per le riunioni di terze parti</span><span class="sxs-lookup"><span data-stu-id="d1286-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="d1286-112">La prima cosa da fare per abilitare un'esperienza di partecipazione con un solo tocco da un dispositivo Team Rooms è impostare le regole di elaborazione del calendario per la cassetta postale sala di Exchange Online del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d1286-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="d1286-113">La cassetta postale della sala deve consentire riunioni esterne e mantenere il corpo e l'oggetto del messaggio in modo che possa vedere l'URL necessario per partecipare alla riunione di terze parti.</span><span class="sxs-lookup"><span data-stu-id="d1286-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="d1286-114">Per impostare queste opzioni della cassetta postale sala usando il cmdlet [Set-CalendarProcessing,](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1286-114">To set these room mailbox options using the [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="d1286-115">Connettersi a PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d1286-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="d1286-116">Per altre informazioni, vedere Connettersi a [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) con l'autenticazione di base o Connettersi a [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)usando l'autenticazione a più fattori, a seconda del metodo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="d1286-116">For more information, see [Connect to Exchange Online PowerShell with Basic authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="d1286-117">Ottenere il nome dell'entità utente (UPN) della cassetta postale della chat room se non lo si conosce eseguendo il comando seguente:Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span><span class="sxs-lookup"><span data-stu-id="d1286-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. <span data-ttu-id="d1286-118">Trovare il nome della cassetta postale della chat room associata al dispositivo Teams Rooms e prendere nota del relativo UPN.</span><span class="sxs-lookup"><span data-stu-id="d1286-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN.</span></span>

4. <span data-ttu-id="d1286-119">Dopo aver trovato l'UPN della cassetta postale sala, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="d1286-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="d1286-120">Sostituire `<UserPrincipalName>` con l'UPN della cassetta postale sala:</span><span class="sxs-lookup"><span data-stu-id="d1286-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="d1286-121">Altre informazioni su [PowerShell di Exchange Online.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="d1286-121">Learn more about [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="d1286-122">Passaggio 2: Configurare Office 365 Threat Protection e la riscrittura dei collegamenti</span><span class="sxs-lookup"><span data-stu-id="d1286-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="d1286-123">Per abilitare l'esperienza di partecipazione con un solo tocco, le informazioni sul collegamento di partecipazione alla riunione della riunione di terze parti devono essere presenti e leggibili nell'invito alla riunione.</span><span class="sxs-lookup"><span data-stu-id="d1286-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="d1286-124">Se l'organizzazione usa la caratteristica Collegamenti sicuri di [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) o se si usa una soluzione di terze parti che analizza tutti gli URL in arrivo e in uscita alla ricerca di minacce, può modificare gli URL di partecipazione alla riunione e rendere la riunione irriconoscibile dal dispositivo Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="d1286-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="d1286-125">Per assicurarsi che non accada, è necessario aggiungere gli URL del servizio riunioni di terze parti all'elenco collegamenti sicuri ATP "non riscrivere" o all'elenco di eccezioni di riscrittura URL di terze parti.</span><span class="sxs-lookup"><span data-stu-id="d1286-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="d1286-126">Per aggiungere URL del servizio riunioni di terze parti all'elenco Collegamenti sicuri ATP "non riscrivere", seguire la procedura descritta in Configurare un elenco personalizzato di URL non riscrivere usando Collegamenti sicuri [ATP.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="d1286-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="d1286-127">Se si usa una soluzione di terze parti, vedere le istruzioni per tale soluzione per aggiungere URL al relativo elenco di eccezioni di riscrittura URL.</span><span class="sxs-lookup"><span data-stu-id="d1286-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="d1286-128">Ecco alcune voci di esempio che potrebbe essere necessario aggiungere all'elenco di eccezioni "non riscrivere" collegamenti sicuri ATP o url di terze parti:</span><span class="sxs-lookup"><span data-stu-id="d1286-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="d1286-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="d1286-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="d1286-130">**Zoom** `*.zoom.us*` , `*.zoom.com*` , `*.zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="d1286-130">**Zoom** `*.zoom.us*`, `*.zoom.com*`, `*.zoomgov.com*`</span></span>

<span data-ttu-id="d1286-131">Per un elenco completo di URL da aggiungere all'elenco di eccezioni "non riscrivere" collegamenti sicuri ATP o all'elenco di eccezioni di riscrittura url di terze parti, contattare il provider di servizi di riunione di terze parti da cui si vogliono accettare gli inviti alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="d1286-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="d1286-132">Aggiungere solo URL attendibili all'elenco di eccezioni di riscrivere i collegamenti sicuri ATP o a url di terze parti.</span><span class="sxs-lookup"><span data-stu-id="d1286-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="d1286-133">Passaggio 3: Abilitare le riunioni di terze parti nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="d1286-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="d1286-134">L'ultimo passaggio da eseguire è consentire a ogni dispositivo di Teams Rooms di partecipare a riunioni di terze parti.</span><span class="sxs-lookup"><span data-stu-id="d1286-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="d1286-135">Per partecipare alle riunioni di terze parti è necessario un nome utente e un indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d1286-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="d1286-136">Se il nome utente e l'indirizzo di posta elettronica da usare sono diversi dalla cassetta postale della sala del dispositivo, è necessario aggiungerli al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d1286-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="d1286-137">È possibile eseguire questa operazione nelle impostazioni del dispositivo o nel file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="d1286-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="d1286-138">Usare le impostazioni del dispositivo</span><span class="sxs-lookup"><span data-stu-id="d1286-138">Use device settings</span></span>

<span data-ttu-id="d1286-139">Per configurare il dispositivo Teams Rooms usando il touchscreen, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1286-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="d1286-140">Nel dispositivo Microsoft Teams Rooms selezionare **Altro ...**.</span><span class="sxs-lookup"><span data-stu-id="d1286-140">On the Microsoft Teams Rooms device, select **More ...**.</span></span>
2. <span data-ttu-id="d1286-141">Selezionare **Impostazioni** e quindi immettere il nome utente e la password dell'amministratore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d1286-141">Select **Settings**, and then enter the device administrator username and password.</span></span>
3. <span data-ttu-id="d1286-142">Passare alla scheda **Riunioni** e selezionare **Cisco WebEx**, **Zoom** o entrambi.</span><span class="sxs-lookup"><span data-stu-id="d1286-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**, or both.</span></span>
4. <span data-ttu-id="d1286-143">Se si vuole partecipare alle riunioni con il nome utente e l'indirizzo di posta elettronica associati alla cassetta postale della sala, selezionare **Partecipa con le informazioni sulla sala.**</span><span class="sxs-lookup"><span data-stu-id="d1286-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**.</span></span>
5. <span data-ttu-id="d1286-144">Se si vuole partecipare alle riunioni con un  nome utente e un indirizzo di posta elettronica alternativi, selezionare Partecipa con informazioni personalizzate e immettere il nome utente e l'indirizzo di posta elettronica da usare.</span><span class="sxs-lookup"><span data-stu-id="d1286-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use.</span></span>
6. <span data-ttu-id="d1286-145">Selezionare **Salva e esci.**</span><span class="sxs-lookup"><span data-stu-id="d1286-145">Select **Save and exit**.</span></span> <span data-ttu-id="d1286-146">Il dispositivo verrà riavviato.</span><span class="sxs-lookup"><span data-stu-id="d1286-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="d1286-147">Usare il file SkypeSettings.xml file di configurazione</span><span class="sxs-lookup"><span data-stu-id="d1286-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="d1286-148">Le impostazioni seguenti possono essere aggiunte al `SkypeSettings.xml` file che si trova in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` .</span><span class="sxs-lookup"><span data-stu-id="d1286-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="d1286-149">Per altre informazioni sul file, vedere Gestire le impostazioni della console di `SkypeSettings.xml` Microsoft Teams Rooms in remoto con un file di configurazione [XML.](xml-config-file.md)</span><span class="sxs-lookup"><span data-stu-id="d1286-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="d1286-150">Per abilitare le riunioni Cisco WebEx, impostare `WebExMeetingsEnabled` l'elemento XML su **True**, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d1286-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="d1286-151">Per abilitare le riunioni zoom, impostare `ZoomMeetingsEnabled` l'elemento XML su **True**, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d1286-151">To enable Zoom meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="d1286-152">Facoltativamente, è possibile specificare un nome utente e un indirizzo di posta elettronica personalizzati per partecipare a riunioni di terze parti usando gli elementi XML seguenti.</span><span class="sxs-lookup"><span data-stu-id="d1286-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="d1286-153">Se i valori specificati non sono validi, il dispositivo Teams Rooms userà per impostazione predefinita il nome utente e l'indirizzo di posta elettronica della cassetta postale della sala.</span><span class="sxs-lookup"><span data-stu-id="d1286-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="d1286-154">Per partecipare a una riunione Cisco WebEx da un dispositivo Teams Rooms, la riunione Cisco deve essere ospitata con l'applicazione Web Cisco WebEx versione WBS 40.7 o successiva.</span><span class="sxs-lookup"><span data-stu-id="d1286-154">To join Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted using Cisco WebEx web application version WBS 40.7 or later.</span></span>
