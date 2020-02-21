---
title: "Lync Server 2013: distribuire l'aspetto della linea condivisa"
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
ms.openlocfilehash: 3be8c6610d27040d608070ca1e7dfb50a29a0cf1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a>Distribuire l'aspetto delle linee condivise in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-06-13_

Leggere questo argomento per informazioni su come distribuire l'aspetto di riga condiviso (SLA, Shared Line Appearance) in Lync Server 2013, aggiornamento cumulativo aprile 2016. SLA è una funzionalità per la gestione di più chiamate su un numero specifico denominato numero condiviso.

Per ulteriori informazioni su questa funzionalità, vedere [Plan for Shared Line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).

SLA (Shared Line Appearance) è una nuova funzionalità di Lync Server 2013, aggiornamento cumulativo aprile 2016. Per abilitare questa funzionalità, è necessario che sia stata distribuita per la prima volta questo aggiornamento cumulativo.

<div>

## <a name="install-shared-line-appearance"></a>Installare l'aspetto della linea condivisa

1.  Dopo la distribuzione di Lync Server 2013, aggiornamento cumulativo di aprile 2016, l'applicazione SLA non è abilitata per impostazione predefinita. Per abilitare l'applicazione, attenersi alla procedura seguente:
    
    1.  Registrare SLA come applicazione server eseguendo il comando seguente per ogni pool:
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        https://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        dove% FQDN% è il nome di dominio completo del pool.
    
    2.  Eseguire il seguente comando per aggiornare i ruoli RBAC per i cmdlet di SLA:
        ```powershell
        Update-CsAdminRole 
        ```
    3.  Riavviare tutti i Front End Server (servizio RTCSRV) in tutti i pool in cui è stato installato e abilitato SLA:
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a>Creare un gruppo di SLA e aggiungervi gli utenti

1.  Creare il gruppo di SLA utilizzando il cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    Il cmdlet Set-CsSlaConfiguration contrassegna l'account VoIP dell'organizzazione SLAGroup1 come entità SLA e il numero di SLAGroup1 diventa il numero del gruppo di SLA. Tutte le chiamate a SLAGroup1 suoneranno l'intero gruppo del contratto di servizio.
    
    Nell'esempio seguente viene creato un gruppo di SLA per un utente VoIP aziendale esistente, SLAGroup1, e viene utilizzato il numero assegnato a SLAGroup1 come numero della linea principale del contratto di servizio.
    
    Il comando imposta il numero massimo di chiamate simultanee per il nuovo gruppo di SLA su 3 e per le chiamate superiori a quelle per ascoltare un segnale di occupato:
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    È possibile utilizzare set-CsSlaConfiguration per creare un nuovo gruppo di SLA o modificarne uno esistente.
    
    <div>
    

    > [!NOTE]  
    > Si noti che il valore specificato <CODE>-Identity</CODE> per deve essere un account utente esistente abilitato per VoIP aziendale valido.

    
    </div>

2.  Aggiungere delegati al gruppo utilizzando il cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) :
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    Nell'esempio seguente viene aggiunto un utente al gruppo di SLA. Ogni utente aggiunto al gruppo deve essere un utente abilitato VoIP aziendale valido:
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    Ripetere il cmdlet per ogni utente che si desidera aggiungere al gruppo. Gli utenti possono appartenere solo a un singolo gruppo di SLA.

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a>Configurare l'opzione occupato del gruppo di SLA

1.  Configurare l'opzione occupato del gruppo di SLA utilizzando il cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    Nell'esempio seguente vengono impostate le chiamate che superano il numero massimo di chiamate simultanee da inoltrare al numero di telefono 202-555-1234. La destinazione potrebbe essere un utente dell'organizzazione invece di un numero di telefono; in tal caso, la sintassi per la persona che riceve le chiamate inoltrate è la stessa di quando si specifica un delegato: `sip:<NameofDelegate@domain>`. L'altro parametro possibile per `BusyOption` è `Voicemail`:
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a>Configurare l'opzione di chiamata senza risposta del gruppo di SLA

1.  Configurare l'opzione di chiamata senza risposta del gruppo SLA utilizzando il cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    Nell'esempio seguente viene specificato che le chiamate perse devono essere inoltrate all'utente `sla_forward_number`denominato. Le opzioni valide per il `-MissedCallOption` parametro sono `Forward` `BusySignal`, o `Disconnect`. Se si sceglie `Forward`, è necessario includere anche il `-MissedCallForwardTarget` parametro, con un utente o un numero di telefono come destinazione:
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a>Rimuovere un delegato da un gruppo

1.  Rimuovere un delegato da un gruppo utilizzando il cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) :
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    Ad esempio:
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a>Eliminare un gruppo di SLA

1.  Eliminare un gruppo di SLA utilizzando il cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    Ad esempio:
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

