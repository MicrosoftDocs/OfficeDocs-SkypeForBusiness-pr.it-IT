---
title: 'Lync Server 2013: abilitare gli utenti per VoIP aziendale'
description: 'Lync Server 2013: abilitare gli utenti per VoIP aziendale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aa8dbbeb507ced5217e517c1608c3a2a9259668
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557652"
---
# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="f7581-103">Abilitare gli utenti per VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7581-103">Enable users for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7581-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f7581-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f7581-105">Dopo aver installato i file per uno o più Mediation Server, configurare il routing delle chiamate in uscita e, facoltativamente, distribuire una o più funzionalità di VoIP aziendale avanzate, è possibile utilizzare le procedure seguenti per consentire a un utente di effettuare chiamate tramite VoIP aziendale:</span><span class="sxs-lookup"><span data-stu-id="f7581-105">After you install files for one or more Mediation Servers, configure outbound call routing, and optionally deploy one or more advanced Enterprise Voice features, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7581-106">Nelle procedure riportate di seguito, solo il primo può essere eseguito utilizzando il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f7581-106">Of the following procedures, only the first can be performed by using Lync Server Control Panel.</span></span> <span data-ttu-id="f7581-107">Per le procedure rimanenti, è possibile utilizzare solo Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f7581-107">For the remaining procedures, you can use only Lync Server Management Shell.</span></span>



</div>

  - <span data-ttu-id="f7581-108">Abilitare l'account utente per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="f7581-108">Enable the user account for Enterprise Voice.</span></span>

  - <span data-ttu-id="f7581-109">(Facoltativo) Assegnare all'account utente criteri vocali specifici dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f7581-109">(Optional) Assign the user account a user-specific voice policy.</span></span>

  - <span data-ttu-id="f7581-110">(Facoltativo) Assegnare all'account utente un dial plan specifico dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f7581-110">(Optional) Assign the user account a user-specific dial plan.</span></span>

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="f7581-111">Per abilitare un account utente per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="f7581-111">To enable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="f7581-112">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="f7581-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f7581-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f7581-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f7581-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f7581-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f7581-115">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="f7581-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="f7581-116">Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account di Gestione account di protezione, dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) di linea dell'account utente da abilitare e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="f7581-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="f7581-117">Nella tabella fare clic sull'account utente che si desidera abilitare per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="f7581-117">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="f7581-118">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="f7581-118">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="f7581-119">Nella pagina **Modifica utente Lync Server**, in **Telefonia**, fare clic su **VoIP aziendale**.</span><span class="sxs-lookup"><span data-stu-id="f7581-119">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="f7581-120">Fare clic su **URI linea** e quindi digitare un numero di telefono normalizzato univoco, ad esempio tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="f7581-120">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>

9.  <span data-ttu-id="f7581-121">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f7581-121">Click **Commit**.</span></span>

<span data-ttu-id="f7581-122">Per completare l'abilitazione di un utente per VoIP aziendale, assicurarsi che all'utente sia assegnato un criterio vocale e un dial plan, indipendentemente dal fatto che sia globale (assegnato per impostazione predefinita) o specifico dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f7581-122">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.</span></span>

