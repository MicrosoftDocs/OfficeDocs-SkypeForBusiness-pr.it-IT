---
title: Visualizzare le informazioni sul PIN utente in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Riepilogo: visualizzare le informazioni sul PIN utente in Skype for Business Server.'
ms.openlocfilehash: e0a74d980be4c77c5fe92f9e0d871f238a7271f5
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991941"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a><span data-ttu-id="38975-103">Visualizzare le informazioni sul PIN utente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="38975-103">View user PIN information in Skype for Business Server</span></span>
 
<span data-ttu-id="38975-104">**Riepilogo:** Visualizzare le informazioni sui PIN utente in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="38975-104">**Summary:** View user PIN information in Skype for Business Server.</span></span>
  
<span data-ttu-id="38975-105">Per partecipare a una conferenza telefonica con accesso esterno come utente autenticato, un utente di Skype for Business Server con credenziali di Active Directory Domain Services (AD DS) richiede un PIN (Personal Identification Number).</span><span class="sxs-lookup"><span data-stu-id="38975-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="38975-106">È possibile visualizzare le informazioni sul PIN di un utente dal pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="38975-106">You can view a user's PIN information from Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="38975-107">È possibile visualizzare le informazioni sullo stato del PIN, ad esempio se il PIN è stato impostato o quando il PIN è stato modificato per l'ultima volta, ma non è possibile visualizzare il PIN corrente guardando lo stato del PIN.</span><span class="sxs-lookup"><span data-stu-id="38975-107">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="38975-108">Se un utente ha perso il PIN, è possibile reimpostarlo seguendo le procedure descritte in [impostare un PIN per i servizi di conferenza telefonica con accesso esterno di un utente in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="38975-108">If a user has lost their PIN, you can reset it by following the procedures in [Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span></span>
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="38975-109">Per visualizzare il PIN di un utente nel pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="38975-109">To view a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="38975-110">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="38975-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="38975-111">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="38975-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="38975-112">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="38975-112">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="38975-113">Usare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="38975-113">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="38975-114">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="38975-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="38975-115">Se si ha una query salvata, fare clic sull'icona **Apri query** , usare la finestra di dialogo **Apri** per recuperare la query (un file con estensione USF) e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="38975-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="38975-116">Opzionale Specificare altri criteri di ricerca per restringere i risultati:</span><span class="sxs-lookup"><span data-stu-id="38975-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="38975-117">un.</span><span class="sxs-lookup"><span data-stu-id="38975-117">a.</span></span> <span data-ttu-id="38975-118">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="38975-118">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="38975-119">b.</span><span class="sxs-lookup"><span data-stu-id="38975-119">b.</span></span> <span data-ttu-id="38975-120">Immettere la proprietà User digitando o facendo clic sulla freccia nell'elenco a discesa per selezionare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="38975-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="38975-121">c.</span><span class="sxs-lookup"><span data-stu-id="38975-121">c.</span></span> <span data-ttu-id="38975-122">Nell'elenco **a discesa uguale a** fare clic sull'operatore, ad esempio **uguale** a o diverso **da**.</span><span class="sxs-lookup"><span data-stu-id="38975-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="38975-123">3D.</span><span class="sxs-lookup"><span data-stu-id="38975-123">d.</span></span> <span data-ttu-id="38975-124">A seconda della proprietà utente selezionata, immettere i criteri da usare per filtrare i risultati della ricerca digitando o facendo clic sulla freccia nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="38975-124">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="38975-125">Per aggiungere altre clausole di ricerca alla query, fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="38975-125">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="38975-126">e.</span><span class="sxs-lookup"><span data-stu-id="38975-126">e.</span></span> <span data-ttu-id="38975-127">Fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="38975-127">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="38975-128">Se il PIN è bloccato, è necessario sbloccare il PIN prima di poterlo impostare.</span><span class="sxs-lookup"><span data-stu-id="38975-128">If the PIN is locked, you must unlock the PIN before you can set it.</span></span> <span data-ttu-id="38975-129">Per sbloccare il PIN, fare clic sull'utente, fare clic su **azione**e quindi su **Sblocca PIN**.</span><span class="sxs-lookup"><span data-stu-id="38975-129">To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="38975-130">Fare clic su un utente nei risultati della ricerca, fare clic su **azione**e quindi su **Visualizza stato PIN**.</span><span class="sxs-lookup"><span data-stu-id="38975-130">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="38975-131">Visualizzazione delle informazioni sui PIN utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="38975-131">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="38975-132">Puoi visualizzare le informazioni sul PIN utente usando il cmdlet Get-CsClientPinInfo.</span><span class="sxs-lookup"><span data-stu-id="38975-132">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="38975-133">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38975-133">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="38975-134">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="38975-134">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="38975-135">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="38975-135">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-user-pin-information"></a><span data-ttu-id="38975-136">Per visualizzare le informazioni sul PIN dell'utente</span><span class="sxs-lookup"><span data-stu-id="38975-136">To view user PIN information</span></span>

<span data-ttu-id="38975-137">Per visualizzare le informazioni sul PIN per un utente, digitare un comando simile a quello seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="38975-137">To view PIN information for a user, type a command similar to the following in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

<span data-ttu-id="38975-138">Questo restituirà informazioni simili alla seguente:</span><span class="sxs-lookup"><span data-stu-id="38975-138">That will return information similar to this:</span></span>

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

<span data-ttu-id="38975-139">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="38975-139">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="38975-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38975-140">See also</span></span>

[<span data-ttu-id="38975-141">Impostare il PIN di conferenza telefonica con accesso esterno di un utente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="38975-141">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>](set-a-user-s-dial-in-conferencing-pin.md)
  
[<span data-ttu-id="38975-142">Bloccare o sbloccare un PIN utente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="38975-142">Lock or unlock a user PIN in Skype for Business Server</span></span>](lock-or-unlock-a-user-pin.md)
