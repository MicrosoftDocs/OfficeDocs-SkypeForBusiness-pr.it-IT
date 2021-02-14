---
title: 'Gestire i numeri di accesso per le conferenze telefoniche con accesso esterno in Skype for Business Server '
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
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Riepilogo: informazioni su come gestire i numeri di accesso alle conferenze telefoniche con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: 868d757edc6728254c1ab09d22398cd3dc60901b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806486"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a><span data-ttu-id="8cf06-103">Gestire i numeri di accesso per le conferenze telefoniche con accesso esterno in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8cf06-103">Manage dial-in conferencing access numbers in Skype for Business Server</span></span>
 
<span data-ttu-id="8cf06-104">**Riepilogo:** Informazioni su come gestire i numeri di accesso alle conferenze telefoniche con accesso esterno in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8cf06-104">**Summary:** Learn how to manage dial-in conferencing access numbers in Skype for Business Server.</span></span>
  
<span data-ttu-id="8cf06-105">Quando si distribuiscono conferenze telefoniche con accesso esterno, è necessario configurare numeri di telefono che gli utenti possono comporre dalla rete PSTN (Public Switched Telephone Network) per partecipare alla parte audio delle conferenze.</span><span class="sxs-lookup"><span data-stu-id="8cf06-105">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="8cf06-106">Questi numeri di accesso esterno vengono visualizzati negli inviti alle riunioni e nella pagina Web Impostazioni conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="8cf06-106">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span> 
  
