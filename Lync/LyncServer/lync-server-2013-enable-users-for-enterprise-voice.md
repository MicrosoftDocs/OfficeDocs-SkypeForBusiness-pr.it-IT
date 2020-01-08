---
title: 'Lync Server 2013: consentire agli utenti di VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d94b2ad348bc1d086716deed2beef0dcfbe78e2b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="3037f-102">Consentire agli utenti di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3037f-102">Enable users for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3037f-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3037f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3037f-104">Dopo aver installato i file per uno o più server di mediazione, configurare il routing delle chiamate in uscita e, facoltativamente, distribuire una o più funzionalità vocali avanzate per l'organizzazione, è possibile usare le procedure seguenti per consentire a un utente di effettuare chiamate tramite VoIP aziendale:</span><span class="sxs-lookup"><span data-stu-id="3037f-104">After you install files for one or more Mediation Servers, configure outbound call routing, and optionally deploy one or more advanced Enterprise Voice features, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3037f-105">Delle procedure seguenti, solo il primo può essere eseguito usando il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3037f-105">Of the following procedures, only the first can be performed by using Lync Server Control Panel.</span></span> <span data-ttu-id="3037f-106">Per le procedure rimanenti, è possibile usare solo Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3037f-106">For the remaining procedures, you can use only Lync Server Management Shell.</span></span>



</div>

  - <span data-ttu-id="3037f-107">Abilitare l'account utente per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="3037f-107">Enable the user account for Enterprise Voice.</span></span>

  - <span data-ttu-id="3037f-108">Opzionale Assegnare l'account utente a un criterio vocale specifico per l'utente.</span><span class="sxs-lookup"><span data-stu-id="3037f-108">(Optional) Assign the user account a user-specific voice policy.</span></span>

  - <span data-ttu-id="3037f-109">Opzionale Assegna l'account utente a un dial plan specifico per l'utente.</span><span class="sxs-lookup"><span data-stu-id="3037f-109">(Optional) Assign the user account a user-specific dial plan.</span></span>

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="3037f-110">Per abilitare un account utente per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="3037f-110">To enable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="3037f-111">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3037f-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3037f-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3037f-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3037f-113">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3037f-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3037f-114">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="3037f-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="3037f-115">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente che si vuole abilitare e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="3037f-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="3037f-116">Nella tabella fare clic sull'account utente che si desidera abilitare per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="3037f-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="3037f-117">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="3037f-117">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="3037f-118">Nella pagina **modifica utente di Lync Server** , in **telefonia**, fare clic su **VoIP aziendale**.</span><span class="sxs-lookup"><span data-stu-id="3037f-118">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="3037f-119">Fare clic su **URI linea**e quindi digitare un numero di telefono normalizzato univoco, ad esempio Tel: + 14255550200.</span><span class="sxs-lookup"><span data-stu-id="3037f-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>

9.  <span data-ttu-id="3037f-120">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="3037f-120">Click **Commit**.</span></span>

<span data-ttu-id="3037f-121">Per completare l'abilitazione di un utente per VoIP aziendale, assicurati che all'utente sia assegnato un criterio vocale e un dial plan, sia globale (assegnato per impostazione predefinita) che specifico per l'utente.</span><span class="sxs-lookup"><span data-stu-id="3037f-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.</span></span>

