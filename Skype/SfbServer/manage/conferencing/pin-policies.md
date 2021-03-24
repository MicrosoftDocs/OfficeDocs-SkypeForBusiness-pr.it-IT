---
title: Gestire i criteri PIN per le conferenze telefoniche con accesso esterno in Skype for Business Server
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
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 'Riepilogo: informazioni su come gestire i criteri PIN per le conferenze telefoniche con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: 34b006b54242c25fb9afcd3fc9fd6e6692e9cbd2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096748"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="3f9b6-103">Gestire i criteri PIN per le conferenze telefoniche con accesso esterno in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3f9b6-103">Manage PIN policies for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="3f9b6-104">**Riepilogo:** Informazioni su come gestire i criteri PIN per le conferenze telefoniche con accesso esterno in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-104">**Summary:** Learn how to manage PIN policies for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="3f9b6-105">Gli utenti di Skype for Business Server che dispongono di credenziali di Servizi di dominio Active Directory (AD DS) nell'organizzazione possono partecipare a conferenze telefoniche con accesso esterno come utenti autenticati utilizzando un PIN (Personal Identification Number).</span><span class="sxs-lookup"><span data-stu-id="3f9b6-105">Skype for Business Server users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="3f9b6-106">Il criterio PIN definisce le regole per il funzionamento dei PIN per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-106">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>
  
 <span data-ttu-id="3f9b6-107">Se si desidera utilizzare lo stesso criterio PIN per l'intera organizzazione, è possibile utilizzare il criterio PIN globale e modificarlo in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-107">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="3f9b6-108">Il criterio PIN globale definisce le regole per i PIN delle conferenze telefoniche con accesso esterno a livello della foresta.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-108">The global PIN policy defines the rules for dial-in conferencing PINs at the forest level.</span></span> <span data-ttu-id="3f9b6-109">È possibile modificare il criterio PIN globale, ma non eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-109">You can modify the global PIN policy, but you cannot delete it.</span></span>
  
<span data-ttu-id="3f9b6-110">È possibile creare un nuovo criterio PIN se si desidera un criterio specifico da applicare a un sito o a un determinato gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-110">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span>
  
<span data-ttu-id="3f9b6-111">I criteri PIN si applicano agli utenti partendo dall'ambito più limitato fino all'ambito più esteso.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-111">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="3f9b6-112">Se si assegna a un utente un criterio PIN a livello utente, tali impostazioni avranno la priorità.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-112">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="3f9b6-113">Se invece non si assegna un criterio utente, si applicherà il criterio PIN a livello di sito, se esistente.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-113">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="3f9b6-114">Se non si applica alcun criterio utente o sito, le impostazioni predefinite verranno fornite dal criterio PIN globale.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-114">If no user or site policies apply, global PIN policy provides the default settings.</span></span>
  
## <a name="view-information-about-pin-policies"></a><span data-ttu-id="3f9b6-115">Visualizzare informazioni sui criteri PIN</span><span class="sxs-lookup"><span data-stu-id="3f9b6-115">View information about PIN policies</span></span>

<span data-ttu-id="3f9b6-116">È possibile visualizzare informazioni sui criteri PIN utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-116">You can view information about PIN policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="3f9b6-117">Visualizzare informazioni sui criteri PIN tramite il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3f9b6-117">View information about PIN policies by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="3f9b6-118">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="3f9b6-119">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3f9b6-120">Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-120">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="3f9b6-121">Nella pagina **Criteri PIN** fare clic sul criterio PIN che si desidera visualizzare, fare clic su **Modifica** e quindi su **Mostra dettagli.**</span><span class="sxs-lookup"><span data-stu-id="3f9b6-121">On the **PIN Policy** page, click the PIN policy that you want to view, click **Edit**, and then click **Show details**.</span></span>
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="3f9b6-122">Visualizzare informazioni sui criteri PIN tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="3f9b6-122">View information about PIN policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="3f9b6-123">Per visualizzare informazioni sui criteri PIN, utilizzare il cmdlet **Get-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="3f9b6-123">To view information about PIN policies, use the **Get-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="3f9b6-124">Ad esempio, il comando seguente restituisce informazioni su un singolo criterio PIN con identity site:Redmond:</span><span class="sxs-lookup"><span data-stu-id="3f9b6-124">For example, the following command returns information about a single PIN policy with the Identity site:Redmond:</span></span>
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

