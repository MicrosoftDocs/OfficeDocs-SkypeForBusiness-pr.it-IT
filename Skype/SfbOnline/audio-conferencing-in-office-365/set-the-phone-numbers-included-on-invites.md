---
title: Impostare il telefono numeri incluso nel invita
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'È possibile ottenere i passaggi per creare un numero di telefono predefinito per i chiamanti partecipare a una Skype per riunione in linea aziendale. '
ms.openlocfilehash: 5ddc20d1b9166315581a6f894c5d630d9e247881
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568282"
---
# <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="85d44-103">Impostare il telefono numeri incluso nel invita</span><span class="sxs-lookup"><span data-stu-id="85d44-103">Set the phone numbers included on invites</span></span>

<span data-ttu-id="85d44-104">Audioconferenze con accesso esterno in Office 365 consente agli utenti dell'organizzazione creare Skype per le riunioni aziendali e Teams Microsoft e quindi consentire agli utenti di accedere a tali riunioni mediante un telefono.</span><span class="sxs-lookup"><span data-stu-id="85d44-104">Audio Conferencing in Office 365 enables users in your organization to create Skype for Business and Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="85d44-105">In Office 365, è necessario l'opzione di utilizzare un ponte per conferenze audio Microsoft o un ponte per conferenze audio di terze parti ospitato da un provider approvato audioconferenza (ACP).</span><span class="sxs-lookup"><span data-stu-id="85d44-105">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="85d44-106">Non esiste una risorsa che contenga un elenco di tutti i numeri con accesso esterno per Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="85d44-106">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="85d44-107">Se si desidera utilizzare per verificare se sono disponibili i numeri di telefono di accesso esterno nell'area o paese/area geografica, utilizzare **Skype per Business admin center** > **vocale** > **I numeri di telefono**, fare clic su **Aggiungi** , quindi **nuovi numeri di servizio **.</span><span class="sxs-lookup"><span data-stu-id="85d44-107">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="85d44-108">Utilizzare gli elenchi **Paese/area geografica**, **paese** e **città** per filtrare la ricerca. >, inoltre, se sta cercando numeri a pagamento servizio gratuito, **numero verde** selezionare dal **paese** elenco.</span><span class="sxs-lookup"><span data-stu-id="85d44-108">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="85d44-109">Un ponte per conferenze offre un set di numeri di telefono di accesso esterno per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="85d44-109">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="85d44-110">Tutti gli elementi da utilizzare per partecipare alle riunioni creati dall'organizzatore della riunione, ma è possibile selezionare quelli che verranno inclusi nel proprio gli inviti di riunione.</span><span class="sxs-lookup"><span data-stu-id="85d44-110">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="85d44-111">Può esistere un massimo di un numero a pagamento e un numero verde nel invito alla riunione per organizzare una riunione, ma è disponibile anche un collegamento presente nella parte inferiore di ogni invito alla riunione che consente di aprire l'elenco completo di tutti i numeri di telefono di accesso esterno che può essere utilizzato per accedere a una riunione.</span><span class="sxs-lookup"><span data-stu-id="85d44-111">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="85d44-112">Impostare il numero di telefono di accesso esterno predefinito per l'organizzatore della riunione</span><span class="sxs-lookup"><span data-stu-id="85d44-112">Set the default dial-in phone number for a meeting organizer</span></span>

<span data-ttu-id="85d44-113">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="85d44-113">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="85d44-114">Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="85d44-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![Visualizza la selezione utenti in Microsoft Teams e Skype per Business Admin Center](../images/teamsselectusers.png)

2. <span data-ttu-id="85d44-116">Nella parte superiore della pagina, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="85d44-116">At the top of the page, click **Edit**.</span></span>

    ![Fare clic su Modifica nel team di Microsoft e Skype per Business Admin Center](../images/teamsedituser.png)