<span data-ttu-id="3037f-122">Per impostazione predefinita, a tutti gli utenti viene assegnato un criterio vocale globale e un dial plan.</span><span class="sxs-lookup"><span data-stu-id="3037f-122">By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="3037f-123">Se un criterio vocale o un dial plan esiste a livello di sito per il sito in cui si trova l'account utente, i criteri del sito verranno applicati automaticamente all'utente.</span><span class="sxs-lookup"><span data-stu-id="3037f-123">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="3037f-124">Per applicare un criterio vocale per utente o un dial plan a un utente, è necessario eseguire i cmdlet **Grant-CsVoicePolicy** e **Grant-CsDialPlan** .</span><span class="sxs-lookup"><span data-stu-id="3037f-124">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="3037f-125">Per informazioni dettagliate, vedere la documentazione di [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="3037f-125">For details, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="voice-policy-assignment"></a><span data-ttu-id="3037f-126">Assegnazione dei criteri vocali</span><span class="sxs-lookup"><span data-stu-id="3037f-126">Voice Policy Assignment</span></span>

<span data-ttu-id="3037f-127">I criteri vocali globali e a livello di sito vengono assegnati automaticamente a tutti gli account utente abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="3037f-127">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="3037f-128">È anche possibile creare criteri vocali applicabili a utenti o gruppi specifici.</span><span class="sxs-lookup"><span data-stu-id="3037f-128">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="3037f-129">Questi criteri per utente devono essere assegnati in modo esplicito agli utenti o ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="3037f-129">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="3037f-130">Se si vuole usare il criterio vocale globale o del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione e continuare la sezione Assegnazione di dial plan più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3037f-130">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to Dial Plan Assignment section later in this topic.</span></span>

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="3037f-131">Per assegnare un criterio vocale specifico per l'utente</span><span class="sxs-lookup"><span data-stu-id="3037f-131">To assign a user-specific voice policy</span></span>

1.  <span data-ttu-id="3037f-132">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3037f-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3037f-133">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3037f-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3037f-134">Per assegnare un criterio vocale utente esistente a un utente, eseguire le operazioni seguenti al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="3037f-134">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="3037f-135">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3037f-135">For example:</span></span>
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    <span data-ttu-id="3037f-136">In questo esempio l'utente con il nome visualizzato Bob Kelly viene assegnato il criterio vocale con il nome **VoicePolicyJapan**.</span><span class="sxs-lookup"><span data-stu-id="3037f-136">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>

<span data-ttu-id="3037f-137">Per informazioni dettagliate sull'assegnazione di un criterio vocale specifico per l'utente o sull'uso del cmdlet **Grant-CsVoicePolicy** , vedere la documentazione di [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="3037f-137">For details about assigning a user-specific voice policy or about running the **Grant-CsVoicePolicy** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a><span data-ttu-id="3037f-138">Assegnazione di dial plan</span><span class="sxs-lookup"><span data-stu-id="3037f-138">Dial Plan Assignment</span></span>

<span data-ttu-id="3037f-139">Per completare la configurazione dell'account utente per gli utenti di VoIP aziendale o per gli utenti di servizi di conferenza telefonica con accesso esterno, l'utente deve essere assegnato a un dial plan.</span><span class="sxs-lookup"><span data-stu-id="3037f-139">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="3037f-140">Gli account utente useranno automaticamente il dial plan globale o, se disponibile, il dial plan a livello di sito, quando non si assegna esplicitamente un dial plan per utente esistente.</span><span class="sxs-lookup"><span data-stu-id="3037f-140">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="3037f-141">Se si vuole usare il dial plan globale o del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione.</span><span class="sxs-lookup"><span data-stu-id="3037f-141">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>

<div>

## <a name="to-assign-a-dial-plan"></a><span data-ttu-id="3037f-142">Per assegnare un dial plan</span><span class="sxs-lookup"><span data-stu-id="3037f-142">To assign a dial plan</span></span>

1.  <span data-ttu-id="3037f-143">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3037f-143">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3037f-144">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3037f-144">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3037f-145">Per assegnare un dial plan specifico per l'utente, eseguire la procedura seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="3037f-145">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="3037f-146">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3037f-146">For example:</span></span>
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    <span data-ttu-id="3037f-147">In questo esempio l'utente con il nome visualizzato Bob Kelly viene assegnato al dial plan utente con il nome **DialPlanJapan**.</span><span class="sxs-lookup"><span data-stu-id="3037f-147">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>

<span data-ttu-id="3037f-148">Per informazioni dettagliate sull'assegnazione di un dial plan utente o sull'esecuzione del cmdlet **Grant-CsDialPlan** , vedere la documentazione di [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="3037f-148">For details about assigning a user dial plan or about running the **Grant-CsDialPlan** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3037f-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3037f-149">See Also</span></span>


[<span data-ttu-id="3037f-150">Disabilitare un utente per VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3037f-150">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

