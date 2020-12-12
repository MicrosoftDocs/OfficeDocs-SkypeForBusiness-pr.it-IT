---
title: Abilitare i dispositivi di teams Rooms per partecipare a riunioni di terze parti
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
description: Questo articolo illustra come configurare i dispositivi dell'organizzazione e dei team Rooms per supportare la partecipazione a una riunione di terze parti a Cisco WebEx e zoom.
ms.openlocfilehash: 8079b6fc231bf30a654e2513af55a806433eb83f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662361"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="856df-103">Consentire ai dispositivi della sala team di partecipare a riunioni di terze parti</span><span class="sxs-lookup"><span data-stu-id="856df-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="856df-104">I dispositivi Microsoft teams Rooms supportano un'esperienza One-Touch per partecipare a riunioni online di terze parti.</span><span class="sxs-lookup"><span data-stu-id="856df-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings.</span></span> <span data-ttu-id="856df-105">Quando è abilitata, è possibile usare un dispositivo teams Rooms per partecipare a riunioni ospitate in Cisco WebEx e zoom<sup>1</sup> con la stessa facilità con cui è possibile partecipare a riunioni ospitate in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="856df-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom<sup>1</sup> just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="856df-106">Prima di poter partecipare a riunioni di terze parti da un dispositivo di teams rooms, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="856df-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="856df-107">Configurare la cassetta postale della sala di Exchange Online del dispositivo teams Rooms per elaborare gli inviti per riunioni di terze parti</span><span class="sxs-lookup"><span data-stu-id="856df-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings</span></span>
2. <span data-ttu-id="856df-108">Verificare che l'organizzazione non disponga di criteri che impediscano la connessione a servizi di riunione di terze parti</span><span class="sxs-lookup"><span data-stu-id="856df-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services</span></span>
3. <span data-ttu-id="856df-109">Configurare i dispositivi di teams Rooms per consentire riunioni di terze parti</span><span class="sxs-lookup"><span data-stu-id="856df-109">Configure your Teams Rooms devices to allow third-party meetings</span></span>

