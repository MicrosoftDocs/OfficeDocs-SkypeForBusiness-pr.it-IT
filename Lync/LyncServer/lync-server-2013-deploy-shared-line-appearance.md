---
title: "Lync Server 2013: distribuire l'aspetto della linea condivisa"
description: "Lync Server 2013: distribuire l'aspetto della linea condivisa."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c83c06bbc9b91e11cabc0abee20de28fc7281205
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558622"
---
# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="63b38-103">Distribuire l'aspetto delle linee condivise in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63b38-103">Deploy Shared Line Appearance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63b38-104">_**Ultimo argomento modificato:** 2016-06-13_</span><span class="sxs-lookup"><span data-stu-id="63b38-104">_**Topic Last Modified:** 2016-06-13_</span></span>

<span data-ttu-id="63b38-105">Leggere questo argomento per informazioni su come distribuire l'aspetto di riga condiviso (SLA, Shared Line Appearance) in Lync Server 2013, aggiornamento cumulativo aprile 2016.</span><span class="sxs-lookup"><span data-stu-id="63b38-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="63b38-106">SLA è una funzionalità per la gestione di più chiamate su un numero specifico denominato numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="63b38-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="63b38-107">Per ulteriori informazioni su questa funzionalità, vedere [Plan for Shared Line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="63b38-107">For more information about this feature, see [Plan for Shared Line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span></span>

<span data-ttu-id="63b38-108">SLA (Shared Line Appearance) è una nuova funzionalità di Lync Server 2013, aggiornamento cumulativo aprile 2016.</span><span class="sxs-lookup"><span data-stu-id="63b38-108">Shared Line Appearance (SLA) is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="63b38-109">Per abilitare questa funzionalità, è necessario che sia stata distribuita per la prima volta questo aggiornamento cumulativo.</span><span class="sxs-lookup"><span data-stu-id="63b38-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

<div>

## <a name="install-shared-line-appearance"></a><span data-ttu-id="63b38-110">Installare l'aspetto della linea condivisa</span><span class="sxs-lookup"><span data-stu-id="63b38-110">Install Shared Line Appearance</span></span>

1.  <span data-ttu-id="63b38-111">Dopo la distribuzione di Lync Server 2013, aggiornamento cumulativo di aprile 2016, l'applicazione SLA non è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="63b38-111">After Lync Server 2013, Cumulative Update April 2016 is deployed, the SLA application is not enabled by default.</span></span> <span data-ttu-id="63b38-112">Per abilitare l'applicazione, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="63b38-112">To enable the application, follow the steps below:</span></span>
    
    1.  <span data-ttu-id="63b38-113">Registrare SLA come applicazione server eseguendo il comando seguente per ogni pool:</span><span class="sxs-lookup"><span data-stu-id="63b38-113">Register SLA as a server application by running the following command for each pool:</span></span>
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        <span data-ttu-id="63b38-114">dove% FQDN% è il nome di dominio completo del pool.</span><span class="sxs-lookup"><span data-stu-id="63b38-114">where %FQDN% is the fully qualified domain name of the pool.</span></span>
    
    2.  <span data-ttu-id="63b38-115">Eseguire il seguente comando per aggiornare i ruoli RBAC per i cmdlet di SLA:</span><span class="sxs-lookup"><span data-stu-id="63b38-115">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>
        ```powershell
        Update-CsAdminRole 
        ```
    3.  <span data-ttu-id="63b38-116">Riavviare tutti i Front End Server (servizio RTCSRV) in tutti i pool in cui è stato installato e abilitato SLA:</span><span class="sxs-lookup"><span data-stu-id="63b38-116">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="63b38-117">Creare un gruppo di SLA e aggiungervi gli utenti</span><span class="sxs-lookup"><span data-stu-id="63b38-117">Create an SLA group and add users to it</span></span>

1.  <span data-ttu-id="63b38-118">Creare il gruppo di SLA utilizzando il cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :</span><span class="sxs-lookup"><span data-stu-id="63b38-118">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="63b38-119">Il cmdlet Set-CsSlaConfiguration contrassegna l'account VoIP aziendale SLAGroup1 come entità SLA e il numero di SLAGroup1 diventa il numero del gruppo di SLA.</span><span class="sxs-lookup"><span data-stu-id="63b38-119">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="63b38-120">Tutte le chiamate a SLAGroup1 suoneranno l'intero gruppo del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="63b38-120">All calls to SLAGroup1 will ring the entire SLA group.</span></span>
    
    <span data-ttu-id="63b38-121">Nell'esempio seguente viene creato un gruppo di SLA per un utente VoIP aziendale esistente, SLAGroup1, e viene utilizzato il numero assegnato a SLAGroup1 come numero della linea principale del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="63b38-121">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>
    
    <span data-ttu-id="63b38-122">Il comando imposta il numero massimo di chiamate simultanee per il nuovo gruppo di SLA su 3 e per le chiamate superiori a quelle per ascoltare un segnale di occupato:</span><span class="sxs-lookup"><span data-stu-id="63b38-122">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    <span data-ttu-id="63b38-123">È possibile utilizzare Set-CsSlaConfiguration per creare un nuovo gruppo di SLA o modificarne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="63b38-123">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="63b38-124">Si noti che il valore specificato per <CODE>-Identity</CODE> deve essere un account utente esistente abilitato per VoIP aziendale valido.</span><span class="sxs-lookup"><span data-stu-id="63b38-124">Note that what you specify for <CODE>-Identity</CODE> must be a valid existing Enterprise Voice-enabled user account.</span></span>

    
    </div>