<span data-ttu-id="8cf06-107">In questo argomento viene descritto come visualizzare, modificare o eliminare i numeri di accesso alle conferenze telefoniche con accesso esterno esistenti.</span><span class="sxs-lookup"><span data-stu-id="8cf06-107">This topic describes how to view, modify, or delete existing dial-in conferencing access numbers.</span></span> <span data-ttu-id="8cf06-108">Per ulteriori informazioni su come creare i numeri di accesso esterno iniziali, vedere Configurare le conferenze telefoniche con accesso [esterno in Skype for Business Server.](../../deploy/deploy-conferencing/dial-in-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="8cf06-108">For more information about how to create initial dial-in access numbers, see [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span></span>
  
## <a name="view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="8cf06-109">Visualizzare i numeri di accesso per le conferenze telefoniche con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="8cf06-109">View dial-in conferencing access numbers</span></span>

<span data-ttu-id="8cf06-110">È possibile visualizzare i numeri di accesso alle conferenze telefoniche con accesso esterno utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8cf06-110">You can view dial-in conferencing access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8cf06-111">Visualizzare i numeri di accesso esterno utilizzando il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8cf06-111">View dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8cf06-112">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8cf06-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="8cf06-113">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8cf06-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8cf06-114">Nella barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Numero di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="8cf06-114">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="8cf06-115">Nella pagina **Numero di accesso esterno** fare clic sul numero di accesso che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="8cf06-115">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>
    
5. <span data-ttu-id="8cf06-116">In **Modifica** selezionare la **casella di controllo** Mostra dettagli.</span><span class="sxs-lookup"><span data-stu-id="8cf06-116">In **Edit**, select the **Show Details** check box.</span></span>
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8cf06-117">Visualizzare i numeri di accesso esterno tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8cf06-117">View dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="8cf06-118">Per visualizzare informazioni sui numeri di accesso esterno, utilizzare il cmdlet **Get-CsDialInConferencingAccessNumber.**</span><span class="sxs-lookup"><span data-stu-id="8cf06-118">To view information about dial-in access numbers, use the **Get-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="8cf06-119">Il comando seguente restituisce una raccolta di tutti i numeri di accesso per le conferenze telefoniche con accesso esterno configurati per l'utilizzo nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="8cf06-119">The following command returns a collection of all the dial-in conferencing access numbers configured for use in the organization:</span></span> 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

<span data-ttu-id="8cf06-120">Di seguito è riportato un esempio del tipo di informazioni restituite:</span><span class="sxs-lookup"><span data-stu-id="8cf06-120">The following is an example of the type of information returned:</span></span>
  
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

<span data-ttu-id="8cf06-121">Per ulteriori informazioni, vedere [Get-CsDialInConferencingAccessNumber.](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8cf06-121">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="modify-dial-in-conferencing-access-numbers"></a><span data-ttu-id="8cf06-122">Modificare i numeri di accesso per le conferenze telefoniche con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="8cf06-122">Modify dial-in conferencing access numbers</span></span>

<span data-ttu-id="8cf06-123">È possibile modificare i numeri di accesso esterno utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8cf06-123">You can modify dial-in access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8cf06-124">Modificare i numeri di accesso esterno utilizzando il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8cf06-124">Modify dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8cf06-125">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8cf06-125">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="8cf06-126">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8cf06-126">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8cf06-127">Nella barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Numero di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="8cf06-127">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="8cf06-128">Nella pagina **Numero di accesso** esterno fare clic su uno dei numeri di accesso esterno nell'elenco, fare clic su Modifica e quindi su Mostra **dettagli.** </span><span class="sxs-lookup"><span data-stu-id="8cf06-128">On the **Dial-in Access Number** page, click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8cf06-p103">Se si utilizza il campo di ricerca per cercare il contenuto di una colonna nell'elenco dei numeri di accesso esterno, i risultati ottenuti potrebbero non essere quelli previsti. Ordinare invece l'elenco in base alla colonna a cui si è interessati per identificare il numero di accesso esterno da visualizzare o modificare.</span><span class="sxs-lookup"><span data-stu-id="8cf06-p103">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="8cf06-131">In **Numero visualizzato** digitare il numero di telefono che gli utenti della rete PSTN (Public Switched Telephone Network) devono comporre per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="8cf06-131">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> 
    
    <span data-ttu-id="8cf06-132">Questo numero viene visualizzato negli inviti alle riunioni e nella pagina Web Impostazioni conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="8cf06-132">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="8cf06-133">In **Nome visualizzato** digitare una descrizione per il numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="8cf06-133">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="8cf06-134">Questo è il nome associato al numero di accesso remoto nei risultati della ricerca di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="8cf06-134">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span>
    
    <span data-ttu-id="8cf06-135">Questo nome viene visualizzato nel client quando un utente chiama il numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="8cf06-135">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="8cf06-p105">In **URI linea** digitare il numero E.164 del numero di accesso esterno nel formato URI TEL, preceduto dal simbolo + e senza utilizzare spazi. Ad esempio, tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="8cf06-p105">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8cf06-138">Non è possibile riutilizzare lo stesso URI linea per un altro numero di accesso per conferenze con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="8cf06-138">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="8cf06-139">In **URI SIP** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8cf06-139">In **SIP URI**, do the following:</span></span>
    
   <span data-ttu-id="8cf06-140">Nella casella di testo digitare un URI SIP univoco per il numero di accesso per conferenze con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="8cf06-140">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="8cf06-141">Questo URI SIP viene visualizzato in varie posizioni, tra cui, ad esempio, i messaggi di notifica delle chiamate e le versioni precedenti dei client Lync.</span><span class="sxs-lookup"><span data-stu-id="8cf06-141">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8cf06-p107">Non è possibile riutilizzare lo stesso URI SIP per un altro numero di accesso per conferenze con accesso esterno. L'URI SIP non può essere modificato dopo che il numero di accesso è stato creato. L'unico modo per modificare l'URI SIP è quello di eliminare e ricreare il numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="8cf06-p107">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   <span data-ttu-id="8cf06-145">Nella casella di riepilogo a discesa fare clic sul dominio dell'applicazione Operatore Conferenza che supporta questo numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="8cf06-145">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="8cf06-146">In **Pool** fare clic sul pool che esegue l'istanza di Operatore Conferenza che supporta il numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="8cf06-146">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8cf06-147">Se è necessario modificare il pool dopo avere creato il numero di accesso, utilizzare il cmdlet **Move-CsApplicationEndpoint** oppure eliminare e ricreare il numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="8cf06-147">If you need to change the pool after you create the access number, you must use the **Move-CsApplicationEndpoint** cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="8cf06-148">In **Lingua principale** fare clic sulla lingua in cui verranno riprodotte le richieste per il numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="8cf06-148">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="8cf06-p108">La lingua principale è la lingua utilizzata da Operatore Conferenza per rispondere alla chiamata. Le lingue supportate vengono visualizzate insieme a ogni numero di telefono di accesso nella pagina Web Impostazioni conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="8cf06-p108">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="8cf06-151">(Facoltativo) In **Lingue secondarie (massimo quattro)** fare clic su **Aggiungi**, selezionare una o più lingue aggiuntive che si desidera supportare per i chiamanti al numero di accesso esterno e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8cf06-151">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="8cf06-p109">È possibile selezionare fino a quattro lingue secondarie per ogni numero di accesso esterno. Gli utenti possono selezionare una lingua secondaria prima di immettere l'ID conferenza quando chiamano per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="8cf06-p109">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="8cf06-154">Per aggiungere un'area per il numero di accesso remoto, in Aree associate fare clic su **Aggiungi,** fare clic su una o più aree associate ai dial plan per il numero di accesso remoto e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="8cf06-154">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="8cf06-155">Per eliminare un'area dal numero di accesso esterno, in **Aree associate** fare clic sull'area desiderata e quindi su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="8cf06-155">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="8cf06-156">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8cf06-156">Click **Commit**.</span></span>
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8cf06-157">Modificare i numeri di accesso esterno tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8cf06-157">Modify dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="8cf06-158">Per modificare i numeri di accesso esterno, utilizzare il cmdlet **Set-CsDialInConferencingAccessNumber.**</span><span class="sxs-lookup"><span data-stu-id="8cf06-158">To modify dial-in access numbers, use the **Set-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="8cf06-159">Il comando seguente modifica la proprietà DisplayName per il numero di accesso alla conferenza telefonica con accesso esterno con l'identità sip:RedmondDialIn@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="8cf06-159">The following command modifies the DisplayName property for the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com.</span></span> <span data-ttu-id="8cf06-160">In questo esempio, il nome visualizzato è impostato su "Redmond Dial-In Access Number":</span><span class="sxs-lookup"><span data-stu-id="8cf06-160">In this example, the display name is set to "Redmond Dial-In Access Number":</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

<span data-ttu-id="8cf06-161">Nell'esempio seguente, il numero di accesso per le conferenze telefoniche con accesso esterno con identità sip:RedmondDialIn@litwareinc.com viene modificato in modo da includere due aree: Redmond e Seattle.</span><span class="sxs-lookup"><span data-stu-id="8cf06-161">In the next example, the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com is modified to include two regions: Redmond and Seattle.</span></span> <span data-ttu-id="8cf06-162">Per ottenere questo risultato, viene utilizzato il parametro Region, seguito dalle due aree (due stringhe separate da virgole).</span><span class="sxs-lookup"><span data-stu-id="8cf06-162">To do this, the Regions parameter is called, followed by the two regions (two string values separated by commas).</span></span> <span data-ttu-id="8cf06-163">Si noti che questo comando avrà esito negativo se le due aree Redmond e Seattle non sono già state definite nei dial plan.</span><span class="sxs-lookup"><span data-stu-id="8cf06-163">Note that this command will fail unless both the Redmond and Seattle regions have already been defined in dial plans.</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

<span data-ttu-id="8cf06-164">Per ulteriori informazioni, vedere [Set-CsDialInConferencingAccessNumber.](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8cf06-164">For more information, see [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="8cf06-165">Eliminare un numero di accesso per le conferenze telefoniche con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="8cf06-165">Delete a dial-in conferencing access number</span></span>

<span data-ttu-id="8cf06-166">È possibile eliminare un numero di accesso per le conferenze telefoniche con accesso esterno utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8cf06-166">You can delete a dial-in conferencing access number by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8cf06-167">Eliminare un numero di accesso per le conferenze telefoniche con accesso esterno utilizzando il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8cf06-167">Delete a dial-in conferencing access number by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="8cf06-168">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8cf06-168">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="8cf06-169">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8cf06-169">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8cf06-170">Nella barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Numero di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="8cf06-170">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="8cf06-171">Nella pagina fare clic sul numero di accesso esterno che si desidera eliminare nell'elenco, fare clic su **Modifica** e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="8cf06-171">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="8cf06-172">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8cf06-172">Click **OK**.</span></span>
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8cf06-173">Eliminare un numero di accesso per le conferenze telefoniche con accesso esterno tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8cf06-173">Delete a dial-in conferencing access number by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="8cf06-174">Per eliminare un numero di accesso per le conferenze telefoniche con accesso esterno, utilizzare **Remove-CsDialInConferencingAccessNumber.**</span><span class="sxs-lookup"><span data-stu-id="8cf06-174">To delete a dial-in conferencing access number, use the **Remove-CsDialInConferencingAccessNumber**.</span></span>
  
<span data-ttu-id="8cf06-175">Il comando seguente consente di eliminare il numero di accesso per le conferenze telefoniche con identità sip:RedmondDialInAccess@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="8cf06-175">The following command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

<span data-ttu-id="8cf06-176">Il comando successivo elimina tutti i numeri di accesso per le conferenze telefoniche con accesso esterno associati all'area nord-occidentale:</span><span class="sxs-lookup"><span data-stu-id="8cf06-176">The next command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="8cf06-177">Il comando successivo elimina tutti i numeri di accesso alle conferenze telefoniche con accesso esterno in cui l'italiano è la lingua principale:</span><span class="sxs-lookup"><span data-stu-id="8cf06-177">The next command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="8cf06-178">Per ulteriori informazioni, [vedere Remove-CsDialInConferencingAccessNumber.](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8cf06-178">For more information, see [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  

