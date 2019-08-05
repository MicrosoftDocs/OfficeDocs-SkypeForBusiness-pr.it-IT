---
title: Gestire i criteri PIN per i servizi di conferenza telefonica con accesso esterno in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 'Riepilogo: informazioni su come gestire i criteri PIN per i servizi di conferenza telefonica con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: a8db6fc0398d2f577afe54ab2289c3122adcb197
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188924"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="94b6c-103">Gestire i criteri PIN per i servizi di conferenza telefonica con accesso esterno in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="94b6c-103">Manage PIN policies for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="94b6c-104">**Riepilogo:** Informazioni su come gestire i criteri PIN per i servizi di conferenza telefonica con accesso esterno in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="94b6c-104">**Summary:** Learn how to manage PIN policies for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="94b6c-105">Gli utenti di Skype for Business Server che hanno credenziali Active Directory Domain Services (AD DS) nell'organizzazione possono partecipare a conferenze telefoniche con accesso esterno come utenti autenticati usando un PIN (Personal Identification Number).</span><span class="sxs-lookup"><span data-stu-id="94b6c-105">Skype for Business Server users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="94b6c-106">I criteri PIN definiscono le regole per il funzionamento dei pin di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="94b6c-106">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>
  
 <span data-ttu-id="94b6c-107">Se si vogliono usare gli stessi criteri PIN per l'intera organizzazione, è possibile usare il criterio PIN globale e modificarlo in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="94b6c-107">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="94b6c-108">Il criterio PIN globale definisce le regole per i pin di conferenza telefonica con accesso esterno a livello di foresta.</span><span class="sxs-lookup"><span data-stu-id="94b6c-108">The global PIN policy defines the rules for dial-in conferencing PINs at the forest level.</span></span> <span data-ttu-id="94b6c-109">È possibile modificare il criterio PIN globale, ma non è possibile eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="94b6c-109">You can modify the global PIN policy, but you cannot delete it.</span></span>
  
<span data-ttu-id="94b6c-110">Se si vuole applicare un criterio specifico a un sito o a un determinato gruppo di utenti, è possibile creare un nuovo criterio PIN.</span><span class="sxs-lookup"><span data-stu-id="94b6c-110">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span>
  
<span data-ttu-id="94b6c-111">I criteri PIN si applicano agli utenti dall'ambito più limitato all'ambito più ampio.</span><span class="sxs-lookup"><span data-stu-id="94b6c-111">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="94b6c-112">Se si assegna un criterio PIN a livello di utente a un utente, queste impostazioni hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="94b6c-112">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="94b6c-113">Se non si assegna un criterio utente, il criterio PIN a livello di sito si applica, se esistente.</span><span class="sxs-lookup"><span data-stu-id="94b6c-113">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="94b6c-114">Se non si applicano criteri per l'utente o il sito, il criterio PIN globale fornisce le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="94b6c-114">If no user or site policies apply, global PIN policy provides the default settings.</span></span>
  
## <a name="view-information-about-pin-policies"></a><span data-ttu-id="94b6c-115">Visualizzare le informazioni sui criteri PIN</span><span class="sxs-lookup"><span data-stu-id="94b6c-115">View information about PIN policies</span></span>

<span data-ttu-id="94b6c-116">Puoi visualizzare le informazioni sui criteri PIN usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="94b6c-116">You can view information about PIN policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="94b6c-117">Visualizzare le informazioni sui criteri PIN tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="94b6c-117">View information about PIN policies by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="94b6c-118">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .</span><span class="sxs-lookup"><span data-stu-id="94b6c-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="94b6c-119">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="94b6c-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="94b6c-120">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="94b6c-120">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="94b6c-121">Nella pagina **criteri PIN** fare clic sul criterio PIN che si vuole visualizzare, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="94b6c-121">On the **PIN Policy** page, click the PIN policy that you want to view, click **Edit**, and then click **Show details**.</span></span>
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="94b6c-122">Visualizzare le informazioni sui criteri PIN usando Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="94b6c-122">View information about PIN policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="94b6c-123">Per visualizzare le informazioni sui criteri PIN, usare il cmdlet **Get-CsPinPolicy** .</span><span class="sxs-lookup"><span data-stu-id="94b6c-123">To view information about PIN policies, use the **Get-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="94b6c-124">Ad esempio, il comando seguente restituisce informazioni su un singolo criterio PIN con il sito identità: Redmond:</span><span class="sxs-lookup"><span data-stu-id="94b6c-124">For example, the following command returns information about a single PIN policy with the Identity site:Redmond:</span></span>
  
