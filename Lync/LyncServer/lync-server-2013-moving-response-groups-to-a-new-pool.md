---
title: 'Lync Server 2013: spostamento di Response Group in un nuovo pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 562d519e278096acf589482124eeb9cdf7ebf189
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a>Spostamento di Response Group in un nuovo pool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Lync Server 2013 introduce un nuovo supporto per i cmdlet per lo spostamento di Response Group da un pool a un altro, anche quando il nome di dominio completo (FQDN) è diverso.

Utilizzare i passaggi della procedura seguente per spostare i Response Group da un pool Front end a un altro pool Front end con un nome di dominio completo diverso.

<div>


> [!NOTE]  
> In un ambiente di coesistenza, è possibile spostare i Response Group solo tra&nbsp;i pool Front End di Lync Server 2013.



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a>Per spostare i Response Group in un pool con un nome di dominio completo diverso

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Esportare i Response Group nel pool di origine. Nella riga di comando digitare il comando seguente:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    Ad esempio:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    Per rimuovere i Response Group dal pool di origine durante l'esportazione, includere il parametro – RemoveExportedConfiguration. Ad esempio:
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  Importare i Response Group nel pool di destinazione e assegnare il pool di destinazione come nuovo proprietario. Nella riga di comando digitare il comando seguente:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    Se si desidera copiare anche le impostazioni a livello di applicazione di Response Group dal pool di origine al pool di destinazione, includere il parametro – ReplaceExistingRgsSettings. È possibile definire solo un set di impostazioni a livello di applicazione per ogni pool. Se si copiano le impostazioni a livello di applicazione dal pool di origine al pool di destinazione, le impostazioni del pool di origine sostituiscono quelle del pool di destinazione. Se le impostazioni a livello di applicazione non vengono copiate dal pool di origine, le impostazioni esistenti del pool di destinazione verranno applicate ai Response Group importati.
    
    Ad esempio:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > Le impostazioni a livello di applicazione includono la configurazione predefinita per la musica di attesa, il file audio predefinito per la musica in attesa, il periodo di richiamata dell'agente e la configurazione del contesto delle chiamate. Per visualizzare queste impostazioni di configurazione, eseguire il cmdlet <STRONG>Get-CsRgsConfiguration</STRONG>. Per informazioni dettagliate su questo cmdlet, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.

    
    </div>

4.  Verificare che l'importazione abbia avuto esito positivo visualizzando la configurazione di Response Group importata eseguendo le operazioni seguenti:
    
      - Verificare che tutti i flussi di lavoro siano stati importati. Nella riga di comando digitare quanto segue:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Verificare che tutte le code siano state importate. Nella riga di comando digitare quanto segue:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Verificare che tutti i gruppi di agenti siano stati importati. Nella riga di comando digitare quanto segue:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Verificare che tutte le ore di attività siano state importate. Nella riga di comando digitare quanto segue:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - Verificare che tutti i set di festività siano stati importati. Nella riga di comando digitare quanto segue:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  Verificare che l'importazione abbia avuto esito positivo effettuando una chiamata a uno dei Response Group e verificando che la chiamata venga gestita correttamente.

6.  Richiedere agli agenti che sono membri di gruppi di agenti formali di accedere ai rispettivi gruppi di agenti nel pool di destinazione.

7.  Se i Response Group non sono stati precedentemente rimossi dal pool di origine, rimuovere i Response Group dal pool di origine. Nella riga di comando digitare il comando seguente:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    Ad esempio:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