<span data-ttu-id="856df-110">Le sezioni seguenti illustrano come eseguire ognuno di questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="856df-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="856df-111">Passaggio 1: consentire l'elaborazione dell'invito del calendario per le riunioni di terze parti</span><span class="sxs-lookup"><span data-stu-id="856df-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="856df-112">La prima cosa da fare per abilitare un'esperienza di join One-Touch da un dispositivo di Team Rooms è impostare le regole di elaborazione del calendario per la cassetta postale della sala di Exchange Online del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="856df-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="856df-113">La cassetta postale della sala deve consentire riunioni esterne e tenere il corpo del messaggio e l'oggetto in modo che possa vedere l'URL necessario per partecipare alla riunione di terze parti.</span><span class="sxs-lookup"><span data-stu-id="856df-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="856df-114">Per impostare le opzioni delle cassette postali della sala usando il cmdlet [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) , eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="856df-114">To set these room mailbox options using the [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="856df-115">Connettersi a PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="856df-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="856df-116">Per altre informazioni, vedere [connettersi a PowerShell di Exchange Online con l'autenticazione di base](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) o [connettersi a PowerShell di Exchange Online con l'autenticazione](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)a più fattori, a seconda del metodo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="856df-116">For more information, see [Connect to Exchange Online Powershell with Basic authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="856df-117">Ottenere il nome dell'entità utente (UPN) della cassetta postale della sala se non lo si conosce eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="856df-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
3. <span data-ttu-id="856df-118">Trovare il nome della cassetta postale della sala associata al dispositivo teams Rooms e prendere nota del relativo UPN</span><span class="sxs-lookup"><span data-stu-id="856df-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN</span></span>

4. <span data-ttu-id="856df-119">Dopo aver trovato l'UPN della cassetta postale della sala, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="856df-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="856df-120">Sostituire `<UserPrincipalName>` con l'UPN della cassetta postale della sala:</span><span class="sxs-lookup"><span data-stu-id="856df-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="856df-121">Altre informazioni su [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="856df-121">Learn more about [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="856df-122">Passaggio 2: configurare la protezione delle minacce di Office 365 e la riscrittura dei collegamenti</span><span class="sxs-lookup"><span data-stu-id="856df-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="856df-123">Per abilitare l'esperienza di join One-Touch, le informazioni sul collegamento alla riunione di partecipazione dalla riunione di terze parti devono essere presenti e leggibili nell'invito alla riunione.</span><span class="sxs-lookup"><span data-stu-id="856df-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="856df-124">Se l'organizzazione usa la caratteristica [collegamenti attendibili di Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) o se si usa una soluzione di terze parti che analizza tutti gli URL in entrata e in uscita per le minacce, può modificare gli URL di join della riunione e rendere la riunione irriconoscibile dal dispositivo teams rooms.</span><span class="sxs-lookup"><span data-stu-id="856df-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="856df-125">Per verificare che non si verifichi questo problema, è necessario aggiungere gli URL del servizio di riunione di terze parti all'elenco collegamenti sicuri ATP "non riscrivere" o all'elenco di eccezioni di riscrittura URL di terze parti.</span><span class="sxs-lookup"><span data-stu-id="856df-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="856df-126">Per aggiungere URL del servizio di riunione di terze parti all'elenco collegamenti sicuri ATP "non riscrivere", seguire i passaggi descritti in [configurare un elenco di URL non riscrivibile personalizzato usando collegamenti sicuri ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="856df-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="856df-127">Se si usa una soluzione di terze parti, vedere le istruzioni per la soluzione per aggiungere URL all'elenco di eccezioni di riscrittura URL.</span><span class="sxs-lookup"><span data-stu-id="856df-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="856df-128">Ecco alcuni esempi di voci che potrebbe essere necessario aggiungere ai collegamenti sicuri ATP "non riscrivere" o elenco di eccezioni di riscrittura URL di terze parti:</span><span class="sxs-lookup"><span data-stu-id="856df-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="856df-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="856df-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="856df-130">**Zoom** `*.zoom.us*` , `*.zoom.com*``*.zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="856df-130">**Zoom** `*.zoom.us*`, `*.zoom.com*`, `*.zoomgov.com*`</span></span>

<span data-ttu-id="856df-131">Per un elenco completo degli URL da aggiungere ai collegamenti sicuri ATP "non riscrivere", elenco di eccezioni di riscrittura URL di terze parti, contattare il provider di servizi di terze parti a cui si vogliono accettare gli inviti alla riunione.</span><span class="sxs-lookup"><span data-stu-id="856df-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="856df-132">Aggiungere solo gli URL attendibili per i collegamenti sicuri ATP "non riscrivere" o elenco di eccezioni di riscrittura URL di terze parti.</span><span class="sxs-lookup"><span data-stu-id="856df-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="856df-133">Passaggio 3: abilitare riunioni di terze parti sul dispositivo</span><span class="sxs-lookup"><span data-stu-id="856df-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="856df-134">L'ultimo passaggio da eseguire è consentire a ogni dispositivo sale team di partecipare a riunioni di terze parti.</span><span class="sxs-lookup"><span data-stu-id="856df-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="856df-135">Le riunioni di terze parti richiedono un nome utente e un indirizzo di posta elettronica per partecipare.</span><span class="sxs-lookup"><span data-stu-id="856df-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="856df-136">Se il nome utente e l'indirizzo di posta elettronica che è necessario usare sono diversi dalla cassetta postale della sala del dispositivo, è necessario aggiungerli al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="856df-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="856df-137">Questa operazione può essere eseguita nelle impostazioni del dispositivo o nel file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="856df-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="856df-138">Usare le impostazioni del dispositivo</span><span class="sxs-lookup"><span data-stu-id="856df-138">Use device settings</span></span>

<span data-ttu-id="856df-139">Per configurare il dispositivo teams Rooms usando il touchscreen, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="856df-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="856df-140">Nel dispositivo Microsoft teams Rooms selezionare **altro...**</span><span class="sxs-lookup"><span data-stu-id="856df-140">On the Microsoft Teams Rooms device, select **More ...**</span></span>
2. <span data-ttu-id="856df-141">Selezionare **Impostazioni** e quindi immettere il nome utente e la password dell'amministratore del dispositivo</span><span class="sxs-lookup"><span data-stu-id="856df-141">Select **Settings**, and then enter the device administrator username and password</span></span>
3. <span data-ttu-id="856df-142">Passare alla scheda **riunioni** e selezionare **Cisco WebEx**, **Zoom**<sup>1</sup>o entrambi</span><span class="sxs-lookup"><span data-stu-id="856df-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**<sup>1</sup>, or both</span></span>
4. <span data-ttu-id="856df-143">Per partecipare alle riunioni con il nome utente e l'indirizzo di posta elettronica associato alla cassetta postale della sala, selezionare **partecipa con info sala**</span><span class="sxs-lookup"><span data-stu-id="856df-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**</span></span>
5. <span data-ttu-id="856df-144">Per partecipare alle riunioni con un nome utente e un indirizzo di posta elettronica alternativi, selezionare **partecipa con info personalizzate** e immettere il nome utente e l'indirizzo di posta elettronica che si vuole usare</span><span class="sxs-lookup"><span data-stu-id="856df-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use</span></span>
6. <span data-ttu-id="856df-145">Selezionare **Salva ed esci**.</span><span class="sxs-lookup"><span data-stu-id="856df-145">Select **Save and exit**.</span></span> <span data-ttu-id="856df-146">Il dispositivo verrà riavviato.</span><span class="sxs-lookup"><span data-stu-id="856df-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="856df-147">Usare il file di configurazione SkypeSettings.xml</span><span class="sxs-lookup"><span data-stu-id="856df-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="856df-148">Le impostazioni seguenti possono essere aggiunte al `SkypeSettings.xml` file che si trova in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` .</span><span class="sxs-lookup"><span data-stu-id="856df-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="856df-149">Per altre informazioni sul `SkypeSettings.xml` file, vedere [gestire le impostazioni della console Microsoft teams rooms in remoto con un file di configurazione XML](xml-config-file.md).</span><span class="sxs-lookup"><span data-stu-id="856df-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="856df-150">Per abilitare le riunioni Cisco WebEx, imposta l' `WebExMeetingsEnabled` elemento XML su **true**, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="856df-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="856df-151">Per abilitare le riunioni zoom <sup>1</sup> , imposta l' `ZoomMeetingsEnabled` elemento XML su **true**, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="856df-151">To enable Zoom <sup>1</sup> meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="856df-152">Puoi facoltativamente specificare un nome utente e un indirizzo di posta elettronica personalizzati per partecipare a riunioni di terze parti usando gli elementi XML seguenti.</span><span class="sxs-lookup"><span data-stu-id="856df-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="856df-153">Se i valori forniti non sono validi, il dispositivo teams Rooms utilizzerà automaticamente il nome utente e l'indirizzo di posta elettronica della cassetta postale della sala.</span><span class="sxs-lookup"><span data-stu-id="856df-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="856df-154">Per partecipare a una riunione Cisco WebEx da un dispositivo di teams rooms, la riunione Cisco deve essere ospitata usando la versione WBS 40,7 o successiva di Cisco WebEx Web Application.</span><span class="sxs-lookup"><span data-stu-id="856df-154">To join Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted using Cisco WebEx web application version WBS 40.7 or later.</span></span>

<span data-ttu-id="856df-155"><sup>1</sup> la partecipazione alle riunioni zoom è attualmente disponibile solo per selezionare i clienti di Microsoft teams Rooms tramite il programma di accesso alla tecnologia (TAP).</span><span class="sxs-lookup"><span data-stu-id="856df-155"><sup>1</sup> Zoom meetings join is currently only available to select Microsoft Teams Rooms customers through Technology Access Program (TAP).</span></span>
