---
title: 'Gestire i numeri dei servizi di conferenza telefonica con accesso esterno in Skype for Business Server '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Riepilogo: informazioni su come gestire i numeri dei servizi di conferenza telefonica con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: e41011c4ba06da7f05d8cb1a52717e707cd2f8bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191276"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a><span data-ttu-id="f2718-103">Gestire i numeri dei servizi di conferenza telefonica con accesso esterno in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f2718-103">Manage dial-in conferencing access numbers in Skype for Business Server</span></span>
 
<span data-ttu-id="f2718-104">**Riepilogo:** Informazioni su come gestire i numeri di accesso per i servizi di conferenza telefonica con chiamata in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f2718-104">**Summary:** Learn how to manage dial-in conferencing access numbers in Skype for Business Server.</span></span>
  
<span data-ttu-id="f2718-105">Quando si distribuiscono i servizi di conferenza telefonica con accesso esterno, è necessario configurare i numeri di telefono che gli utenti possono effettuare la chiamata dalla rete PSTN (Public Switched Telephone Network) per partecipare alla parte audio delle conferenze.</span><span class="sxs-lookup"><span data-stu-id="f2718-105">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="f2718-106">I numeri di accesso per le connessioni in ingresso vengono visualizzati negli inviti alle riunioni e nella pagina Web delle impostazioni di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="f2718-106">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span> 
  
