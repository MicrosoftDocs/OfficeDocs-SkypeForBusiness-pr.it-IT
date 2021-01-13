---
title: Visualizzare le informazioni sul PIN degli utenti in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Riepilogo: visualizzare le informazioni sul PIN degli utenti in Skype for Business Server.'
ms.openlocfilehash: fa5385c1ca318c4a41e17088368d9928fd6d0e0b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806506"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a><span data-ttu-id="37961-103">Visualizzare le informazioni sul PIN degli utenti in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="37961-103">View user PIN information in Skype for Business Server</span></span>
 
<span data-ttu-id="37961-104">**Riepilogo:** Visualizzare le informazioni sul PIN degli utenti in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="37961-104">**Summary:** View user PIN information in Skype for Business Server.</span></span>
  
<span data-ttu-id="37961-105">Per partecipare a una conferenza telefonica con accesso esterno come utente autenticato, un utente di Skype for Business Server con le credenziali di servizi di dominio Active Directory richiede un codice PIN (Personal Identification Number).</span><span class="sxs-lookup"><span data-stu-id="37961-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="37961-106">È possibile visualizzare le informazioni sul PIN di un utente dal pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="37961-106">You can view a user's PIN information from Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="37961-107">È possibile visualizzare informazioni sullo stato del PIN, ad esempio per scoprire se il PIN è stato impostato o quando è stato modificato l'ultima volta, ma non è possibile vedere il PIN corrente controllandone lo stato.</span><span class="sxs-lookup"><span data-stu-id="37961-107">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="37961-108">Se un utente ha perso il proprio PIN, è possibile reimpostarlo attenendosi alle procedure descritte in [impostare il pin per le conferenze telefoniche con accesso esterno di un utente in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="37961-108">If a user has lost their PIN, you can reset it by following the procedures in [Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span></span>
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="37961-109">Per visualizzare il PIN di un utente nel pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="37961-109">To view a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="37961-110">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="37961-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="37961-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="37961-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="37961-112">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="37961-112">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="37961-113">Utilizzare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="37961-113">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="37961-114">Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="37961-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="37961-115">Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="37961-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="37961-116">(Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:</span><span class="sxs-lookup"><span data-stu-id="37961-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="37961-117">a.</span><span class="sxs-lookup"><span data-stu-id="37961-117">a.</span></span> <span data-ttu-id="37961-118">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="37961-118">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="37961-119">b.</span><span class="sxs-lookup"><span data-stu-id="37961-119">b.</span></span> <span data-ttu-id="37961-120">Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.</span><span class="sxs-lookup"><span data-stu-id="37961-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="37961-121">c.</span><span class="sxs-lookup"><span data-stu-id="37961-121">c.</span></span> <span data-ttu-id="37961-122">Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Non uguale a**).</span><span class="sxs-lookup"><span data-stu-id="37961-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="37961-123">d.</span><span class="sxs-lookup"><span data-stu-id="37961-123">d.</span></span> <span data-ttu-id="37961-124">A seconda della proprietà utente selezionata, immettere i criteri che si desidera utilizzare per filtrare i risultati della ricerca digitandoli oppure facendo clic sulla freccia nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="37961-124">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="37961-125">Per aggiungere ulteriori clausole di ricerca alla query, fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="37961-125">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="37961-126">e.</span><span class="sxs-lookup"><span data-stu-id="37961-126">e.</span></span> <span data-ttu-id="37961-127">Fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="37961-127">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="37961-p108">Se il PIN è bloccato, è necessario sbloccarlo per poterlo impostare. Per sbloccare il PIN, fare clic sull'utente, su **Azione** e quindi su **Sblocca PIN**.</span><span class="sxs-lookup"><span data-stu-id="37961-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="37961-130">Fare clic su un utente nei risultati della ricerca, su **Azione** e quindi su **Visualizza stato PIN**.</span><span class="sxs-lookup"><span data-stu-id="37961-130">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="37961-131">Visualizzazione delle informazioni sul PIN utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="37961-131">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="37961-132">È possibile visualizzare le informazioni sul PIN degli utenti utilizzando il cmdlet Get-CsClientPinInfo.</span><span class="sxs-lookup"><span data-stu-id="37961-132">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="37961-133">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37961-133">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="37961-134">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo del Blog ["Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="37961-134">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="37961-135">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="37961-135">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-user-pin-information"></a><span data-ttu-id="37961-136">Per visualizzazione informazioni sul PIN di un utente</span><span class="sxs-lookup"><span data-stu-id="37961-136">To view user PIN information</span></span>

<span data-ttu-id="37961-137">Per visualizzare le informazioni sul PIN per un utente, digitare un comando simile al seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="37961-137">To view PIN information for a user, type a command similar to the following in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

<span data-ttu-id="37961-138">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="37961-138">That will return information similar to this:</span></span>

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

<span data-ttu-id="37961-139">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="37961-139">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="37961-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37961-140">See also</span></span>

[<span data-ttu-id="37961-141">Impostare il PIN di conferenza telefonica con accesso esterno di un utente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="37961-141">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>](set-a-user-s-dial-in-conferencing-pin.md)
  
[<span data-ttu-id="37961-142">Bloccare o sbloccare il PIN di un utente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="37961-142">Lock or unlock a user PIN in Skype for Business Server</span></span>](lock-or-unlock-a-user-pin.md)
