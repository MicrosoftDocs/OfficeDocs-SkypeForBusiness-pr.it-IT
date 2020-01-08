---
title: 'Lync Server 2013: utilizzo di stop per il servizio di registrazione centralizzato'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 521328b688f90ca591abddb3e59e7d49ae771b15
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a>Uso di stop per il servizio di registrazione centralizzato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

È possibile interrompere una sessione di registrazione corrente con il cmdlet Stop-CsClsLogging. In genere, non ci sono molte situazioni in cui è necessario interrompere una sessione di registrazione. Ad esempio, è possibile cercare registri e modificare le configurazioni senza prima di tutto necessario interrompere la registrazione. Se sono in uso due scenari, ad esempio AlwaysOn e UserReplicator, ed è necessario raccogliere informazioni correlate all'autenticazione, è necessario interrompere uno degli altri scenari (in un ambito globale, di un sito, di un pool o un computer) prima di iniziare a eseguire Scenario di autenticazione. Per informazioni dettagliate, vedere [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).

<div>


> [!NOTE]  
> Per determinare gli scenari che è possibile eseguire in una distribuzione, un pool o un computer specifico, è necessario tenere presente che si è limitati a eseguire due scenari <STRONG>per ogni computer</STRONG>. Se si esegue la registrazione di attività in un pool, è consigliabile trattare un pool come singola entità. Nella maggior parte dei casi, non avrebbe senso eseguire scenari diversi in ogni computer in un pool. È consigliabile esaminare il problema di cui si stanno raccogliendo i dati e pensare allo scenario più appropriato in un dato computer nella distribuzione complessiva. Se, ad esempio, consideriamo lo scenario UserReplicator, il valore dell'uso di UserReplicator in un server perimetrale o in un pool di Edge sarà molto scarso.<BR>Dopo aver compreso il problema e l'ambito dell'impatto, è consigliabile scegliere quali scenari eseguire in quali computer e pool. Anche se lo scenario AlwaysOn ha un significato per un'applicazione di ambito esteso, poiché raccoglie informazioni su un'ampia gamma di provider, gli scenari specifici hanno solo valore dell'applicazione in computer o pool specifici. È inoltre necessario prestare attenzione quando si avvia una sessione di registrazione in modo casuale senza prima capire il valore di uno scenario specifico. Se si usa lo scenario errato oppure se si usa uno scenario appropriato per l'attività e si applica lo scenario nell'ambito errato (globale, sito, pool o computer), è possibile ottenere dati discutibili che non sono molto utili, come se non fosse stato eseguito affatto lo scenario.



</div>

Per controllare le funzioni del servizio di registrazione centralizzato tramite Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contiene uno di questi due gruppi. Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Ad esempio:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>Per interrompere una sessione di servizio di registrazione centralizzata attualmente in uso

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire una query sul servizio di registrazione centralizzata per individuare gli scenari in esecuzione digitando quanto segue:
    
        Show-CsClsLogging
    
    ![Console di Windows PowerShell dopo la chiamata di show-CSCL](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "console di Windows PowerShell dopo aver chiamato Show-CSCL")
    
    Il risultato di Show-CsClsLogging è un riepilogo degli scenari in uso e l'ambito in cui sono in uso. Per informazioni dettagliate, vedere [Mostra-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).

3.  Per interrompere una sessione di registrazione attualmente in uso con uno scenario specifico, digitare:
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    Ad esempio:
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    Questo comando interrompe la registrazione con lo scenario UserReplicatior in pool01.contoso.net.
    
    <div>
    

    > [!NOTE]  
    > I log creati durante questa sessione di registrazione usando lo scenario UserReplicator non vengono eliminati. La registrazione è ancora disponibile per l'esecuzione delle ricerche sull'uso del comando Cerca-CsClsLogging. Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Ricerca-CsClsLogging</A>.

    
    </div>

Agendo come comando complementare per Start-CsClsLogging, il cmdlet Stop-CsClsLogging termina la sessione di registrazione, definita da scenari, e mantiene i registri creati dalla sessione di registrazione. È possibile eseguire due scenari in un computer specifico in qualsiasi momento. Il metodo di interruzione di uno scenario per raccogliere informazioni con un altro scenario è un'attività comune che è possibile eseguire durante la maggior parte dei problemi di lavoro.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Uso di Start per il servizio di registrazione centralizzato per acquisire i registri in Lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[Panoramica del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Mostra-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