3. <span data-ttu-id="85d44-118">Accanto a **Servizi di conferenza Audio**, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="85d44-118">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Fare clic su Modifica accanto a conferenze Audio](../images/teamseditaudioconf.png)

4. <span data-ttu-id="85d44-120">Utilizzare i campi **numero a pagamento** o **numero verde** per immettere i numeri per l'utente.</span><span class="sxs-lookup"><span data-stu-id="85d44-120">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="85d44-121">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="85d44-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="85d44-122">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="85d44-122">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="85d44-123">Scegliere **Admin Center** > **Skype per le aziende**.</span><span class="sxs-lookup"><span data-stu-id="85d44-123">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="85d44-124">Scegliere **utenti**.</span><span class="sxs-lookup"><span data-stu-id="85d44-124">Choose **Users**.</span></span>
    
    ![Visualizza la selezione utenti in Skype per interfaccia di amministrazione di Business](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="85d44-126">Scegliere gli utenti che si desidera modificare:</span><span class="sxs-lookup"><span data-stu-id="85d44-126">Choose the users you want to edit:</span></span>
    
  - <span data-ttu-id="85d44-127">Per selezionare un singolo utente, selezionare il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="85d44-127">To select a single user, select the user's name.</span></span>
    
  - <span data-ttu-id="85d44-128">Per selezionare tutti gli utenti della pagina, selezionare la casella accanto al **nome visualizzato** nella parte superiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="85d44-128">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
  - <span data-ttu-id="85d44-129">Per selezionare più utenti, selezionare la casella accanto al nome di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="85d44-129">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="85d44-130">Riquadro destro fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="85d44-130">In the right panel, choose **Edit**.</span></span>
    
    ![Scegliere l'icona di modifica.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="85d44-132">Scegliere **servizi di conferenza Audio**.</span><span class="sxs-lookup"><span data-stu-id="85d44-132">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="85d44-133">Nella pagina **proprietà** nell'elenco **nome Provider di** scegliere il provider per l'utente.</span><span class="sxs-lookup"><span data-stu-id="85d44-133">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="85d44-134">A seconda del provider, completare le caselle seguenti.</span><span class="sxs-lookup"><span data-stu-id="85d44-134">Depending on the provider, complete the following boxes.</span></span>
    
  - <span data-ttu-id="85d44-135">**Microsoft è il provider**: **numero verde predefinito** elenchi per selezionare i numeri predefiniti per l'utente e utilizzare il **numero a pagamento predefinito** .</span><span class="sxs-lookup"><span data-stu-id="85d44-135">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="85d44-136">Almeno un numero verde deve essere assegnato ai bridge conferenza prima può essere impostata come il numero verde predefinito di un utente.</span><span class="sxs-lookup"><span data-stu-id="85d44-136">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="85d44-137">Per ottenere un numero verde, vedere [Getting numeri di telefono del servizio per Skype per le aziende e team di Microsoft](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="85d44-137">To get a toll-free number, see [Getting service phone numbers for Skype for Business and Microsoft Teams](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span> 
  
  - <span data-ttu-id="85d44-138">**Terze parti sono il provider**: utilizzare i campi **numero a pagamento** e **numero verde** per immettere i numeri per l'utente.</span><span class="sxs-lookup"><span data-stu-id="85d44-138">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>


## <a name="change-the-audio-conferencing-phone-number-for-users"></a><span data-ttu-id="85d44-139">Modificare il numero di telefono per conferenze audio per gli utenti</span><span class="sxs-lookup"><span data-stu-id="85d44-139">Change the audio conferencing phone number for users</span></span>

<span data-ttu-id="85d44-140">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="85d44-140">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="85d44-141">Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="85d44-141">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="85d44-142">Nella parte superiore della pagina, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="85d44-142">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="85d44-143">Accanto a **Servizi di conferenza Audio**, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="85d44-143">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="85d44-144">Utilizzare i campi **numero a pagamento** o **numero verde** per immettere i numeri per l'utente.</span><span class="sxs-lookup"><span data-stu-id="85d44-144">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>

## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="85d44-145">Reimpostare i numeri di telefono di accesso esterno alle audioconferenze</span><span class="sxs-lookup"><span data-stu-id="85d44-145">Reset audio conferencing phone numbers</span></span>

<span data-ttu-id="85d44-146">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="85d44-146">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="85d44-147">**Skype per interfaccia di amministrazione di Business**, scegliere **audioconferenze**.</span><span class="sxs-lookup"><span data-stu-id="85d44-147">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="85d44-148">Nella parte superiore della pagina, scegliere **utenti**.</span><span class="sxs-lookup"><span data-stu-id="85d44-148">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="85d44-149">Scegliere gli utenti che si desidera ripristinare e quindi nel riquadro azioni fare clic su **Cancella**.</span><span class="sxs-lookup"><span data-stu-id="85d44-149">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="85d44-150">Per impostazione predefinita, quando si modificano le impostazioni di conferenza dell'utente, un messaggio di posta elettronica viene inviato all'utente.</span><span class="sxs-lookup"><span data-stu-id="85d44-150">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="85d44-151">Per modificare questa impostazione, vedere [abilitare o disabilitare l'invio messaggi di posta elettronica quando modificano le impostazioni di conferenza Audio](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="85d44-151">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="85d44-152">Quando si modificano le impostazioni di conferenza audio di un utente, Skype ricorrenti e future per le riunioni aziendali e Microsoft Teams deve essere aggiornato e inviati ai partecipanti.</span><span class="sxs-lookup"><span data-stu-id="85d44-152">When you change a user's audio conferencing settings, recurring and future Skype for Business and Microsoft Teams meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="85d44-153">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="85d44-153">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="85d44-154">Per renderle automatiche o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).</span><span class="sxs-lookup"><span data-stu-id="85d44-154">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet.</span></span>
    
- <span data-ttu-id="85d44-155">Usa il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) per modificare il numero a pagamento o verde predefinito di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="85d44-155">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="85d44-156">Per modificare il numero verde predefinito di un utente, esegui:</span><span class="sxs-lookup"><span data-stu-id="85d44-156">To change the default toll-free number for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="85d44-157">Usa il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** per cambiare il numero a pagamento o verde predefinito di utenti in base al loro numero predefinito originale o alla loro località.</span><span class="sxs-lookup"><span data-stu-id="85d44-157">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="85d44-158">Per trovare il BridgeID, utilizzare il cmdlet **Get-CsOnlineDialInConferencingBridge** .</span><span class="sxs-lookup"><span data-stu-id="85d44-158">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge** cmdlet.</span></span>
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="85d44-159">Per impostare il numero verde predefinito per tutti gli utenti senza 1 in modo da +18005551234, eseguire:</span><span class="sxs-lookup"><span data-stu-id="85d44-159">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="85d44-160">Per modificare il numero verde predefinito di tutti gli utenti che hanno +18005551234 come il numero verde predefinito per +18005551239, eseguire:</span><span class="sxs-lookup"><span data-stu-id="85d44-160">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="85d44-161">Per impostare il numero verde predefinito di tutti gli utenti presente negli Stati Uniti a +18005551234, eseguire:</span><span class="sxs-lookup"><span data-stu-id="85d44-161">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="85d44-162">Fonti di ulteriori informazioni su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="85d44-162">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="85d44-p107">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="85d44-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="85d44-166">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="85d44-166">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="85d44-167">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="85d44-167">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="85d44-p108">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="85d44-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="85d44-170">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="85d44-170">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="85d44-171">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="85d44-171">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="85d44-172">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="85d44-172">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="85d44-173">See also</span><span class="sxs-lookup"><span data-stu-id="85d44-173">Related topics</span></span>

[<span data-ttu-id="85d44-174">Provare o acquistare le audioconferenze in Office 365</span><span class="sxs-lookup"><span data-stu-id="85d44-174">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
