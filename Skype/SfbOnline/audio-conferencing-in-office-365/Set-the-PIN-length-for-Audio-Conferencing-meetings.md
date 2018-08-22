---
title: Impostare la lunghezza del PIN per le riunioni di audioconferenza in Skype Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Ulteriori parametri per la lunghezza e i requisiti di un PIN e informazioni su come impostare il periodo per le riunioni in Skype per le aziende.
ms.openlocfilehash: 54ee8e70972a7033a9a759f8df37647ba5a2b700
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490566"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="91191-103">Impostare la lunghezza del PIN per le riunioni di audioconferenza in Skype Business online</span><span class="sxs-lookup"><span data-stu-id="91191-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>


> [!NOTE]
> <span data-ttu-id="91191-104">Per informazioni su come impostare la lunghezza del PIN nel Teams Microsoft, vedere [impostare la lunghezza del PIN per le riunioni di conferenze Audio nel team di Microsoft](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="91191-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="91191-105">Quando procede all'impostazione di audioconferenza per Skype per le aziende, si otterrà un ponte per conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="91191-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="91191-106">Un ponte per conferenze può contenere uno o più numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="91191-106">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="91191-107">Si imposta il numero di telefono verrà inclusa in inviti riunione per Skype per applicazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="91191-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="91191-108">Ponte per conferenze audio risponde a una chiamata a coloro che si collegano a una riunione utilizzando un telefono.</span><span class="sxs-lookup"><span data-stu-id="91191-108">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="91191-109">Vengono fornite risposte al chiamante di istruzioni vocali da un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre le notifiche e chiedere ai chiamanti di registrare il proprio nome.</span><span class="sxs-lookup"><span data-stu-id="91191-109">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="91191-110">**Impostazioni bridge Microsoft** consentono di modificare le impostazioni per le notifiche di riunione e la riunione partecipare esperienza e impostare la lunghezza del PIN che vengono utilizzati per gli organizzatori delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="91191-110">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="91191-111">Gli organizzatori delle riunioni utilizzano PIN per avviare riunioni se è Impossibile partecipare alla riunione utilizzando il Skype per applicazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="91191-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="91191-112">Impostazione della lunghezza PIN</span><span class="sxs-lookup"><span data-stu-id="91191-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="91191-113">Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="91191-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="91191-114">In **sicurezza** > **lunghezza del PIN**, selezionare il numero di cifre che si desidera utilizzare per il PIN e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="91191-114">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="91191-115">Un PIN è diverso da un ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="91191-115">A PIN is different from a conference ID.</span></span> <span data-ttu-id="91191-116">ID conferenza vengono utilizzati per i chiamanti quando partecipano a riunione.</span><span class="sxs-lookup"><span data-stu-id="91191-116">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="91191-117">Vengono utilizzati per identificare la riunione.</span><span class="sxs-lookup"><span data-stu-id="91191-117">They are used to identify the meeting.</span></span> <span data-ttu-id="91191-118">Il PIN viene utilizzato per autenticare un chiamante organizzatore della riunione.</span><span class="sxs-lookup"><span data-stu-id="91191-118">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="91191-119">Fonti di informazioni sulle impostazioni del PIN</span><span class="sxs-lookup"><span data-stu-id="91191-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="91191-120">PIN può essere da 4 a 12 cifre. il valore predefinito è 5.</span><span class="sxs-lookup"><span data-stu-id="91191-120">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="91191-121">I numeri vengono utilizzati solo quando si crea PIN.</span><span class="sxs-lookup"><span data-stu-id="91191-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="91191-122">Lettere e caratteri speciali non vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="91191-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="91191-123">Un PIN è solo necessario per l'organizzatore della riunione quando Skype per gli utenti aziendali non è già avviato la riunione.</span><span class="sxs-lookup"><span data-stu-id="91191-123">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="91191-124">Se tutti gli utenti è accedono alla riunione, il PIN è obbligatorio per l'organizzatore della riunione avviare la riunione.</span><span class="sxs-lookup"><span data-stu-id="91191-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="91191-125">Impostazioni di protezione PIN vengono applicate a tutti i numeri di telefono associati a un ponte Microsoft.</span><span class="sxs-lookup"><span data-stu-id="91191-125">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="91191-126">Essi verranno applicate a tutte le riunioni che utilizzano i numeri di telefono associati a un ponte specificato.</span><span class="sxs-lookup"><span data-stu-id="91191-126">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="91191-127">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="91191-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="91191-128">Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .</span><span class="sxs-lookup"><span data-stu-id="91191-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="91191-129">Per impostare il numero di cifre in Aggiungi a 8:`Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="91191-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="91191-p107">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="91191-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="91191-133">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="91191-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="91191-134">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="91191-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="91191-p108">Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="91191-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="91191-137">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="91191-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="91191-138">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="91191-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="91191-139">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="91191-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="91191-140">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="91191-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="91191-p109">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="91191-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="91191-143">Le differenze nella nostra funzionalità di chiamata ai servizi di emergenza includono quanto segue: (i) Skype for Business potrebbe non conoscere la posizione effettiva di un chiamante ai servizi di emergenza, il che potrebbe comportare un instradamento della chiamata ai servizi di emergenza a un call center dei servizi di emergenza errato e/o l'invio dei servizi di emergenza a una località errata; (ii) se il dispositivo dell'utente non riceve l'alimentazione, sta sperimentando un'interruzione dell'alimentazione, o per qualsiasi motivo, non è in grado di accedere a Internet, l'utente non potrà effettuare la chiamata ai servizi di emergenza tramite i Piani per chiamate di Office 365; e (iii) sebbene i Piani per chiamate di Office 365 possano essere usati ovunque nel mondo laddove sia disponibile una connessione a Internet, gli utenti non dovrebbero chiamare i servizi di emergenza da una località al di fuori del proprio paese/regione poiché la chiamata non verrà probabilmente instradata al call center appropriato di tale paese/area geografica.</span><span class="sxs-lookup"><span data-stu-id="91191-143">See also</span></span>

[<span data-ttu-id="91191-144">Provare o acquistare le audioconferenze in Office 365</span><span class="sxs-lookup"><span data-stu-id="91191-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
