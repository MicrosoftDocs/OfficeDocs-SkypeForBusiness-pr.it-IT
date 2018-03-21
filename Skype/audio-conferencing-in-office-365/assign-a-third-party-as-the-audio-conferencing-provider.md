---
title: Assegnazione di terze parti come provider di servizi di conferenza audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Informazioni su come configurare di terze parti come provider di servizi di conferenza telefonica con Skype per le aziende. '
ms.openlocfilehash: 5ae513c754764933f08370139eeb557f0fb39211
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2018
---
# <a name="assign-a-third-party-as-the-audio-conferencing-provider"></a><span data-ttu-id="0e7e7-103">Assegnazione di terze parti come provider di servizi di conferenza audio</span><span class="sxs-lookup"><span data-stu-id="0e7e7-103">Assign a third-party as the audio conferencing provider</span></span>

<span data-ttu-id="0e7e7-104">Un provider di servizi di conferenza audio fornisce di *ponte conferenza*.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-104">An audio conferencing provider supplies the *conference bridge*.</span></span> <span data-ttu-id="0e7e7-105">Bridge conferenza fornisce il numero di telefono di accesso esterno, pin e gli ID conferenza per le riunioni creati.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-105">The conference bridge provides the dial-in phone number, PINs, and conference IDs for meetings that are created.</span></span> <span data-ttu-id="0e7e7-106">È sufficiente assegnare un provider di servizi di conferenza audio a coloro che desidera programmare o lead Skype per le riunioni aziendali o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-106">You only need to assign an audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0e7e7-107">Per Microsoft Teams, un utente non può utilizzare un provider di servizi di conferenza audio di terze parti, devono utilizzare audioconferenze con accesso esterno in Office 365, che imposta il provider di servizi di conferenza audio a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-107">For Microsoft Teams, a user can't use a third-party audio conferencing provider, they must use Audio Conferencing in Office 365, which sets the audio conferencing provider to Microsoft.</span></span> 
  
## <a name="steps-to-do-before-you-can-assign-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="0e7e7-108">Passaggi da eseguire prima di poter assegnare un provider di servizi di conferenza audio di terze parti</span><span class="sxs-lookup"><span data-stu-id="0e7e7-108">Steps to do BEFORE you can assign a third-party audio conferencing provider</span></span>

1. <span data-ttu-id="0e7e7-109">A seconda del piano di Office 365, potrebbe essere necessario acquistare le licenze di componente aggiuntivo **Per conferenze Audio** per gli utenti dell'organizzazione che desiderano programmare o lead Skype per Business o Microsoft Teams riunioni tramite servizi di conferenza Audio.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-109">Depending on your Office 365 plan, you might need to buy **Audio Conferencing** add-on licenses for the people in your organization who are going to schedule or lead Skype for Business or Microsoft Teams meetings using Audio Conferencing.</span></span> <span data-ttu-id="0e7e7-110">Per ulteriori informazioni, vedere [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="0e7e7-110">To learn more, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="0e7e7-111">Se è stato acquistato licenze di componente aggiuntivo **Per conferenze Audio** , assegnarli a utenti all'interno dell'organizzazione che desiderano programmare o condurre riunioni che utilizzano i servizi di conferenza Audio.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-111">If you purchased **Audio Conferencing** add-on licenses, assign them to the people in your organization who are going to schedule or lead meetings that use Audio Conferencing.</span></span> <span data-ttu-id="0e7e7-112">Vedi [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="0e7e7-112">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0e7e7-113">Se si assegna una licenza di **Audioconferenza** a un utente **AFTER** assegnarle un provider di servizi di conferenza audio di terze parti, tale persona viene automaticamente impostata su invece utilizzare Microsoft come i provider di servizi di conferenza audio!</span><span class="sxs-lookup"><span data-stu-id="0e7e7-113">If you assign an **Audio Conferencing** license to someone **AFTER** you assign them a third-party audio conferencing provider, that person will automatically be set to use Microsoft as their audio conferencing provider instead!</span></span> <span data-ttu-id="0e7e7-114">In questo caso, è necessario rimuovere Microsoft come provider di servizi di conferenza audio prima di poter assegnare un provider di servizi di conferenza audio di terze parti a loro.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-114">If this happens, you will need to first remove Microsoft as the audio conferencing provider before you can assign a third-party audio conferencing provider to them.</span></span>
  