<span data-ttu-id="3f9b6-125">Per ulteriori informazioni, inclusa una descrizione completa della sintassi e un elenco di parametri, [vedere Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3f9b6-125">For more information, including a complete syntax description and list of parameters, see [Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-the-global-pin-policy"></a><span data-ttu-id="3f9b6-126">Modificare il criterio PIN globale</span><span class="sxs-lookup"><span data-stu-id="3f9b6-126">Modify the global PIN policy</span></span>

<span data-ttu-id="3f9b6-127">È possibile modificare il criterio PIN globale utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-127">You can modify the global PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="3f9b6-128">Modificare il criterio PIN per le conferenze telefoniche con accesso esterno globale utilizzando il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3f9b6-128">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="3f9b6-129">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="3f9b6-130">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-130">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3f9b6-131">Nella barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-131">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="3f9b6-132">Nella pagina **Criteri PIN** fare clic sul criterio **Globale**, su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-132">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="3f9b6-p105">In **Modifica criteri PIN**, in **Lunghezza minima PIN**, digitare o selezionare la lunghezza minima che si desidera consentire per il PIN. La lunghezza minima predefinita è di cinque cifre.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-p105">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="3f9b6-p106">Per poter specificare il numero massimo di tentativi di accesso prima che un utente venga bloccato, selezionare la casella di controllo **Specifica numero massimo di tentativi di accesso**. Se non si seleziona questa opzione, il numero massimo di tentativi consentiti viene determinato automaticamente in base alla lunghezza del PIN. Per impostazione predefinita, il numero massimo di tentativi viene determinato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="3f9b6-138">Se si seleziona la casella di controllo **Specifica numero massimo di tentativi di accesso**, in **Numero massimo di tentativi di accesso** digitare o selezionare il numero massimo di tentativi di accesso che si desidera consentire.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-138">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="3f9b6-p107">Per impostare una scadenza per i PIN, selezionare la casella di controllo **Abilita scadenza PIN**. Se non si seleziona questa opzione, i PIN non scadranno mai, come da impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="3f9b6-142">Se si seleziona la casella di controllo **Abilita scadenza PIN**, in **Scadenza PIN dopo (giorni)** digitare o selezionare il numero di giorni trascorsi i quali scadranno i PIN.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-142">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="3f9b6-p108">In **Conteggio cronologia PIN** digitare il numero di PIN che deve creare un utente prima che possa riutilizzare un PIN. Per impostazione predefinita, gli utenti possono riutilizzare i loro PIN.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="3f9b6-p109">Per consentire schemi comuni di cifre nei PIN, ad esempio numeri progressivi o gruppi ripetuti di numeri, selezionare la casella di controllo **Consenti formati comuni**. Se non si seleziona questa opzione, saranno consentiti solo schemi complessi di cifre, come da impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3f9b6-148">Per motivi di sicurezza, Microsoft consiglia di non consentire modelli comuni.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-148">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="3f9b6-149">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-149">Click **Commit**.</span></span>
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="3f9b6-150">Modificare il criterio PIN di conferenza telefonica con accesso esterno globale tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="3f9b6-150">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="3f9b6-151">Per modificare il criterio PIN per le conferenze telefoniche con accesso esterno globale, utilizzare il cmdlet **Set-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="3f9b6-151">To modify the global dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="3f9b6-152">Il comando seguente modifica il valore di MinPasswordLength per tutti i criteri PIN configurati per l'utilizzo nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-152">The following command changes the value of the MinPasswordLength for all the PIN policies configured for use in the organization.</span></span> <span data-ttu-id="3f9b6-153">A tale scopo, nel comando viene innanzitutto chiamato il cmdlet **Get-CsPinPolicy** senza alcun parametro per recuperare una raccolta di tutti i criteri per il PIN esistenti.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-153">To do this, the command first calls the **Get-CsPinPolicy** cmdlet without any parameters in order to retrieve a collection of all the existing PIN policies.</span></span> <span data-ttu-id="3f9b6-154">La raccolta viene quindi reindirizzata al cmdlet **Set-CsPinPolicy,** che modifica il valore della proprietà MinPasswordLength per ogni criterio della raccolta:</span><span class="sxs-lookup"><span data-stu-id="3f9b6-154">That collection is then piped to the **Set-CsPinPolicy** cmdlet, which modifies the value of the MinPasswordLength property for each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

<span data-ttu-id="3f9b6-155">Per ulteriori informazioni, inclusa una descrizione completa della sintassi e un elenco di parametri, [vedere Set-CsPinPolicy.](/powershell/module/skype/set-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3f9b6-155">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="create-a-user-or-site-pin-policy"></a><span data-ttu-id="3f9b6-156">Creare un criterio PIN utente o sito</span><span class="sxs-lookup"><span data-stu-id="3f9b6-156">Create a user or site PIN policy</span></span>

<span data-ttu-id="3f9b6-157">È possibile creare un criterio PIN utente o sito utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-157">You can create a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="3f9b6-158">Creare un criterio PIN utente o sito tramite il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3f9b6-158">Create a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="3f9b6-159">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-159">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="3f9b6-160">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-160">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3f9b6-161">Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-161">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="3f9b6-162">Nella pagina **Criteri PIN** fare clic su **Nuovo** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f9b6-162">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="3f9b6-p111">Per creare criteri a livello di utente fare clic su **Criteri utente**. In **Nuovi criteri PIN** digitare un nome descrittivo dei criteri in **Nome**.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-p111">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="3f9b6-p112">Per creare criteri a livello di sito, fare clic su **Criteri sito**. Nel campo di ricerca **Seleziona un sito** digitare il nome del sito per cui si desidera creare i criteri, per intero o in parte. Fare clic sul sito desiderato nell'elenco dei siti e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-p112">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="3f9b6-168">Nel campo **Descrizione** digitare una descrizione per i criteri per il PIN.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-168">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="3f9b6-p113">Nel campo **Lunghezza minima PIN** digitare o selezionare la lunghezza minima che si desidera consentire per il PIN. La lunghezza minima predefinita è di cinque cifre.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-p113">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="3f9b6-p114">Per poter specificare il numero massimo di tentativi di accesso prima che un utente venga bloccato, selezionare la casella di controllo **Specifica numero massimo di tentativi di accesso**. Se non si seleziona questa opzione, il numero massimo di tentativi consentiti viene determinato automaticamente in base alla lunghezza del PIN. Per impostazione predefinita, il numero massimo di tentativi viene determinato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-p114">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="3f9b6-174">Se si seleziona la casella di controllo **Specifica numero massimo di tentativi di accesso**, in **Numero massimo di tentativi di accesso** digitare o selezionare il numero massimo di tentativi di accesso che si desidera consentire.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-174">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="3f9b6-p115">Per impostare una scadenza per i PIN, selezionare la casella di controllo **Abilita scadenza PIN**. Se non si seleziona questa opzione, i PIN non scadranno mai, come da impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-p115">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="3f9b6-178">Se si seleziona la casella di controllo **Abilita scadenza PIN**, in **Scadenza PIN dopo (giorni)** digitare o selezionare il numero di giorni trascorsi i quali scadranno i PIN.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-178">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="3f9b6-p116">In **Conteggio cronologia PIN** digitare il numero di PIN che deve creare un utente prima che possa riutilizzare un PIN. Per impostazione predefinita, gli utenti possono riutilizzare i loro PIN.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-p116">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="3f9b6-p117">Per consentire schemi comuni di cifre nei PIN, ad esempio numeri progressivi o gruppi ripetuti di numeri, selezionare la casella di controllo **Consenti formati comuni**. Se non si seleziona questa opzione, saranno consentiti solo schemi complessi di cifre, come da impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-p117">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3f9b6-184">Per motivi di sicurezza, Microsoft consiglia di non consentire modelli comuni.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-184">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="3f9b6-185">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-185">Click **Commit**.</span></span>
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="3f9b6-186">Creare un criterio PIN utente o sito tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="3f9b6-186">Create a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="3f9b6-187">Per creare un criterio PIN utente o sito, utilizzare il cmdlet **New-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="3f9b6-187">To create a user or site PIN policy, use the **New-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="3f9b6-188">Il comando seguente crea un nuovo criterio PIN con Identity site:Redmond.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-188">The following command creates a new PIN policy with the Identity site:Redmond.</span></span> <span data-ttu-id="3f9b6-189">Questo comando include un solo parametro facoltativo, MinPasswordLength, utilizzato per impostare la proprietà MinPasswordLength su 7.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-189">This command includes just one optional parameter, MinPasswordLength, which is used to set the MinPasswordLength property to 7.</span></span> <span data-ttu-id="3f9b6-190">Tutte le altre proprietà dei criteri verranno configurate utilizzando i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-190">All the remaining policy properties will be configured using the default values.</span></span>
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 <span data-ttu-id="3f9b6-191">Per ulteriori informazioni, inclusa una descrizione completa della sintassi e un elenco di parametri, [vedere New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3f9b6-191">For more information, including a complete syntax description and list of parameters, see [New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-a-user-or-site-pin-policy"></a><span data-ttu-id="3f9b6-192">Modificare un criterio PIN utente o sito</span><span class="sxs-lookup"><span data-stu-id="3f9b6-192">Modify a user or site PIN policy</span></span>

<span data-ttu-id="3f9b6-193">È possibile modificare i criteri PIN di un utente o di un sito utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-193">You can modify a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="3f9b6-194">Modificare i criteri PIN di un utente o di un sito tramite il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3f9b6-194">Modify a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="3f9b6-195">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="3f9b6-196">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-196">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3f9b6-197">Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-197">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="3f9b6-198">Nella pagina **Criteri PIN** fare clic sui criteri per il PIN che si desidera modificare, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-198">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="3f9b6-199">In **Modifica criteri PIN** modificare le impostazioni dei criteri nel modo desiderato, con l'eccezione del nome che non è modificabile.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-199">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>
    
6. <span data-ttu-id="3f9b6-200">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-200">Click **Commit**.</span></span>
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="3f9b6-201">Modificare i criteri PIN di un utente o di un sito tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="3f9b6-201">Modify a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="3f9b6-202">Per modificare il criterio PIN per le conferenze telefoniche con accesso esterno, utilizzare il cmdlet **Set-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="3f9b6-202">To modify the dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="3f9b6-203">Il comando seguente modifica il criterio PIN assegnato al sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-203">The following command modifies the PIN policy assigned to the Redmond site.</span></span> <span data-ttu-id="3f9b6-204">In questo caso, il comando modifica il valore della proprietà MinPasswordLength su 10. ciò significa che i nuovi PIN doranno contenere almeno 10 cifre:</span><span class="sxs-lookup"><span data-stu-id="3f9b6-204">In this case, the command changes the value of the MinPasswordLength property to 10; that means that new PINs will have to contain at least 10 digits:</span></span>
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

<span data-ttu-id="3f9b6-205">Per ulteriori informazioni, inclusa una descrizione completa della sintassi e un elenco di parametri, [vedere Set-CsPinPolicy.](/powershell/module/skype/set-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3f9b6-205">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="delete-a-user-or-site-pin-policy"></a><span data-ttu-id="3f9b6-206">Eliminare un criterio PIN utente o sito</span><span class="sxs-lookup"><span data-stu-id="3f9b6-206">Delete a user or site PIN policy</span></span>

<span data-ttu-id="3f9b6-207">È possibile eliminare un criterio PIN utente o sito utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-207">You can delete a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="3f9b6-208">Eliminare un criterio PIN di un utente o di un sito tramite il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3f9b6-208">Delete a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="3f9b6-209">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-209">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="3f9b6-210">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-210">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3f9b6-211">Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-211">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="3f9b6-212">Nella pagina **Criteri PIN** fare clic sul criterio PIN che si desidera modificare, fare clic su **Modifica** e quindi su **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="3f9b6-212">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Delete**.</span></span>
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="3f9b6-213">Eliminare un criterio PIN utente o sito tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="3f9b6-213">Delete a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="3f9b6-214">Per eliminare un criterio PIN utente o sito, utilizzare il cmdlet **Remove-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="3f9b6-214">To delete a user or site PIN policy, use the **Remove-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="3f9b6-215">Il comando seguente rimuove tutti i criteri PIN configurati nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="3f9b6-215">The following command removes all the PIN policies that have been configured at the site scope.</span></span> <span data-ttu-id="3f9b6-216">A tale scopo, utilizzare il cmdlet **Get-CsPinPolicy,** insieme al parametro Filter, per restituire una raccolta di tutti i criteri la cui identità inizia con i caratteri "site:".</span><span class="sxs-lookup"><span data-stu-id="3f9b6-216">To do this, use the **Get-CsPinPolicy** cmdlet, along with the Filter parameter, to return a collection of all the policies that have an Identity that begins with the characters "site:".</span></span> <span data-ttu-id="3f9b6-217">Questa raccolta viene quindi reindirizzata al cmdlet **Remove-CsPinPolicy,** che elimina ogni criterio nella raccolta:</span><span class="sxs-lookup"><span data-stu-id="3f9b6-217">This collection is then piped to the **Remove-CsPinPolicy** cmdlet, which deletes each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

<span data-ttu-id="3f9b6-218">Per ulteriori informazioni, inclusa una descrizione completa della sintassi e un elenco di parametri, [vedere Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3f9b6-218">For more information, including a complete syntax description and list of parameters, see [Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span></span>