<span data-ttu-id="f2718-107">Questo argomento descrive come visualizzare, modificare o eliminare i numeri di accesso ai servizi di conferenza telefonica in ingresso esistenti.</span><span class="sxs-lookup"><span data-stu-id="f2718-107">This topic describes how to view, modify, or delete existing dial-in conferencing access numbers.</span></span> <span data-ttu-id="f2718-108">Per altre informazioni su come creare numeri di accesso per le connessioni telefoniche iniziali, vedere Configurare le conferenze telefoniche con ingresso [esterno in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="f2718-108">For more information about how to create initial dial-in access numbers, see [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span></span>
  
## <a name="view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="f2718-109">Visualizzare i numeri di accesso per i servizi di conferenza telefonica</span><span class="sxs-lookup"><span data-stu-id="f2718-109">View dial-in conferencing access numbers</span></span>

<span data-ttu-id="f2718-110">Puoi visualizzare i numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso usando Skype for Business Server Control Panel o usando Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f2718-110">You can view dial-in conferencing access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f2718-111">Visualizzare i numeri di accesso per le connessioni telefoniche tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f2718-111">View dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f2718-112">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="f2718-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="f2718-113">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f2718-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f2718-114">Sulla barra di spostamento sinistra fare clic su servizi di conferenza e quindi su **numero di accesso** **esterno**.</span><span class="sxs-lookup"><span data-stu-id="f2718-114">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="f2718-115">Nella pagina **numero di accesso** esterno, fare clic sul numero di accesso che si vuole visualizzare.</span><span class="sxs-lookup"><span data-stu-id="f2718-115">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>
    
5. <span data-ttu-id="f2718-116">In **modifica**selezionare la casella di controllo **Mostra dettagli** .</span><span class="sxs-lookup"><span data-stu-id="f2718-116">In **Edit**, select the **Show Details** check box.</span></span>
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f2718-117">Visualizzare i numeri di accesso per le connessioni telefoniche tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f2718-117">View dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="f2718-118">Per visualizzare le informazioni sui numeri di accesso esterno, usare il cmdlet **Get-CsDialInConferencingAccessNumber** .</span><span class="sxs-lookup"><span data-stu-id="f2718-118">To view information about dial-in access numbers, use the **Get-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="f2718-119">Il comando seguente restituisce una raccolta di tutti i numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso configurati per l'uso nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="f2718-119">The following command returns a collection of all the dial-in conferencing access numbers configured for use in the organization:</span></span> 
  
```
Get-CsDialInConferencingAccessNumber
```

<span data-ttu-id="f2718-120">Di seguito è riportato un esempio del tipo di informazioni restituite:</span><span class="sxs-lookup"><span data-stu-id="f2718-120">The following is an example of the type of information returned:</span></span>
  
<pre>
Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                     CN=Application Contacts,CN=RTCService=Services,
                     CN=Configuration,DC=litwareinc,DC=com
PrimaryUri         : sip:testnumber@litwareinc.com
DisplayName        : Test
DisplayNumber      : 1-425-555-1019
LineUri            : tel:+14255551019
PrimaryLanguage    : en-US
SecondaryLanguages : {}
Pool               : atl-cs-001.litwareinc.com
HostingProvider    :
Regions            : {US}
</pre>

<span data-ttu-id="f2718-121">Per altre informazioni, vedere [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f2718-121">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="modify-dial-in-conferencing-access-numbers"></a><span data-ttu-id="f2718-122">Modificare i numeri di accesso per i servizi di conferenza telefonica</span><span class="sxs-lookup"><span data-stu-id="f2718-122">Modify dial-in conferencing access numbers</span></span>

<span data-ttu-id="f2718-123">Puoi modificare i numeri di accesso esterno usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f2718-123">You can modify dial-in access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f2718-124">Modificare i numeri di accesso esterno tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f2718-124">Modify dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f2718-125">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="f2718-125">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="f2718-126">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f2718-126">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f2718-127">Sulla barra di spostamento sinistra fare clic su servizi di conferenza e quindi su **numero di accesso** **esterno**.</span><span class="sxs-lookup"><span data-stu-id="f2718-127">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="f2718-128">Nella pagina **numero di accesso** esterno, fare clic su uno dei numeri di accesso esterno nell'elenco, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f2718-128">On the **Dial-in Access Number** page, click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f2718-129">L'uso del campo di ricerca per cercare il contenuto di una colonna nell'elenco dei numeri di accesso per la chiamata in ingresso potrebbe non restituire i risultati previsti.</span><span class="sxs-lookup"><span data-stu-id="f2718-129">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="f2718-130">Ordinare invece l'elenco in base alla colonna di interesse per identificare il numero di accesso esterno che si vuole visualizzare o modificare.</span><span class="sxs-lookup"><span data-stu-id="f2718-130">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="f2718-131">In **numero di visualizzazione**Digitare il numero di telefono che gli utenti del telefono PSTN (Public Switched Telephone Network) Dial per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="f2718-131">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> 
    
    <span data-ttu-id="f2718-132">Questo numero viene visualizzato negli inviti alle riunioni e nella pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="f2718-132">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="f2718-133">In **nome visualizzato**Digitare una descrizione per il numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="f2718-133">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="f2718-134">Questo è il nome associato al numero di accesso esterno nei risultati della ricerca di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="f2718-134">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span>
    
    <span data-ttu-id="f2718-135">Questo nome viene visualizzato nel client quando un utente chiama il numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="f2718-135">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="f2718-136">In **URI di linea**Digitare il numero e. 164 del numero di accesso esterno in formato Tel URI, incluso il simbolo + prima del numero ed escludendo gli spazi.</span><span class="sxs-lookup"><span data-stu-id="f2718-136">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="f2718-137">Ad esempio, Tel: + 14255550200.</span><span class="sxs-lookup"><span data-stu-id="f2718-137">For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f2718-138">Lo stesso URI di linea non può essere riutilizzato da un altro numero di accesso per i servizi di conferenza telefonica in ingresso.</span><span class="sxs-lookup"><span data-stu-id="f2718-138">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="f2718-139">In **URI SIP**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2718-139">In **SIP URI**, do the following:</span></span>
    
   <span data-ttu-id="f2718-140">Nella casella di testo digitare un URI SIP univoco per questo numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso.</span><span class="sxs-lookup"><span data-stu-id="f2718-140">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="f2718-141">Questo URI SIP viene visualizzato in varie posizioni, inclusi, ma non solo, i messaggi di notifica delle chiamate e le versioni precedenti dei client Lync.</span><span class="sxs-lookup"><span data-stu-id="f2718-141">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f2718-142">Lo stesso URI SIP non può essere riutilizzato da un altro numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso.</span><span class="sxs-lookup"><span data-stu-id="f2718-142">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="f2718-143">L'URI SIP non può essere modificato dopo la creazione del numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="f2718-143">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="f2718-144">L'unico modo per modificare l'URI SIP consiste nell'eliminare e ricreare il numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="f2718-144">The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   <span data-ttu-id="f2718-145">Nella casella di riepilogo a discesa fare clic sul dominio dell'applicazione operatore di conferenza che supporta questo numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="f2718-145">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="f2718-146">In **pool**fare clic sul pool in cui è in esecuzione l'istanza di operatore conferenza che supporta questo numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="f2718-146">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f2718-147">Se è necessario modificare il pool dopo la creazione del numero di accesso, è necessario usare il cmdlet **Move-CsApplicationEndpoint** oppure eliminare e ricreare il numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="f2718-147">If you need to change the pool after you create the access number, you must use the **Move-CsApplicationEndpoint** cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="f2718-148">In **lingua principale**fare clic sulla lingua in cui vengono riprodotti le richieste per questo numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="f2718-148">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="f2718-149">La lingua principale è la lingua che l'operatore di conferenza USA per rispondere alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="f2718-149">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="f2718-150">Le lingue supportate vengono visualizzate accanto a ogni numero di telefono di Access nella pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="f2718-150">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="f2718-151">Opzionale In **lingue secondarie (massimo quattro)** fare clic su **Aggiungi**, selezionare una o più lingue aggiuntive che si desidera supportare per i chiamanti per il numero di accesso esterno e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2718-151">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="f2718-152">È possibile scegliere fino a quattro lingue secondarie per ogni numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="f2718-152">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="f2718-153">Gli utenti possono selezionare una lingua secondaria prima di immettere l'ID conferenza quando effettuano la chiamata a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="f2718-153">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="f2718-154">Per aggiungere un'area geografica per il numero di accesso esterno, fare clic su **Aggiungi**in **aree geografiche associate**, fare clic su una o più aree geografiche associate ai dial plan per questo numero di accesso esterno e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2718-154">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="f2718-155">Per eliminare un'area dal numero di accesso esterno, in **aree geografiche associate**fare clic sull'area che si vuole eliminare e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="f2718-155">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="f2718-156">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f2718-156">Click **Commit**.</span></span>
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f2718-157">Modificare i numeri di accesso esterno con Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f2718-157">Modify dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="f2718-158">Per modificare i numeri di accesso esterno, usare il cmdlet **Set-CsDialInConferencingAccessNumber** .</span><span class="sxs-lookup"><span data-stu-id="f2718-158">To modify dial-in access numbers, use the **Set-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="f2718-159">Il comando seguente modifica la proprietà DisplayName per il numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso con Identity sip:RedmondDialIn@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="f2718-159">The following command modifies the DisplayName property for the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com.</span></span> <span data-ttu-id="f2718-160">In questo esempio, il nome visualizzato è impostato su "numero di accesso telefonico di Redmond":</span><span class="sxs-lookup"><span data-stu-id="f2718-160">In this example, the display name is set to "Redmond Dial-In Access Number":</span></span>
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

<span data-ttu-id="f2718-161">Nell'esempio successivo il numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso con identità sip:RedmondDialIn@litwareinc.com viene modificato per includere due aree geografiche: Redmond e Seattle.</span><span class="sxs-lookup"><span data-stu-id="f2718-161">In the next example, the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com is modified to include two regions: Redmond and Seattle.</span></span> <span data-ttu-id="f2718-162">A questo scopo, viene chiamato il parametro regions, seguito dalle due aree geografiche (due valori stringa separati da virgole).</span><span class="sxs-lookup"><span data-stu-id="f2718-162">To do this, the Regions parameter is called, followed by the two regions (two string values separated by commas).</span></span> <span data-ttu-id="f2718-163">Tieni presente che questo comando avrà esito negativo, a meno che le aree Redmond e Seattle non siano già state definite in dial plan.</span><span class="sxs-lookup"><span data-stu-id="f2718-163">Note that this command will fail unless both the Redmond and Seattle regions have already been defined in dial plans.</span></span>
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

<span data-ttu-id="f2718-164">Per altre informazioni, vedere [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f2718-164">For more information, see [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="f2718-165">Eliminare un numero di accesso ai servizi di conferenza telefonica con chiamata in ingresso</span><span class="sxs-lookup"><span data-stu-id="f2718-165">Delete a dial-in conferencing access number</span></span>

<span data-ttu-id="f2718-166">Puoi eliminare un numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso utilizzando Skype for Business Server Control Panel o usando Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f2718-166">You can delete a dial-in conferencing access number by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f2718-167">Eliminare un numero di conferenza telefonica con accesso esterno tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f2718-167">Delete a dial-in conferencing access number by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="f2718-168">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .</span><span class="sxs-lookup"><span data-stu-id="f2718-168">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="f2718-169">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f2718-169">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f2718-170">Sulla barra di spostamento sinistra fare clic su servizi di conferenza e quindi su **numero di accesso** **esterno**.</span><span class="sxs-lookup"><span data-stu-id="f2718-170">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="f2718-171">Nella pagina fare clic sul numero di accesso esterno che si vuole eliminare nell'elenco, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="f2718-171">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="f2718-172">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2718-172">Click **OK**.</span></span>
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f2718-173">Eliminare un numero di conferenza telefonica con accesso esterno con Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f2718-173">Delete a dial-in conferencing access number by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="f2718-174">Per eliminare un numero di conferenza telefonica con accesso esterno, usare il comando **Remove-CsDialInConferencingAccessNumber**.</span><span class="sxs-lookup"><span data-stu-id="f2718-174">To delete a dial-in conferencing access number, use the **Remove-CsDialInConferencingAccessNumber**.</span></span>
  
<span data-ttu-id="f2718-175">Il comando seguente elimina il numero di accesso per i servizi di conferenza telefonica con chiamata in sip:RedmondDialInAccess@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="f2718-175">The following command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
  
```
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

<span data-ttu-id="f2718-176">Il comando successivo Elimina tutti i numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso associati all'area nord-ovest:</span><span class="sxs-lookup"><span data-stu-id="f2718-176">The next command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
  
```
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="f2718-177">Il comando successivo Elimina tutti i numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso in cui l'italiano è la lingua principale:</span><span class="sxs-lookup"><span data-stu-id="f2718-177">The next command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
  
```
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="f2718-178">Per altre informazioni, vedere [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f2718-178">For more information, see [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  

