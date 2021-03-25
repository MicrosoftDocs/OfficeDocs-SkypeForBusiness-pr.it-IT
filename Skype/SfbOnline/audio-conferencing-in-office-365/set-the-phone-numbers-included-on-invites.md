---
title: Impostare in Skype for Business online i numeri di telefono inclusi negli inviti
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Ottenere i passaggi per creare un numero di telefono predefinito affinché i chiamanti possano partecipare ad una riunione di Skype for Business online. '
ms.openlocfilehash: 956c2fa23f61f0c0e24cd1c2a0802bd3f1397bb1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113222"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a><span data-ttu-id="0c92b-103">Impostare in Skype for Business online i numeri di telefono inclusi negli inviti</span><span class="sxs-lookup"><span data-stu-id="0c92b-103">Set the phone numbers included on invites in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="0c92b-104">Per informazioni sui numeri di telefono inclusi negli inviti di Microsoft Teams, vedere[Impostare i numeri di telefono inclusi negli inviti di Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span><span class="sxs-lookup"><span data-stu-id="0c92b-104">For information about meeting invite phone numbers in Microsoft Teams, see [Set the phone numbers included on invites in Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span></span>

<span data-ttu-id="0c92b-105">Le audioconferenze in Microsoft 365 o Office 365 consentono agli utenti dell'organizzazione di creare riunioni Skype for Business e quindi di accedere a tali riunioni tramite telefono.</span><span class="sxs-lookup"><span data-stu-id="0c92b-105">Audio Conferencing in Microsoft 365 or Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="0c92b-106">In Microsoft 365 e Office 365 è possibile usare un bridge di audioconferenza Microsoft o un bridge di audioconferenza di terze parti ospitato da un provider di servizi di audioconferenza (ACP) approvato.</span><span class="sxs-lookup"><span data-stu-id="0c92b-106">In Microsoft 365 and Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0c92b-107">Non esiste una risorsa che contenga un elenco di tutti i numeri con accesso esterno per Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="0c92b-107">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="0c92b-108">Se stai cercando di vedere se sono disponibili numeri di telefono per l'accesso esterno nella tua area geografica o paese/area geografica, usa l'interfaccia di amministrazione **Di Skype for Business** Numeri di telefono vocali , fai clic su Aggiungi e quindi su Nuovi numeri di  >    >   **servizio**. </span><span class="sxs-lookup"><span data-stu-id="0c92b-108">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="0c92b-109">Utilizza gli elenchi **Paese/area geografica**, **Stato/regione** e **Città** per filtrare la ricerca. > Inoltre, se stai cercando numeri di servizio gratuiti, seleziona **Numero verde** dall'elenco **Stato/regione**.</span><span class="sxs-lookup"><span data-stu-id="0c92b-109">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="0c92b-110">Un ponte per conferenze offre un insieme di numeri di telefono di accesso esterno per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0c92b-110">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="0c92b-111">Tutti questi numeri possono essere utilizzati per accedere alle riunioni create dall'organizzatore, ma è possibile selezionare quelli che verranno inclusi negli inviti alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="0c92b-111">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0c92b-112">Vi è un massimo per organizzatore di un numero a pagamento e un numero verde nell'invito alla riunione, ma è disponibile anche un collegamento nella parte inferiore di ogni invito che consente di aprire l'elenco completo di tutti i numeri di telefono di accesso esterno che possono essere utilizzati per accedere ad una riunione.</span><span class="sxs-lookup"><span data-stu-id="0c92b-112">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="0c92b-113">Impostare il numero di telefono di accesso esterno predefinito per l'organizzatore della riunione</span><span class="sxs-lookup"><span data-stu-id="0c92b-113">Set the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="0c92b-114">Accedere con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="0c92b-114">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="0c92b-115">Scegli **Interfaccia di amministrazione** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="0c92b-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="0c92b-116">Scegli **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="0c92b-116">Choose **Users**.</span></span>
    
    ![Visualizza la selezione utenti nell'interfaccia di amministrazione di Skype for Business](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="0c92b-118">Scegli gli utenti che desideri modificare:</span><span class="sxs-lookup"><span data-stu-id="0c92b-118">Choose the users you want to edit:</span></span>
    
   - <span data-ttu-id="0c92b-119">Per selezionare un singolo utente, seleziona il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0c92b-119">To select a single user, select the user's name.</span></span>
    
   - <span data-ttu-id="0c92b-120">Per selezionare tutti gli utenti della pagina, seleziona la casella accanto al **Nome visualizzato** nella parte superiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0c92b-120">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
   - <span data-ttu-id="0c92b-121">Per selezionare più utenti, seleziona la casella accanto al nome di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="0c92b-121">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="0c92b-122">Nel riquadro destro, scegli **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0c92b-122">In the right panel, choose **Edit**.</span></span>
    
    ![Scegli l'icona di modifica.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="0c92b-124">Scegli **servizi di audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="0c92b-124">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="0c92b-125">Nella pagina **Proprietà** nell'elenco **Nome provider** scegli il provider per l'utente.</span><span class="sxs-lookup"><span data-stu-id="0c92b-125">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="0c92b-126">A seconda del provider, completa le caselle seguenti.</span><span class="sxs-lookup"><span data-stu-id="0c92b-126">Depending on the provider, complete the following boxes.</span></span>
    
   - <span data-ttu-id="0c92b-127">**Microsoft è il provider**: usa gli elenchi **Numero a pagamento predefinito** e **Numero verde predefinito** per selezionare i numeri predefiniti per l'utente.</span><span class="sxs-lookup"><span data-stu-id="0c92b-127">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="0c92b-128">Almeno un numero verde deve essere assegnato al ponte per conferenze prima che possa essere impostato come numero verde predefinito per un utente.</span><span class="sxs-lookup"><span data-stu-id="0c92b-128">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="0c92b-129">Per ottenere un numero verde, consulta Ottenere i numeri di servizio [per Skype for Business.](/microsoftteams/getting-service-phone-numbers)</span><span class="sxs-lookup"><span data-stu-id="0c92b-129">To get a toll-free number, see [Getting service phone numbers for Skype for Business](/microsoftteams/getting-service-phone-numbers).</span></span> 
  
   - <span data-ttu-id="0c92b-130">**Il provider è una terza parte**: utilizza i campi **Numero a pagamento** e **Numero verde** per immettere i numeri per l'utente.</span><span class="sxs-lookup"><span data-stu-id="0c92b-130">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>


## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="0c92b-131">Reimpostare i numeri di telefono per Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="0c92b-131">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="0c92b-132">**Nell'interfaccia di amministrazione di Skype for Business** scegliere **Audioconferenza.**</span><span class="sxs-lookup"><span data-stu-id="0c92b-132">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="0c92b-133">Nella parte superiore della pagina, scegli **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="0c92b-133">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="0c92b-134">Scegli gli utenti che desideri ripristinare e quindi nel riquadro azioni, fai clic su **Cancella**.</span><span class="sxs-lookup"><span data-stu-id="0c92b-134">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="0c92b-135">Per impostazione predefinita, quando si modificano le impostazioni di conferenza dell'utente, un messaggio di posta elettronica viene inviato all'utente.</span><span class="sxs-lookup"><span data-stu-id="0c92b-135">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="0c92b-136">Per modificare questa impostazione, vedere [Abilitare o disabilitare l'invio di messaggi di posta elettronica quando vengono modificate le impostazioni di audioconferenza.](enable-or-disable-sending-emails-when-their-settings-change.md)</span><span class="sxs-lookup"><span data-stu-id="0c92b-136">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0c92b-137">Quando vengono modificate le impostazioni di audioconferenza di un utente, è necessario aggiornare le riunioni di Skype for Business ricorrenti e future ed inviarle ai partecipanti.</span><span class="sxs-lookup"><span data-stu-id="0c92b-137">When you change a user's audio conferencing settings, recurring and future Skype for Business meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="0c92b-138">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="0c92b-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="0c92b-139">Per renderle automatiche o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).</span><span class="sxs-lookup"><span data-stu-id="0c92b-139">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet.</span></span>
    
- <span data-ttu-id="0c92b-140">Usa il cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) per modificare il numero a pagamento o verde predefinito di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="0c92b-140">Use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="0c92b-141">Per modificare il numero verde predefinito di un utente, esegui:</span><span class="sxs-lookup"><span data-stu-id="0c92b-141">To change the default toll-free number for a user, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="0c92b-142">Usa il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** per cambiare il numero a pagamento o verde predefinito di utenti in base al loro numero predefinito originale o alla loro località.</span><span class="sxs-lookup"><span data-stu-id="0c92b-142">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0c92b-143">Per trovare bridgeID, usare il cmdlet **Get-CsOnlineDialInConferencingBridge.**</span><span class="sxs-lookup"><span data-stu-id="0c92b-143">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge** cmdlet.</span></span>
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="0c92b-144">Per impostare il numero verde predefinito per tutti gli utenti senza uno su +18005551234, eseguire:</span><span class="sxs-lookup"><span data-stu-id="0c92b-144">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="0c92b-145">Per modificare il numero verde predefinito di tutti gli utenti che hanno +18005551234 come numero verde predefinito in +18005551239, eseguire:</span><span class="sxs-lookup"><span data-stu-id="0c92b-145">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="0c92b-146">Per impostare il numero verde predefinito di tutti gli utenti che si trovano negli Stati Uniti su +18005551234, eseguire:</span><span class="sxs-lookup"><span data-stu-id="0c92b-146">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="0c92b-147">Per altre informazioni sulle Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="0c92b-147">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="0c92b-p107">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="0c92b-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0c92b-151">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0c92b-151">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="0c92b-152">Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c92b-152">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="0c92b-153">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="0c92b-153">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="0c92b-154">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="0c92b-154">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="0c92b-155">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="0c92b-155">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="0c92b-156">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="0c92b-156">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="0c92b-157">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="0c92b-157">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="0c92b-158">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0c92b-158">Related topics</span></span>

[<span data-ttu-id="0c92b-159">Provare o acquistare audioconferenze in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="0c92b-159">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)