```
Get-CsPinPolicy -Identity "site:Redmond"
```

<span data-ttu-id="94b6c-125">Per altre informazioni, inclusa una descrizione completa della sintassi e un elenco di parametri, vedere [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="94b6c-125">For more information, including a complete syntax description and list of parameters, see [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-the-global-pin-policy"></a><span data-ttu-id="94b6c-126">Modificare il criterio PIN globale</span><span class="sxs-lookup"><span data-stu-id="94b6c-126">Modify the global PIN policy</span></span>

<span data-ttu-id="94b6c-127">Puoi modificare il criterio PIN globale usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="94b6c-127">You can modify the global PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="94b6c-128">Modificare il criterio PIN di conferenza telefonica con accesso esterno globale usando il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="94b6c-128">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="94b6c-129">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .</span><span class="sxs-lookup"><span data-stu-id="94b6c-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="94b6c-130">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="94b6c-130">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="94b6c-131">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="94b6c-131">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="94b6c-132">Nella pagina **criteri PIN** fare clic sul criterio **globale** , fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="94b6c-132">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="94b6c-133">In **modifica criterio PIN**, in **lunghezza minima PIN**, digitare o selezionare la lunghezza minima del PIN che si vuole consentire.</span><span class="sxs-lookup"><span data-stu-id="94b6c-133">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow.</span></span> <span data-ttu-id="94b6c-134">La lunghezza minima predefinita è di cinque cifre.</span><span class="sxs-lookup"><span data-stu-id="94b6c-134">The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="94b6c-135">Per poter specificare il numero massimo di tentativi di accesso prima che un utente venga bloccato, selezionare la casella di controllo **specifica tentativi di accesso massimo** .</span><span class="sxs-lookup"><span data-stu-id="94b6c-135">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box.</span></span> <span data-ttu-id="94b6c-136">Se non si seleziona questa opzione, il numero massimo di tentativi consentiti viene determinato automaticamente in base alla lunghezza del PIN.</span><span class="sxs-lookup"><span data-stu-id="94b6c-136">If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length.</span></span> <span data-ttu-id="94b6c-137">Per impostazione predefinita, il numero massimo di tentativi viene determinato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="94b6c-137">By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="94b6c-138">Se è stata selezionata la casella di controllo **specifica tentativi di accesso massimo** , in **tentativi di accesso massimo**digitare o selezionare il numero massimo di tentativi di accesso che si desidera consentire.</span><span class="sxs-lookup"><span data-stu-id="94b6c-138">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="94b6c-139">Per impostare i pin in scadenza, selezionare la casella di controllo **Abilita scadenza PIN** .</span><span class="sxs-lookup"><span data-stu-id="94b6c-139">To have PINs expire, select the **Enable PIN expiration** check box.</span></span> <span data-ttu-id="94b6c-140">Se non si seleziona questa opzione, i pin non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="94b6c-140">If you do not select this option, PINs will never expire.</span></span> <span data-ttu-id="94b6c-141">Per impostazione predefinita, i pin non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="94b6c-141">By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="94b6c-142">Se è stata selezionata la casella di controllo **Abilita scadenza PIN** , in **PIN scade dopo (giorni)** digitare o selezionare il numero di giorni dopo il quale i pin scadono.</span><span class="sxs-lookup"><span data-stu-id="94b6c-142">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="94b6c-143">In **conteggio cronologia PIN**Digitare il numero di pin che un utente deve creare prima che l'utente possa riutilizzare un PIN.</span><span class="sxs-lookup"><span data-stu-id="94b6c-143">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN.</span></span> <span data-ttu-id="94b6c-144">Per impostazione predefinita, gli utenti possono riutilizzare i loro PIN.</span><span class="sxs-lookup"><span data-stu-id="94b6c-144">By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="94b6c-145">Per consentire modelli comuni di cifre nei pin, ad esempio numeri sequenziali e set ripetitivi di numeri, selezionare la casella di controllo **Consenti schemi comuni** .</span><span class="sxs-lookup"><span data-stu-id="94b6c-145">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box.</span></span> <span data-ttu-id="94b6c-146">Se non si seleziona questa opzione, sono consentiti solo modelli complessi di cifre.</span><span class="sxs-lookup"><span data-stu-id="94b6c-146">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="94b6c-147">Per impostazione predefinita, sono consentiti solo modelli complessi di cifre.</span><span class="sxs-lookup"><span data-stu-id="94b6c-147">By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="94b6c-148">Per motivi di sicurezza, Microsoft consiglia di non consentire modelli comuni.</span><span class="sxs-lookup"><span data-stu-id="94b6c-148">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="94b6c-149">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="94b6c-149">Click **Commit**.</span></span>
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="94b6c-150">Modificare il criterio PIN di conferenza telefonica con accesso esterno globale usando Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="94b6c-150">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="94b6c-151">Per modificare il criterio PIN per i servizi di conferenza telefonica con accesso esterno globale, usare il cmdlet **Set-CsPinPolicy** .</span><span class="sxs-lookup"><span data-stu-id="94b6c-151">To modify the global dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="94b6c-152">Con il comando seguente viene modificato il valore di MinPasswordLength per tutti i criteri PIN configurati per l'uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="94b6c-152">The following command changes the value of the MinPasswordLength for all the PIN policies configured for use in the organization.</span></span> <span data-ttu-id="94b6c-153">A questo scopo, il comando chiama prima il cmdlet **Get-CsPinPolicy** senza parametri per recuperare una raccolta di tutti i criteri PIN esistenti.</span><span class="sxs-lookup"><span data-stu-id="94b6c-153">To do this, the command first calls the **Get-CsPinPolicy** cmdlet without any parameters in order to retrieve a collection of all the existing PIN policies.</span></span> <span data-ttu-id="94b6c-154">La raccolta viene quindi inviata tramite pipe al cmdlet **Set-CsPinPolicy** , che modifica il valore della proprietà MinPasswordLength per ogni criterio della raccolta:</span><span class="sxs-lookup"><span data-stu-id="94b6c-154">That collection is then piped to the **Set-CsPinPolicy** cmdlet, which modifies the value of the MinPasswordLength property for each policy in the collection:</span></span>
  
```
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

<span data-ttu-id="94b6c-155">Per altre informazioni, ad esempio una descrizione completa della sintassi e un elenco di parametri, vedere [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="94b6c-155">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="create-a-user-or-site-pin-policy"></a><span data-ttu-id="94b6c-156">Creare un criterio PIN per un utente o un sito</span><span class="sxs-lookup"><span data-stu-id="94b6c-156">Create a user or site PIN policy</span></span>

<span data-ttu-id="94b6c-157">È possibile creare un criterio PIN per un utente o un sito usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="94b6c-157">You can create a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="94b6c-158">Creare un criterio PIN per un utente o un sito utilizzando il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="94b6c-158">Create a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="94b6c-159">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .</span><span class="sxs-lookup"><span data-stu-id="94b6c-159">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="94b6c-160">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="94b6c-160">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="94b6c-161">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="94b6c-161">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="94b6c-162">Nella pagina **criteri PIN** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="94b6c-162">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="94b6c-163">Per creare un criterio a livello di utente, fare clic su **criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="94b6c-163">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="94b6c-164">In **nome**digitare un nome che descriva il criterio in **nuovo criterio PIN**.</span><span class="sxs-lookup"><span data-stu-id="94b6c-164">In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="94b6c-165">Per creare un criterio a livello di sito, fare clic su **criteri sito**.</span><span class="sxs-lookup"><span data-stu-id="94b6c-165">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="94b6c-166">Nel campo **Seleziona ricerca sito** digitare tutto o parte del nome del sito per cui si vuole creare un criterio.</span><span class="sxs-lookup"><span data-stu-id="94b6c-166">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="94b6c-167">Nell'elenco dei siti fare clic sul sito desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="94b6c-167">In the list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="94b6c-168">Nel campo **Descrizione** Digitare una descrizione del criterio PIN.</span><span class="sxs-lookup"><span data-stu-id="94b6c-168">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="94b6c-169">Nel campo **lunghezza minima PIN** Digitare o selezionare la lunghezza minima del PIN che si vuole consentire.</span><span class="sxs-lookup"><span data-stu-id="94b6c-169">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow.</span></span> <span data-ttu-id="94b6c-170">La lunghezza minima predefinita è di cinque cifre.</span><span class="sxs-lookup"><span data-stu-id="94b6c-170">The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="94b6c-171">Per poter specificare il numero massimo di tentativi di accesso prima che un utente venga bloccato, selezionare la casella di controllo **specifica tentativi di accesso massimo** .</span><span class="sxs-lookup"><span data-stu-id="94b6c-171">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box.</span></span> <span data-ttu-id="94b6c-172">Se non si seleziona questa opzione, il numero massimo di tentativi consentiti viene determinato automaticamente in base alla lunghezza del PIN.</span><span class="sxs-lookup"><span data-stu-id="94b6c-172">If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length.</span></span> <span data-ttu-id="94b6c-173">Per impostazione predefinita, il numero massimo di tentativi viene determinato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="94b6c-173">By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="94b6c-174">Se è stata selezionata la casella di controllo **specifica tentativi di accesso massimo** , in **tentativi di accesso massimo**digitare o selezionare il numero massimo di tentativi di accesso che si desidera consentire.</span><span class="sxs-lookup"><span data-stu-id="94b6c-174">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="94b6c-175">Per impostare i pin in scadenza, selezionare la casella di controllo **Abilita scadenza PIN** .</span><span class="sxs-lookup"><span data-stu-id="94b6c-175">To have PINs expire, select the **Enable PIN expiration** check box.</span></span> <span data-ttu-id="94b6c-176">Se non si seleziona questa opzione, i pin non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="94b6c-176">If you do not select this option, PINs will never expire.</span></span> <span data-ttu-id="94b6c-177">Per impostazione predefinita, i pin non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="94b6c-177">By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="94b6c-178">Se è stata selezionata la casella di controllo **Abilita scadenza PIN** , in **PIN scade dopo (giorni)** digitare o selezionare il numero di giorni dopo il quale i pin scadono.</span><span class="sxs-lookup"><span data-stu-id="94b6c-178">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="94b6c-179">In **conteggio cronologia PIN**Digitare il numero di pin che un utente deve creare prima che l'utente possa riutilizzare un PIN.</span><span class="sxs-lookup"><span data-stu-id="94b6c-179">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN.</span></span> <span data-ttu-id="94b6c-180">Per impostazione predefinita, gli utenti possono riutilizzare i loro PIN.</span><span class="sxs-lookup"><span data-stu-id="94b6c-180">By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="94b6c-181">Per consentire modelli comuni di cifre nei pin, ad esempio numeri sequenziali e set ripetitivi di numeri, selezionare la casella di controllo **Consenti schemi comuni** .</span><span class="sxs-lookup"><span data-stu-id="94b6c-181">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box.</span></span> <span data-ttu-id="94b6c-182">Se non si seleziona questa opzione, sono consentiti solo modelli complessi di cifre.</span><span class="sxs-lookup"><span data-stu-id="94b6c-182">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="94b6c-183">Per impostazione predefinita, sono consentiti solo modelli complessi di cifre.</span><span class="sxs-lookup"><span data-stu-id="94b6c-183">By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="94b6c-184">Per motivi di sicurezza, Microsoft consiglia di non consentire modelli comuni.</span><span class="sxs-lookup"><span data-stu-id="94b6c-184">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="94b6c-185">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="94b6c-185">Click **Commit**.</span></span>
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="94b6c-186">Creare un criterio PIN per un utente o un sito utilizzando Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="94b6c-186">Create a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="94b6c-187">Per creare un criterio PIN per un utente o un sito, usare il cmdlet **New-CsPinPolicy** .</span><span class="sxs-lookup"><span data-stu-id="94b6c-187">To create a user or site PIN policy, use the **New-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="94b6c-188">Il comando seguente crea un nuovo criterio PIN con il sito Identity: Redmond.</span><span class="sxs-lookup"><span data-stu-id="94b6c-188">The following command creates a new PIN policy with the Identity site:Redmond.</span></span> <span data-ttu-id="94b6c-189">Questo comando include solo un parametro facoltativo, MinPasswordLength, usato per impostare la proprietà MinPasswordLength su 7.</span><span class="sxs-lookup"><span data-stu-id="94b6c-189">This command includes just one optional parameter, MinPasswordLength, which is used to set the MinPasswordLength property to 7.</span></span> <span data-ttu-id="94b6c-190">Tutte le proprietà dei criteri rimanenti verranno configurate usando i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="94b6c-190">All the remaining policy properties will be configured using the default values.</span></span>
  
```
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 <span data-ttu-id="94b6c-191">Per altre informazioni, inclusa una descrizione completa della sintassi e un elenco di parametri, vedere [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="94b6c-191">For more information, including a complete syntax description and list of parameters, see [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-a-user-or-site-pin-policy"></a><span data-ttu-id="94b6c-192">Modificare un criterio PIN per un utente o un sito</span><span class="sxs-lookup"><span data-stu-id="94b6c-192">Modify a user or site PIN policy</span></span>

<span data-ttu-id="94b6c-193">È possibile modificare i criteri di un utente o di un PIN del sito usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="94b6c-193">You can modify a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="94b6c-194">Modificare i criteri di un utente o di un PIN del sito usando il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="94b6c-194">Modify a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="94b6c-195">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .</span><span class="sxs-lookup"><span data-stu-id="94b6c-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="94b6c-196">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="94b6c-196">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="94b6c-197">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="94b6c-197">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="94b6c-198">Nella pagina **criteri PIN** fare clic sul criterio PIN che si vuole modificare, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="94b6c-198">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="94b6c-199">In **modifica criterio PIN**modificare le impostazioni dei criteri (ad eccezione del nome del criterio, che non può essere modificato).</span><span class="sxs-lookup"><span data-stu-id="94b6c-199">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>
    
6. <span data-ttu-id="94b6c-200">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="94b6c-200">Click **Commit**.</span></span>
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="94b6c-201">Modificare i criteri di un utente o di un PIN del sito utilizzando Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="94b6c-201">Modify a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="94b6c-202">Per modificare il criterio PIN per i servizi di conferenza telefonica con accesso esterno, usare il cmdlet **Set-CsPinPolicy** .</span><span class="sxs-lookup"><span data-stu-id="94b6c-202">To modify the dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="94b6c-203">Il comando seguente modifica il criterio PIN assegnato al sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="94b6c-203">The following command modifies the PIN policy assigned to the Redmond site.</span></span> <span data-ttu-id="94b6c-204">In questo caso, il comando modifica il valore della proprietà MinPasswordLength su 10; Ciò significa che i nuovi PIN dovranno contenere almeno 10 cifre:</span><span class="sxs-lookup"><span data-stu-id="94b6c-204">In this case, the command changes the value of the MinPasswordLength property to 10; that means that new PINs will have to contain at least 10 digits:</span></span>
  
```
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

<span data-ttu-id="94b6c-205">Per altre informazioni, ad esempio una descrizione completa della sintassi e un elenco di parametri, vedere [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="94b6c-205">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="delete-a-user-or-site-pin-policy"></a><span data-ttu-id="94b6c-206">Eliminare un criterio PIN per un utente o un sito</span><span class="sxs-lookup"><span data-stu-id="94b6c-206">Delete a user or site PIN policy</span></span>

<span data-ttu-id="94b6c-207">Puoi eliminare un criterio PIN per un utente o un sito usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="94b6c-207">You can delete a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="94b6c-208">Eliminare un criterio PIN per un utente o un sito utilizzando il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="94b6c-208">Delete a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="94b6c-209">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .</span><span class="sxs-lookup"><span data-stu-id="94b6c-209">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="94b6c-210">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="94b6c-210">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="94b6c-211">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="94b6c-211">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="94b6c-212">Nella pagina **criteri PIN** fare clic sul criterio PIN che si vuole modificare, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="94b6c-212">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Delete**.</span></span>
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="94b6c-213">Eliminare un criterio PIN per un utente o un sito utilizzando Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="94b6c-213">Delete a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="94b6c-214">Per eliminare un criterio PIN per un utente o un sito, usare il cmdlet **Remove-CsPinPolicy** .</span><span class="sxs-lookup"><span data-stu-id="94b6c-214">To delete a user or site PIN policy, use the **Remove-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="94b6c-215">Il comando seguente rimuove tutti i criteri PIN configurati nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="94b6c-215">The following command removes all the PIN policies that have been configured at the site scope.</span></span> <span data-ttu-id="94b6c-216">A questo scopo, usa il cmdlet **Get-CsPinPolicy** insieme al parametro Filter per restituire una raccolta di tutti i criteri con un'identità che inizia con i caratteri "sito:".</span><span class="sxs-lookup"><span data-stu-id="94b6c-216">To do this, use the **Get-CsPinPolicy** cmdlet, along with the Filter parameter, to return a collection of all the policies that have an Identity that begins with the characters "site:".</span></span> <span data-ttu-id="94b6c-217">La raccolta viene quindi inviata tramite pipe al cmdlet **Remove-CsPinPolicy** , che elimina ogni criterio della raccolta:</span><span class="sxs-lookup"><span data-stu-id="94b6c-217">This collection is then piped to the **Remove-CsPinPolicy** cmdlet, which deletes each policy in the collection:</span></span>
  
```
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

<span data-ttu-id="94b6c-218">Per altre informazioni, ad esempio una descrizione completa della sintassi e un elenco di parametri, vedere [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="94b6c-218">For more information, including a complete syntax description and list of parameters, see [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span></span>
  