<span data-ttu-id="f7581-123">Per impostazione predefinita, tutti gli utenti vengono assegnati a criteri vocali e dial plan globali.</span><span class="sxs-lookup"><span data-stu-id="f7581-123">By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="f7581-124">Se nel sito principale dell'utente esistono criteri vocali o un dial plan a livello di sito, i criteri del sito verranno applicati automaticamente all'utente.</span><span class="sxs-lookup"><span data-stu-id="f7581-124">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="f7581-125">Per applicare criteri vocali o un dial plan per utente, è necessario eseguire i cmdlet **Grant-CsVoicePolicy** e **Grant-CsDialPlan**.</span><span class="sxs-lookup"><span data-stu-id="f7581-125">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="f7581-126">Per informazioni dettagliate, vedere la documentazione di [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="f7581-126">For details, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="voice-policy-assignment"></a><span data-ttu-id="f7581-127">Assegnazione di criteri vocali</span><span class="sxs-lookup"><span data-stu-id="f7581-127">Voice Policy Assignment</span></span>

<span data-ttu-id="f7581-128">I criteri vocali globali e a livello di sito vengono assegnati automaticamente a tutti gli account utente abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="f7581-128">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="f7581-129">È inoltre possibile creare criteri vocali applicabili a utenti o gruppi specifici.</span><span class="sxs-lookup"><span data-stu-id="f7581-129">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="f7581-130">Questi criteri per utente devono essere assegnati esplicitamente agli utenti o ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="f7581-130">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="f7581-131">Se si desidera utilizzare il criterio vocale globale o del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione e continuare con la sezione Assegnazione dial plan più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="f7581-131">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to Dial Plan Assignment section later in this topic.</span></span>

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="f7581-132">Per assegnare criteri vocali specifici dell'utente</span><span class="sxs-lookup"><span data-stu-id="f7581-132">To assign a user-specific voice policy</span></span>

1.  <span data-ttu-id="f7581-133">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="f7581-133">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f7581-134">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f7581-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f7581-135">Per assegnare un criterio vocale esistente a un utente, eseguire quanto segue al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="f7581-135">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="f7581-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f7581-136">For example:</span></span>
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    <span data-ttu-id="f7581-137">In questo esempio, all'utente con il nome visualizzato Bob Kelly viene assegnato il criterio vocale con il nome **VoicePolicyJapan**.</span><span class="sxs-lookup"><span data-stu-id="f7581-137">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>

<span data-ttu-id="f7581-138">Per informazioni dettagliate sull'assegnazione di criteri vocali specifici dell'utente o sull'esecuzione del cmdlet **Grant-CsVoicePolicy** , vedere la documentazione di [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="f7581-138">For details about assigning a user-specific voice policy or about running the **Grant-CsVoicePolicy** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a><span data-ttu-id="f7581-139">Assegnazione di dial plan</span><span class="sxs-lookup"><span data-stu-id="f7581-139">Dial Plan Assignment</span></span>

<span data-ttu-id="f7581-140">Per completare la configurazione degli account per gli utenti di VoIP aziendale o per gli utenti delle conferenze telefoniche con accesso esterno, è necessario che all'utente sia assegnato un dial plan.</span><span class="sxs-lookup"><span data-stu-id="f7581-140">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="f7581-141">Gli account utente utilizzeranno automaticamente il dial plan globale oppure, se disponibile, il dial plan a livello di sito se non si assegna esplicitamente un dial plan per utente.</span><span class="sxs-lookup"><span data-stu-id="f7581-141">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="f7581-142">Se si desidera utilizzare il dial plan globale o del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione.</span><span class="sxs-lookup"><span data-stu-id="f7581-142">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>

<div>

## <a name="to-assign-a-dial-plan"></a><span data-ttu-id="f7581-143">Per assegnare un dial plan</span><span class="sxs-lookup"><span data-stu-id="f7581-143">To assign a dial plan</span></span>

1.  <span data-ttu-id="f7581-144">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="f7581-144">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f7581-145">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f7581-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f7581-146">Per assegnare un dial plan specifico dell'utente, al prompt dei comandi eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f7581-146">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="f7581-147">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f7581-147">For example:</span></span>
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    <span data-ttu-id="f7581-148">In questo esempio, all'utente con il nome visualizzato Bob Kelly viene assegnato il dial plan utente con il nome **DialPlanJapan**.</span><span class="sxs-lookup"><span data-stu-id="f7581-148">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>

<span data-ttu-id="f7581-149">Per informazioni dettagliate sull'assegnazione di un dial plan utente o sull'esecuzione del cmdlet **Grant-CsDialPlan** , vedere la documentazione di [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="f7581-149">For details about assigning a user dial plan or about running the **Grant-CsDialPlan** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f7581-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7581-150">See Also</span></span>


[<span data-ttu-id="f7581-151">Disabilitare un utente per VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7581-151">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