2.  <span data-ttu-id="63b38-125">Aggiungere delegati al gruppo utilizzando il cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) :</span><span class="sxs-lookup"><span data-stu-id="63b38-125">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) cmdlet:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="63b38-126">Nell'esempio seguente viene aggiunto un utente al gruppo di SLA.</span><span class="sxs-lookup"><span data-stu-id="63b38-126">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="63b38-127">Ogni utente aggiunto al gruppo deve essere un utente abilitato VoIP aziendale valido:</span><span class="sxs-lookup"><span data-stu-id="63b38-127">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    <span data-ttu-id="63b38-128">Ripetere il cmdlet per ogni utente che si desidera aggiungere al gruppo.</span><span class="sxs-lookup"><span data-stu-id="63b38-128">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="63b38-129">Gli utenti possono appartenere solo a un singolo gruppo di SLA.</span><span class="sxs-lookup"><span data-stu-id="63b38-129">Users can only belong to a single SLA group.</span></span>

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="63b38-130">Configurare l'opzione occupato del gruppo di SLA</span><span class="sxs-lookup"><span data-stu-id="63b38-130">Configure the SLA group Busy Option</span></span>

1.  <span data-ttu-id="63b38-131">Configurare l'opzione occupato del gruppo di SLA utilizzando il cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :</span><span class="sxs-lookup"><span data-stu-id="63b38-131">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="63b38-132">Nell'esempio seguente vengono impostate le chiamate che superano il numero massimo di chiamate simultanee da inoltrare al numero di telefono 202-555-1234.</span><span class="sxs-lookup"><span data-stu-id="63b38-132">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="63b38-133">La destinazione potrebbe essere un utente dell'organizzazione invece di un numero di telefono; in tal caso, la sintassi per la persona che riceve le chiamate inoltrate è la stessa di quando si specifica un delegato: `sip:<NameofDelegate@domain>` .</span><span class="sxs-lookup"><span data-stu-id="63b38-133">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate: `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="63b38-134">L'altro parametro possibile per `BusyOption` è `Voicemail` :</span><span class="sxs-lookup"><span data-stu-id="63b38-134">The other possible parameter for `BusyOption` is `Voicemail`:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="63b38-135">Configurare l'opzione di chiamata senza risposta del gruppo di SLA</span><span class="sxs-lookup"><span data-stu-id="63b38-135">Configure the SLA group Missed Call Option</span></span>

1.  <span data-ttu-id="63b38-136">Configurare l'opzione di chiamata senza risposta del gruppo SLA utilizzando il cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :</span><span class="sxs-lookup"><span data-stu-id="63b38-136">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    <span data-ttu-id="63b38-137">Nell'esempio seguente viene specificato che le chiamate perse devono essere inoltrate all'utente denominato `sla_forward_number` .</span><span class="sxs-lookup"><span data-stu-id="63b38-137">The following example specifies that missed calls are to be forwarded to the user named `sla_forward_number`.</span></span> <span data-ttu-id="63b38-138">Le opzioni valide per il `-MissedCallOption` parametro sono `Forward` , `BusySignal` o `Disconnect` .</span><span class="sxs-lookup"><span data-stu-id="63b38-138">The valid options for the `-MissedCallOption` parameter are `Forward`, `BusySignal`, or `Disconnect`.</span></span> <span data-ttu-id="63b38-139">Se si sceglie `Forward` , è necessario includere anche il `-MissedCallForwardTarget` parametro, con un utente o un numero di telefono come destinazione:</span><span class="sxs-lookup"><span data-stu-id="63b38-139">If you choose `Forward`, you must also include the `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="63b38-140">Rimuovere un delegato da un gruppo</span><span class="sxs-lookup"><span data-stu-id="63b38-140">Remove a delegate from a group</span></span>

1.  <span data-ttu-id="63b38-141">Rimuovere un delegato da un gruppo utilizzando il cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) :</span><span class="sxs-lookup"><span data-stu-id="63b38-141">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) cmdlet:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="63b38-142">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="63b38-142">For example:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a><span data-ttu-id="63b38-143">Eliminare un gruppo di SLA</span><span class="sxs-lookup"><span data-stu-id="63b38-143">Delete an SLA group</span></span>

1.  <span data-ttu-id="63b38-144">Eliminare un gruppo di SLA utilizzando il cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="63b38-144">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    <span data-ttu-id="63b38-145">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="63b38-145">For example:</span></span>
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

