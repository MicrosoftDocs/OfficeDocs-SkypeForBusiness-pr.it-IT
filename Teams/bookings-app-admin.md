---
title: Visite virtuali con Microsoft Teams e l’app Bookings
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Microsoft Teams e visite virtuali con l’app Bookings
ms.openlocfilehash: e65e0b8c4af7397ebe0b152d2f977b2bf8cbb667
ms.sourcegitcommit: f0e5da6136656261567ffe0fa3f2fedd901209a8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "51891263"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a><span data-ttu-id="a0d88-103">Visite virtuali con Microsoft Teams e l’app Bookings</span><span class="sxs-lookup"><span data-stu-id="a0d88-103">Virtual visits with Microsoft Teams and the Bookings app</span></span>

<span data-ttu-id="a0d88-104">L'app Bookings in Microsoft Teams offre un modo semplice per pianificare appuntamenti di persona e virtuali come visite mediche, consulenze finanziarie, colloqui, assistenza clienti, orario d’ufficio per l'istruzione e molto altro ancora.</span><span class="sxs-lookup"><span data-stu-id="a0d88-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="a0d88-105">Le utilità di pianificazione possono gestire più calendari di reparto e del personale, oltre a comunicazioni con partecipanti interni ed esterni, da un'unica esperienza.</span><span class="sxs-lookup"><span data-stu-id="a0d88-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="a0d88-106">Gli appuntamenti virtuali vengono tenuti tramite riunioni di Microsoft Teams, che offrono funzionalità efficaci di videoconferenza.</span><span class="sxs-lookup"><span data-stu-id="a0d88-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="a0d88-107">Solo le utilità di pianificazione devono avere l'app Bookings installata in Teams.</span><span class="sxs-lookup"><span data-stu-id="a0d88-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="a0d88-108">Il personale che conduce o partecipa a appuntamenti virtuali non ha bisogno dell'app.</span><span class="sxs-lookup"><span data-stu-id="a0d88-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="a0d88-109">Possono semplicemente partecipare agli appuntamenti dal calendario di Outlook o Teams o da un collegamento nel messaggio di conferma della prenotazione.</span><span class="sxs-lookup"><span data-stu-id="a0d88-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="a0d88-110">Prerequisiti per l'uso dell'app Bookings in Teams</span><span class="sxs-lookup"><span data-stu-id="a0d88-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="a0d88-111">La cassetta postale di Exchange deve essere in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a0d88-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="a0d88-112">Le cassette postali di Exchange Server locale non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="a0d88-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="a0d88-113">Microsoft Bookings deve essere attivato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a0d88-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="a0d88-114">Gli utenti devono avere una licenza appropriata.</span><span class="sxs-lookup"><span data-stu-id="a0d88-114">Users must have an appropriate license.</span></span> <span data-ttu-id="a0d88-115">Sono supportati Office 365 A3, A5, E3 e E5, come anche Microsoft 365 Business Premium, Microsoft 365 Business Standard, A3, A5, E3 e E5.</span><span class="sxs-lookup"><span data-stu-id="a0d88-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Premium, Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="a0d88-116">Tutti gli utenti dell'app Bookings e tutto il personale che partecipa alle riunioni devono avere una licenza che supporti la pianificazione delle riunioni di Teams.</span><span class="sxs-lookup"><span data-stu-id="a0d88-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="a0d88-117">I sistemi devono soddisfare tutti i [prerequisiti del software e del browser](hardware-requirements-for-the-teams-app.md).</span><span class="sxs-lookup"><span data-stu-id="a0d88-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="a0d88-118">Disponibilità di Bookings in Teams</span><span class="sxs-lookup"><span data-stu-id="a0d88-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="a0d88-119">L'app Microsoft Bookings per Teams è disponibile sul desktop e sul Web.</span><span class="sxs-lookup"><span data-stu-id="a0d88-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="a0d88-120">L'app si trova in [App all'interno di Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) e in **Gestisci app** all’interno dell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="a0d88-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="a0d88-121">Controllare l'accesso a Bookings all'interno dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="a0d88-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="a0d88-122">Esistono diversi modi per controllare chi ha accesso all'app Bookings e a specifiche funzionalità dell'app.</span><span class="sxs-lookup"><span data-stu-id="a0d88-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="a0d88-123">Per informazioni su come attivare o disattivare Microsoft Bookings nell'interfaccia di amministrazione di Microsoft 365 e su come creare criteri per l'app Bookings per consentire agli utenti selezionati di creare calendari di Bookings, vedere [Accedere a Microsoft Bookings](https://support.microsoft.com/it-IT/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span><span class="sxs-lookup"><span data-stu-id="a0d88-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/it-IT/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="a0d88-124">Vedere anche come [Creare criteri per l'app Teams per aggiungere l'app Bookings per utenti selezionati](teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a0d88-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="a0d88-125">Impostazioni consigliate per i criteri di riunione</span><span class="sxs-lookup"><span data-stu-id="a0d88-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="a0d88-126">Per consentire l'esperienza migliore per Bookings, creare criteri di riunione del personale per ammettere automaticamente **Tutti gli utenti dell'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="a0d88-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization**.</span></span> <span data-ttu-id="a0d88-127">In questo modo il personale potrà partecipare automaticamente all'appuntamento e sarà possibile consentire l'esperienza di sala di attesa per i partecipanti esterni.</span><span class="sxs-lookup"><span data-stu-id="a0d88-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="a0d88-128">Per altre informazioni, è possibile vedere come [ammettere automaticamente le persone alle riunioni](meeting-policies-participants-and-guests.md#automatically-admit-people).</span><span class="sxs-lookup"><span data-stu-id="a0d88-128">You can learn more about [automatically admitting people to meetings](meeting-policies-participants-and-guests.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="a0d88-129">Impostazione facoltativa delle approvazioni del personale</span><span class="sxs-lookup"><span data-stu-id="a0d88-129">Optional staff approvals setting</span></span>

<span data-ttu-id="a0d88-130">Come impostazione di privacy aggiuntiva, è possibile scegliere di richiedere al personale di acconsentire esplicitamente prima che le informazioni sulla disponibilità della pianificazione siano condivise tramite Bookings e prima che possano essere prenotati per un appuntamento.</span><span class="sxs-lookup"><span data-stu-id="a0d88-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="a0d88-131">Per abilitare questa impostazione, aprire **l'interfaccia di amministrazione di Microsoft 365** \> **Impostazioni** \> **Impostazioni**, quindi selezionare **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="a0d88-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings**, then select **Bookings**.</span></span>

<span data-ttu-id="a0d88-132">Quando questa impostazione è attivata, il personale riceverà un messaggio di posta elettronica in cui viene chiesto di approvare l'appartenenza a un calendario delle prenotazioni.</span><span class="sxs-lookup"><span data-stu-id="a0d88-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="a0d88-133">Questa funzionalità verrà distribuita gradualmente in tutto il mondo per i clienti di Microsoft 365 e Office 365.</span><span class="sxs-lookup"><span data-stu-id="a0d88-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="a0d88-134">Se nel proprio ambiente non sono ancora disponibili tutte le opzioni, ricontrollare più avanti.</span><span class="sxs-lookup"><span data-stu-id="a0d88-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="a0d88-135">Modifica del dominio predefinito durante la configurazione delle cassette postali di Bookings</span><span class="sxs-lookup"><span data-stu-id="a0d88-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="a0d88-136">Quando si configura una cassetta postale di Bookings, viene usato il dominio di posta elettronica predefinito dell'organizzazione di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="a0d88-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="a0d88-137">Tuttavia, questo può causare problemi quando si inviano inviti alle riunioni a destinatari esterni; l'invito potrebbe essere contrassegnato come posta indesiderata e spostato nella cartella Posta indesiderata del destinatario, quindi il destinatario potrebbe non vederlo mai.</span><span class="sxs-lookup"><span data-stu-id="a0d88-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="a0d88-138">È consigliabile modificare il dominio predefinito prima di creare la cassetta postale di Bookings.</span><span class="sxs-lookup"><span data-stu-id="a0d88-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="a0d88-139">Per informazioni su come eseguire questa operazione, vedere [Domande frequenti sui domini](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="a0d88-139">For information on how to do this, see the [Domains FAQ](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="a0d88-140">Se è necessario modificare il dominio predefinito dopo aver già creato la cassetta postale di Bookings, è possibile farlo con PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a0d88-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="a0d88-141">Per altre informazioni, vedere la documentazione di PowerShell per il cmdlet [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="a0d88-141">For more information, see the PowerShell documentation for the [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="a0d88-142">Se si usa una configurazione ibrida di Exchange, è consigliabile testare accuratamente il flusso di posta tra Exchange locale ed Exchange Online quando si modifica il dominio predefinito.</span><span class="sxs-lookup"><span data-stu-id="a0d88-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="a0d88-143">Invio di feedback</span><span class="sxs-lookup"><span data-stu-id="a0d88-143">Sending feedback</span></span>

<span data-ttu-id="a0d88-144">Invitiamo gli utenti a inviarci un feedback sugli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0d88-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="a0d88-145">Esperienza utente o facilità d'uso</span><span class="sxs-lookup"><span data-stu-id="a0d88-145">User experience or ease of use</span></span>
  - <span data-ttu-id="a0d88-146">Lacune delle funzionalità o funzionalità mancanti</span><span class="sxs-lookup"><span data-stu-id="a0d88-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="a0d88-147">Bug o problemi</span><span class="sxs-lookup"><span data-stu-id="a0d88-147">Bugs or issues</span></span>
  
<span data-ttu-id="a0d88-148">Per inviare un feedback, fare clic sul pulsante **Guida** nella parte inferiore della barra di spostamento sinistra di Teams, quindi fare clic su **Segnala un problema** per **TUTTI** i problemi.</span><span class="sxs-lookup"><span data-stu-id="a0d88-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="a0d88-149">Indicare all'inizio del report di feedback che si sta inviando un feedback su "Bookings" in modo da poter identificare facilmente i problemi relativi a Bookings.</span><span class="sxs-lookup"><span data-stu-id="a0d88-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a0d88-150">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a0d88-150">Related topics</span></span>

<span data-ttu-id="a0d88-151">
  [Documentazione di Bookings per gli utenti finali](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)</span><span class="sxs-lookup"><span data-stu-id="a0d88-151">[Bookings documentation for end users](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)</span></span>