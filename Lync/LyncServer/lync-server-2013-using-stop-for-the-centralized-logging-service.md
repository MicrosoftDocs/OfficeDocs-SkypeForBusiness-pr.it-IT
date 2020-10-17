---
title: 'Lync Server 2013: utilizzo di stop per il servizio di registrazione centralizzato'
description: 'Lync Server 2013: utilizzo di stop per il servizio di registrazione centralizzato.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 114530d976b623bd4e5d75555a91a0ec3240ba07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560222"
---
# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a>Utilizzo di stop per il servizio di registrazione centralizzato in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Il cmdlet Stop-CsClsLogging consente di interrompere una sessione di registrazione in esecuzione. In generale, le situazioni in cui può essere necessario interrompere una sessione di registrazione non sono molte. Ad esempio, è possibile eseguire ricerche nei log e modificare configurazioni senza bisogno di interrompere la registrazione. Se sono in esecuzione due scenari, ad esempio AlwaysOn e UserReplicator, ed è necessario raccogliere informazioni relative all'autenticazione, per poter avviare lo scenario Authentication sarà necessario interrompere uno dei due scenari, a livello globale, di pool o di sito. Per informazioni dettagliate, vedere [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).

<div>


> [!NOTE]  
> Nella determinazione degli scenari da eseguire in un dato pool, computer o distribuzione, tenere presente che l'esecuzione è limitata a due scenari <STRONG>per computer</STRONG>. Se si stanno registrando le attività in un pool, è consigliabile trattare il pool come una singola entità. Nella maggior parte dei casi l'esecuzione di scenari diversi in ogni computer di un pool non ha senso. È invece opportuno esaminare il problema su cui si stanno raccogliendo dati e stabilire quale scenario abbia più senso in un determinato computer nella distribuzione complessiva. Ad esempio, se si considera lo scenario UserReplicator, è necessario che l'esecuzione di UserReplicator in un server perimetrale o in un pool perimetrale sia molto scarsa.<BR>Una volta compresi il problema e l'ambito dell'impatto, andranno effettuate scelte attente sugli scenari da eseguire e sui computer e pool ai quali applicarli. Mentre lo scenario AlwaysOn è adatto all'applicazione su vasta scala, in quanto raccoglie informazioni su un'ampia gamma di provider, gli scenari specifici risultano utili solo se applicati a specifici computer o pool. È inoltre necessaria attenzione quando si avvia una sessione di registrazione scelta a caso senza prima comprendere il valore di un dato scenario. Se si utilizza lo scenario sbagliato, oppure si sceglie uno scenario appropriato per l'attività, ma lo si applica all'ambito sbagliato (a livello globale, di sito, di pool o di computer), si possono ottenere dati dubbi e non molto utili, come se non si fosse eseguito affatto lo scenario.



</div>

Per controllare le funzioni del servizio di registrazione centralizzato utilizzando Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contenga uno dei due gruppi. Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati autonomamente), eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Ad esempio:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>Per arrestare una sessione di servizio di registrazione centralizzata attualmente in esecuzione

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire una query sul servizio di registrazione centralizzato per individuare gli scenari attualmente in esecuzione digitando quanto segue:
    
        Show-CsClsLogging
    
    ![Console di Windows PowerShell dopo aver chiamato Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Console di Windows PowerShell dopo aver chiamato Show-CsCl")
    
    Il risultato di Show-CsClsLogging è un riepilogo degli scenari in esecuzione e dei relativi ambiti di esecuzione. Per informazioni dettagliate, vedere [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).

3.  Per interrompere una sessione di registrazione in esecuzione con uno scenario specifico, digitare:
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    Ad esempio:
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    Questo comando interromperà la registrazione con lo scenario UserReplicatior in pool01.contoso.net.
    
    <div>
    

    > [!NOTE]  
    > I log creati nel corso di questa sessione di registrazione utilizzando lo scenario UserReplicator non vengono eliminati. La registrazione resta disponibile per l'esecuzione di ricerche mediante il comando Search-CsClsLogging. Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.

    
    </div>

Il cmdlet Stop-CsClsLogging funge da comando complementare a Start-CsClsLogging e interrompe la sessione di registrazione, definita dagli scenari, conservando i log creati. È possibile eseguire un totale di due scenari su un dato computer in qualsiasi momento. L'interruzione di uno scenario per raccogliere informazioni utilizzando uno scenario diverso è un'attività comune, utile nella maggior parte delle procedure di risoluzione dei problemi relativi ai carichi di lavoro.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Utilizzo di Start per il servizio di registrazione centralizzato per l'acquisizione dei log in Lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[Panoramica del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