3. <span data-ttu-id="0e7e7-115">Trova un provider di servizi di conferenza audio di terze parti a [Individuare Microsoft](https://go.microsoft.com/fwlink/?LinkId=797530).</span><span class="sxs-lookup"><span data-stu-id="0e7e7-115">Find a third-party audio conferencing provider at [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530).</span></span> <span data-ttu-id="0e7e7-116">Contattarli e Scopri come realizzare gli obiettivi impostare con loro.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-116">Contact them and find out how to get things set up with them.</span></span>
    
    <span data-ttu-id="0e7e7-117">Si sono disponibili:</span><span class="sxs-lookup"><span data-stu-id="0e7e7-117">They will give you:</span></span>
    
  - <span data-ttu-id="0e7e7-118">**Numeri di accesso (numero verde)** e numeri verdi, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-118">**Dial-in numbers (toll)** and toll-free numbers if they are available.</span></span>
    
  - <span data-ttu-id="0e7e7-119">**ID conferenza** utilizzati per ogni persona che pianifica le riunioni.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-119">**Conference IDs** that are used for each person who schedules meetings.</span></span> <span data-ttu-id="0e7e7-120">Alcuni audioconferenza chiama tali passcode di conferenza.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-120">Some ACPs call these conference passcodes.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0e7e7-121">Se è stato fatto iniziale impostata per un'AUDIOCONFERENZA di terze parti ma adesso è necessario apportare modifiche, nella parte inferiore della pagina **Microsoft Bridge** **fare clic qui per configurare un provider di servizi di conferenza audio di terze parti**.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-121">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="0e7e7-122">Quando si abilita una persona per le conferenze audio e assegna loro un provider di servizi di conferenza audio di terze parti, i numeri di audio e gli ID conferenza (passcode) vengono aggiunte automaticamente qualsiasi **nuova** Skype per le riunioni Online Business creati.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-122">When you enable a person for audio conferencing, and assign them a third-party audio conferencing provider, the audio numbers and conference IDs (passcodes) are automatically added to any **new** Skype for Business Online meetings that they create.</span></span>
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-a-user"></a><span data-ttu-id="0e7e7-123">Come assegnare a un provider di servizi di conferenza audio di terze parti a un utente</span><span class="sxs-lookup"><span data-stu-id="0e7e7-123">How to assign a third-party audio conferencing provider to a user</span></span>

1. <span data-ttu-id="0e7e7-124">**Skype per interfaccia di amministrazione di Business**, scegliere **utenti**.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-124">In the **Skype for Business admin center**, choose **Users**.</span></span> <span data-ttu-id="0e7e7-125">Selezionare l'utente dall'elenco e fare clic su **Modifica** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-125">Select the user from the list and click **Edit** in the action pane.</span></span>
    
2. <span data-ttu-id="0e7e7-126">Nella pagina proprietà dell'utente, fare clic su **servizi di conferenza Audio** e immettere le informazioni:</span><span class="sxs-lookup"><span data-stu-id="0e7e7-126">On the user's properties page, click **Audio conferencing** and enter this information:</span></span>
    
  - <span data-ttu-id="0e7e7-127">**Nome del provider** Nell'elenco, selezionare il provider di terze parti.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-127">**Provider name** Select the third-party provider from the list.</span></span>
    
  - <span data-ttu-id="0e7e7-128">**Numero verde predefinito** È richiesto.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-128">**Default toll number** This is required.</span></span>
    
  - <span data-ttu-id="0e7e7-129">**Numero verde predefinito** Ciò non necessari.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-129">**Default toll-free number** This not required.</span></span>
    
  - <span data-ttu-id="0e7e7-130">**ID conferenza** Viene fornito dal provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-130">**Conference ID** This is provided by your audio conferencing provider.</span></span>
    
3. <span data-ttu-id="0e7e7-131">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-131">Click **Save**.</span></span>
    
4. <span data-ttu-id="0e7e7-132">Inviare il PIN è stato ricevuto dal provider di servizi di conferenza audio ogni contatto.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-132">Send each person the PIN you received from the audio conferencing provider.</span></span> <span data-ttu-id="0e7e7-133">Il PIN potrebbe essere necessario chiamare l'organizzatore della conferenza telefonica o coordinatore.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-133">The PIN may be required to call in as the conference call organizer or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0e7e7-134">Quando si utilizza un provider di servizi di conferenza audio di terze parti, non vi è un modo visualizzare o impostare i pin per conto degli organizzatori di riunioni.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-134">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-many-people-at-the-same-time"></a><span data-ttu-id="0e7e7-135">Come assegnare a un provider di servizi di conferenza audio di terze parti a molte persone alla stessa ora</span><span class="sxs-lookup"><span data-stu-id="0e7e7-135">How to assign a third-party audio conferencing provider to many people at the same time</span></span>

1. <span data-ttu-id="0e7e7-136">**Skype per interfaccia di amministrazione di Business**, scegliere **audioconferenze** > **bridge di Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-136">In the **Skype for Business admin center**, choose **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="0e7e7-137">Nella parte inferiore della pagina, fare clic sul collegamento di **Se si desidera configurare un provider di servizi di conferenza audio di terze parti in realtà, fare clic qui**.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-137">At the bottom of the page, click the link in **If you would like to configure a third-party audio conferencing provider instead, click here**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0e7e7-138">Se è stato fatto iniziale impostata per un'AUDIOCONFERENZA di terze parti ma adesso è necessario apportare modifiche, nella parte inferiore della pagina **Microsoft Bridge** , **fare clic qui per configurare un provider di servizi di conferenza audio di terze parti**.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-138">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page, **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
2. <span data-ttu-id="0e7e7-139">Nella pagina **Configura una terza parte del provider di servizi di conferenza audio** , in **utenti importazione ed esportazione**, fare clic su **Esportazione guidata**e quindi seguire la procedura **guidata utenti di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-139">On the **Configure a third party audio conferencing provider** page, under **Import and export users**, click **Export wizard**, and then follow the steps in the **Export Users wizard**.</span></span> <span data-ttu-id="0e7e7-140">Al termine, è necessario un file in cui sono elencate le persone che si desidera impostare per le conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-140">When you finish, you'll have a file that lists the people you want to set up for audio conferencing.</span></span>
    
3. <span data-ttu-id="0e7e7-141">Inviare il file creato al provider di servizi di conferenza audio di terze parti.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-141">Send the file you created to your third-party audio conferencing provider.</span></span> <span data-ttu-id="0e7e7-142">Verrà aggiungono informazioni sulle conferenze audio per gli utenti elencati nel file e quindi restituisce il file a un utente.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-142">They will add audio conferencing information for the people listed in the file, and then return the file to you.</span></span>
    
4. <span data-ttu-id="0e7e7-143">Verificare che il file restituito abbia le informazioni corrette in essa contenuti.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-143">Double-check that the returned file has the right information in it.</span></span> <span data-ttu-id="0e7e7-144">È stata ascoltare di istanze di cui non tutti i contatti presenti nel file caso è possibile ottenere le informazioni corrette.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-144">We've heard of instances where not everyone listed in the file got the right information.</span></span>
    
5. <span data-ttu-id="0e7e7-145">Nella **pagina provider di audioconferenza di terze parti Configure**, in **agli utenti di importazione ed esportazione**, fare clic su **Importazione guidata**e quindi seguire le istruzioni della **procedura guidata Importa utenti**</span><span class="sxs-lookup"><span data-stu-id="0e7e7-145">On the **Configure a third-party audio conferencing provider page**, under **Import and export users**, click **Import wizard**, and then follow the steps in the **Import Users wizard**</span></span>
    
6. <span data-ttu-id="0e7e7-146">Inviare il PIN è stato ricevuto dal provider di servizi di conferenza audio ogni contatto.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-146">Send each person the PIN you received from the audio conferencing provider.</span></span> <span data-ttu-id="0e7e7-147">Il PIN può essere necessario per intervenire come coordinatore o organizzatore della conferenza telefonica.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-147">The PIN may be required to call in as the conference call organizer, or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0e7e7-148">Quando si utilizza un provider di servizi di conferenza audio di terze parti, non vi è un modo visualizzare o impostare i pin per conto degli organizzatori di riunioni.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-148">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="when-to-use-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="0e7e7-149">Quando utilizzare un provider di servizi di conferenza audio di terze parti</span><span class="sxs-lookup"><span data-stu-id="0e7e7-149">When to use a third-party audio conferencing provider</span></span>

<span data-ttu-id="0e7e7-150">In caso di un paese o regione in audioconferenze con accesso esterno in Office 365 non è disponibile, la qualità del servizio non è grande a causa della posizione o si dispone di un contratto esistente con un provider di servizi di conferenza audio di terze parti, è consigliabile utilizzare un audio di terze parti provider di servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-150">If you are in a country or region where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract with a third-party audio conferencing provider, we recommend using a third-party audio conferencing provider.</span></span> <span data-ttu-id="0e7e7-151">In caso contrario, è consigliabile utilizzare Microsoft come provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-151">Otherwise, we recommend using Microsoft as your audio conferencing provider.</span></span>
  
## <a name="automate-assigning-the-third-party-audio-conferencing-provider-by-using-windows-powershell"></a><span data-ttu-id="0e7e7-152">Automatizzare l'assegnazione il provider di servizi di conferenza audio di terze parti tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e7e7-152">Automate assigning the third-party audio conferencing provider by using Windows PowerShell</span></span>

- <span data-ttu-id="0e7e7-153">Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il cmdlet [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) .</span><span class="sxs-lookup"><span data-stu-id="0e7e7-153">To save time or automate this, you can use the [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) cmdlet.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0e7e7-154">Per modificare il provider di audio da Microsoft a un provider di servizi di conferenza audio di terze parti, è necessario rimuovere Microsoft come provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-154">To change the audio provider from Microsoft to a third-party audio conferencing provider, you must remove Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="0e7e7-155">A tale scopo, utilizzare il cmdlet [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) .</span><span class="sxs-lookup"><span data-stu-id="0e7e7-155">To do this, use the [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) cmdlet.</span></span>
  
- <span data-ttu-id="0e7e7-156">Per ulteriori informazioni sull'uso di Windows PowerShell, consulta [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="0e7e7-156">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
    
## <a name="what-else-do-i-need-to-know"></a><span data-ttu-id="0e7e7-157">Altre informazioni utili</span><span class="sxs-lookup"><span data-stu-id="0e7e7-157">What else do I need to know?</span></span>

<span data-ttu-id="0e7e7-158">Una persona all'interno dell'organizzazione può utilizzare solo un provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-158">A person in your organization can only use one audio conferencing provider.</span></span> <span data-ttu-id="0e7e7-159">Per modificare il provider di servizi di conferenza audio di una persona a Microsoft, vedere [Microsoft assegnare come provider di servizi di conferenza audio](assign-microsoft-as-the-audio-conferencing-provider.md)o [lo spostamento di provider di servizi di conferenza audio di un utente a Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) .</span><span class="sxs-lookup"><span data-stu-id="0e7e7-159">To change a person's audio conferencing provider to Microsoft, see [Moving a user's audio conferencing provider to Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0e7e7-160">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0e7e7-160">Related Topics</span></span>

[<span data-ttu-id="0e7e7-161">Configurare le audioconferenze per Skype for Business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0e7e7-161">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  
[<span data-ttu-id="0e7e7-162">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="0e7e7-162">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

