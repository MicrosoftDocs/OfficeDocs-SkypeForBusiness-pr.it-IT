---
title: App bookings e visite virtuali in Microsoft Teams
author: mattpennathe3rd
ms.author: v-mapenn
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
ms.reviewer: ''
description: Microsoft teams e visite virtuali con l'app bookings
ms.openlocfilehash: b00a42ab7d0b590d706b8e3218f24d13b945b731
ms.sourcegitcommit: ebdad71a8d393466e33a2fdc8606d882a6007588
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2020
ms.locfileid: "44280288"
---
# <a name="bookings-app-and-virtual-visits-in-microsoft-teams"></a><span data-ttu-id="7a957-103">App bookings e visite virtuali in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a957-103">Bookings app and virtual visits in Microsoft Teams</span></span>

<span data-ttu-id="7a957-104">L'app bookings in Microsoft teams offre un modo semplice per pianificare appuntamenti personali e virtuali, ad esempio visite sanitarie, consulenze finanziarie, interviste, assistenza clienti, ore di ufficio per l'istruzione e molto altro.</span><span class="sxs-lookup"><span data-stu-id="7a957-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="7a957-105">Le utilità di pianificazione possono gestire più calendari di reparto e personale, nonché le comunicazioni con i partecipanti interni ed esterni, da una singola esperienza.</span><span class="sxs-lookup"><span data-stu-id="7a957-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="7a957-106">Gli appuntamenti virtuali si svolgono tramite riunioni di Microsoft teams, che offrono funzionalità di videoconferenza affidabili.</span><span class="sxs-lookup"><span data-stu-id="7a957-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="7a957-107">Solo gli utilità di pianificazione devono avere l'app bookings installata in teams.</span><span class="sxs-lookup"><span data-stu-id="7a957-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="7a957-108">I membri del personale che effettuano o partecipano a appuntamenti virtuali non richiedono l'app.</span><span class="sxs-lookup"><span data-stu-id="7a957-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="7a957-109">Possono semplicemente partecipare agli appuntamenti dal calendario di Outlook o di teams o da un collegamento nel messaggio di conferma della prenotazione.</span><span class="sxs-lookup"><span data-stu-id="7a957-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="7a957-110">Prerequisiti per l'uso dell'app bookings in teams</span><span class="sxs-lookup"><span data-stu-id="7a957-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="7a957-111">La cassetta postale di Exchange deve essere in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7a957-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="7a957-112">Le cassette postali di Exchange Server locali non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="7a957-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="7a957-113">Le prenotazioni Microsoft devono essere attivate per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7a957-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="7a957-114">Gli utenti devono avere una licenza appropriata.</span><span class="sxs-lookup"><span data-stu-id="7a957-114">Users must have an appropriate license.</span></span> <span data-ttu-id="7a957-115">Sono supportati Office 365 a3, a5, E3 e E5, oltre a Microsoft 365 business standard, a3, a5, E3 e E5.</span><span class="sxs-lookup"><span data-stu-id="7a957-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="7a957-116">Tutti gli utenti dell'app bookings e tutti i membri del personale che partecipano alle riunioni devono avere una licenza che supporti la pianificazione della riunione di teams.</span><span class="sxs-lookup"><span data-stu-id="7a957-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="7a957-117">I sistemi devono soddisfare tutti i [prerequisiti del software e del browser](hardware-requirements-for-the-teams-app.md).</span><span class="sxs-lookup"><span data-stu-id="7a957-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="7a957-118">Disponibilità delle prenotazioni in teams</span><span class="sxs-lookup"><span data-stu-id="7a957-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="7a957-119">L'app Microsoft bookings per Teams è disponibile sul desktop e sul Web.</span><span class="sxs-lookup"><span data-stu-id="7a957-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="7a957-120">Può essere trovato in [app in Microsoft teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) e in **Manage Apps** in teams Admin Center.</span><span class="sxs-lookup"><span data-stu-id="7a957-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="7a957-121">Controllare l'accesso alle prenotazioni all'interno dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="7a957-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="7a957-122">Esistono diversi modi per controllare chi ha accesso all'app bookings e a specifiche caratteristiche dell'app.</span><span class="sxs-lookup"><span data-stu-id="7a957-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="7a957-123">Per informazioni su come attivare o disattivare le prenotazioni Microsoft nell'interfaccia di amministrazione di Microsoft 365, nonché su come creare un criterio per l'app bookings per consentire agli utenti selezionati di creare calendari delle prenotazioni, vedere [accedere alle prenotazioni Microsoft](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span><span class="sxs-lookup"><span data-stu-id="7a957-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="7a957-124">Puoi anche scoprire come [creare criteri per l'app teams per aggiungere l'app bookings per gli utenti selezionati](teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7a957-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="7a957-125">Impostazioni consigliate per i criteri riunione</span><span class="sxs-lookup"><span data-stu-id="7a957-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="7a957-126">Per consentire l'esperienza ottimale per le prenotazioni, creare un criterio per la riunione del personale per ammettere automaticamente **tutti gli utenti dell'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="7a957-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization**.</span></span> <span data-ttu-id="7a957-127">In questo modo, il personale potrà partecipare automaticamente all'appuntamento e abilitare l'esperienza di lobby per i partecipanti esterni.</span><span class="sxs-lookup"><span data-stu-id="7a957-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="7a957-128">Per altre informazioni, vedere l' [ammissione automatica delle persone alle riunioni](meeting-policies-in-teams.md#automatically-admit-people).</span><span class="sxs-lookup"><span data-stu-id="7a957-128">You can learn more about [automatically admitting people to meetings](meeting-policies-in-teams.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="7a957-129">Impostazione facoltativa degli approvazioni del personale</span><span class="sxs-lookup"><span data-stu-id="7a957-129">Optional staff approvals setting</span></span>

<span data-ttu-id="7a957-130">Come ulteriore impostazione per la privacy, puoi scegliere di richiedere al personale l'opt-in prima che le informazioni sulla disponibilità di programmazione vengano condivise tramite le prenotazioni e prima che possano essere prenotate per un appuntamento.</span><span class="sxs-lookup"><span data-stu-id="7a957-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="7a957-131">Per abilitare questa impostazione, accedere alle impostazioni dell'interfaccia di **amministrazione di Microsoft 365** \> **Settings** \> **Settings**e quindi selezionare **prenotazioni**.</span><span class="sxs-lookup"><span data-stu-id="7a957-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings**, then select **Bookings**.</span></span>

<span data-ttu-id="7a957-132">Con questa impostazione attivata, il personale riceverà un messaggio di posta elettronica in cui verrà richiesto di approvare l'appartenenza a un calendario di prenotazione.</span><span class="sxs-lookup"><span data-stu-id="7a957-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="7a957-133">Questa caratteristica viene gradualmente distribuita in tutto il mondo a Microsoft 365 e ai clienti di Office 365.</span><span class="sxs-lookup"><span data-stu-id="7a957-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="7a957-134">Se tutte le opzioni non sono ancora disponibili nell'ambiente, vedere presto.</span><span class="sxs-lookup"><span data-stu-id="7a957-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="7a957-135">Cambiare il dominio predefinito durante la configurazione delle cassette postali di prenotazione</span><span class="sxs-lookup"><span data-stu-id="7a957-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="7a957-136">Quando si configura una cassetta postale di prenotazione, viene usato il dominio di posta elettronica predefinito dell'organizzazione Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="7a957-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="7a957-137">Tuttavia, questo problema può causare problemi durante l'invio di inviti alle riunioni a destinatari esterni; l'invito potrebbe essere contrassegnato come posta indesiderata e spostato nella cartella posta indesiderata del destinatario, in modo che il destinatario potrebbe non vedere mai l'invito.</span><span class="sxs-lookup"><span data-stu-id="7a957-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="7a957-138">È consigliabile modificare il dominio predefinito prima di creare la cassetta postale di prenotazione.</span><span class="sxs-lookup"><span data-stu-id="7a957-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="7a957-139">Per informazioni su come eseguire questa operazione, vedere le [domande frequenti sui domini](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="7a957-139">For information on how to do this, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="7a957-140">Se è necessario modificare il dominio predefinito dopo che la cassetta postale di prenotazione è già stata creata, è possibile farlo con PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7a957-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="7a957-141">Per altre informazioni, vedere la documentazione di PowerShell relativa al cmdlet [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) .</span><span class="sxs-lookup"><span data-stu-id="7a957-141">For more information, see the PowerShell documentation for the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="7a957-142">Se si usa una configurazione ibrida di Exchange, è consigliabile testare completamente il flusso di posta tra Exchange locale ed Exchange Online quando si cambia il dominio predefinito.</span><span class="sxs-lookup"><span data-stu-id="7a957-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="7a957-143">Invio di commenti e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="7a957-143">Sending feedback</span></span>

<span data-ttu-id="7a957-144">Accogliamo favorevolmente il feedback su:</span><span class="sxs-lookup"><span data-stu-id="7a957-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="7a957-145">Esperienza utente o facilità d'uso</span><span class="sxs-lookup"><span data-stu-id="7a957-145">User experience or ease of use</span></span>
  - <span data-ttu-id="7a957-146">Funzionalità gap o funzionalità mancanti</span><span class="sxs-lookup"><span data-stu-id="7a957-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="7a957-147">Bug o problemi</span><span class="sxs-lookup"><span data-stu-id="7a957-147">Bugs or issues</span></span>
  
<span data-ttu-id="7a957-148">Per inviare commenti e suggerimenti, fare clic sul pulsante della **Guida** nella parte inferiore della barra di spostamento sinistra teams, quindi fare clic su **segnala un problema** per **tutti i** problemi.</span><span class="sxs-lookup"><span data-stu-id="7a957-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="7a957-149">Tieni presente che all'inizio del tuo report di feedback stai inviando feedback su "prenotazioni" in modo da identificare facilmente i problemi di prenotazione.</span><span class="sxs-lookup"><span data-stu-id="7a957-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7a957-150">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7a957-150">Related topics</span></span>

[<span data-ttu-id="7a957-151">Documentazione delle prenotazioni per gli utenti finali</span><span class="sxs-lookup"><span data-stu-id="7a957-151">Bookings documentation for end users</span></span>](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
