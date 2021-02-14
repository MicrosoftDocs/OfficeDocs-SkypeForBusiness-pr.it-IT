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
ms.openlocfilehash: b7a4ee991ff8a8e41401b3b2d2dc20aa20708b88
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163935"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a><span data-ttu-id="05caf-103">Impostare in Skype for Business online i numeri di telefono inclusi negli inviti</span><span class="sxs-lookup"><span data-stu-id="05caf-103">Set the phone numbers included on invites in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="05caf-104">Per informazioni sui numeri di telefono inclusi negli inviti di Microsoft Teams, vedere[Impostare i numeri di telefono inclusi negli inviti di Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span><span class="sxs-lookup"><span data-stu-id="05caf-104">For information about meeting invite phone numbers in Microsoft Teams, see [Set the phone numbers included on invites in Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span></span>

<span data-ttu-id="05caf-p101">I servizi di audioconferenza di Microsoft 365 o Office 365 consentono agli utenti dell'organizzazione di creare riunioni Skype for Business e quindi di accedere a tali riunioni tramite telefono. In Microsoft 365 e Office 365 è possibile usare un bridge per audioconferenze Microsoft o un bridge per audioconferenze di terze parti ospitato da un provider di servizi di audioconferenza approvato.</span><span class="sxs-lookup"><span data-stu-id="05caf-p101">Audio Conferencing in Microsoft 365 or Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone. In Microsoft 365 and Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="05caf-p102">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing. If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**. Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span><span class="sxs-lookup"><span data-stu-id="05caf-p102">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing. If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**. Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="05caf-p103">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span><span class="sxs-lookup"><span data-stu-id="05caf-p103">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="05caf-112">Vi è un massimo per organizzatore di un numero a pagamento e un numero verde nell'invito alla riunione, ma è disponibile anche un collegamento nella parte inferiore di ogni invito che consente di aprire l'elenco completo di tutti i numeri di telefono di accesso esterno che possono essere utilizzati per accedere ad una riunione.</span><span class="sxs-lookup"><span data-stu-id="05caf-112">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="05caf-113">Impostare il numero di telefono di accesso esterno predefinito per l'organizzatore della riunione</span><span class="sxs-lookup"><span data-stu-id="05caf-113">Set the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="05caf-114">Accedere con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="05caf-114">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="05caf-115">Scegli **Interfaccia di amministrazione** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="05caf-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="05caf-116">Scegli **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="05caf-116">Choose **Users**.</span></span>
    
    ![Visualizza la selezione utenti nell'interfaccia di amministrazione di Skype for Business](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="05caf-118">Scegli gli utenti che desideri modificare:</span><span class="sxs-lookup"><span data-stu-id="05caf-118">Choose the users you want to edit:</span></span>
    
   - <span data-ttu-id="05caf-119">Per selezionare un singolo utente, seleziona il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="05caf-119">To select a single user, select the user's name.</span></span>
    
   - <span data-ttu-id="05caf-120">Per selezionare tutti gli utenti della pagina, seleziona la casella accanto al **Nome visualizzato** nella parte superiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="05caf-120">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
   - <span data-ttu-id="05caf-121">Per selezionare più utenti, seleziona la casella accanto al nome di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="05caf-121">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="05caf-122">Nel riquadro destro, scegli **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="05caf-122">In the right panel, choose **Edit**.</span></span>
    
    ![Scegli l'icona di modifica.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="05caf-124">Scegli **servizi di audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="05caf-124">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="05caf-p104">On the **Properties** page, in the **Provider name** list, choose the provider for the user. Depending on the provider, complete the following boxes.</span><span class="sxs-lookup"><span data-stu-id="05caf-p104">On the **Properties** page, in the **Provider name** list, choose the provider for the user. Depending on the provider, complete the following boxes.</span></span>
    
   - <span data-ttu-id="05caf-127">**Microsoft è il provider**: usa gli elenchi **Numero a pagamento predefinito** e **Numero verde predefinito** per selezionare i numeri predefiniti per l'utente.</span><span class="sxs-lookup"><span data-stu-id="05caf-127">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="05caf-p105">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user. To get a toll-free number, see [Getting service phone numbers for Skype for Business](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="05caf-p105">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user. To get a toll-free number, see [Getting service phone numbers for Skype for Business](/microsoftteams/getting-service-phone-numbers).</span></span> 
  
   - <span data-ttu-id="05caf-130">**Il provider è una terza parte**: utilizza i campi **Numero a pagamento** e **Numero verde** per immettere i numeri per l'utente.</span><span class="sxs-lookup"><span data-stu-id="05caf-130">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>


## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="05caf-131">Reimpostare i numeri di telefono per Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="05caf-131">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="05caf-132">**Nell'interfaccia di amministrazione di Skype for Business,** scegli **Audioconferenza.**</span><span class="sxs-lookup"><span data-stu-id="05caf-132">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="05caf-133">Nella parte superiore della pagina, scegli **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="05caf-133">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="05caf-134">Scegli gli utenti che desideri ripristinare e quindi nel riquadro azioni, fai clic su **Cancella**.</span><span class="sxs-lookup"><span data-stu-id="05caf-134">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="05caf-p106">By default, when you change a user's conferencing settings, an email is sent to the user. To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="05caf-p106">By default, when you change a user's conferencing settings, an email is sent to the user. To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="05caf-137">Quando vengono modificate le impostazioni di audioconferenza di un utente, è necessario aggiornare le riunioni di Skype for Business ricorrenti e future ed inviarle ai partecipanti.</span><span class="sxs-lookup"><span data-stu-id="05caf-137">When you change a user's audio conferencing settings, recurring and future Skype for Business meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="05caf-138">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="05caf-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="05caf-139">Per renderle automatiche o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).</span><span class="sxs-lookup"><span data-stu-id="05caf-139">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet.</span></span>
    
- <span data-ttu-id="05caf-140">Usa il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) per modificare il numero a pagamento o verde predefinito di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="05caf-140">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="05caf-141">Per modificare il numero verde predefinito di un utente, esegui:</span><span class="sxs-lookup"><span data-stu-id="05caf-141">To change the default toll-free number for a user, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="05caf-142">Usa il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** per cambiare il numero a pagamento o verde predefinito di utenti in base al loro numero predefinito originale o alla loro località.</span><span class="sxs-lookup"><span data-stu-id="05caf-142">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="05caf-143">Per trovare il BridgeID, usa il cmdlet **Get-CsOnlineDialInConferencingBridge.**</span><span class="sxs-lookup"><span data-stu-id="05caf-143">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge** cmdlet.</span></span>
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="05caf-144">Per impostare il numero verde predefinito per tutti gli utenti senza un numero su +18005551234, esegui:</span><span class="sxs-lookup"><span data-stu-id="05caf-144">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="05caf-145">Per cambiare il numero verde predefinito di tutti gli utenti che hanno +18005551234 come numero verde predefinito in +18005551239, esegui:</span><span class="sxs-lookup"><span data-stu-id="05caf-145">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="05caf-146">Per impostare il numero verde predefinito di tutti gli utenti che si trovano negli Stati Uniti su +18005551234, esegui:</span><span class="sxs-lookup"><span data-stu-id="05caf-146">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="05caf-147">Altre informazioni sulle Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05caf-147">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="05caf-p107">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="05caf-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="05caf-151">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="05caf-151">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="05caf-152">Perché è necessario usare PowerShell di Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="05caf-152">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="05caf-p108">Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="05caf-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="05caf-155">Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05caf-155">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="05caf-156">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="05caf-156">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="05caf-157">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="05caf-157">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="05caf-158">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="05caf-158">Related topics</span></span>

[<span data-ttu-id="05caf-159">Provare o acquistare audioconferenze in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="05caf-159">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
