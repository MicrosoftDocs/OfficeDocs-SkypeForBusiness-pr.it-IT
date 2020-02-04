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
ms.openlocfilehash: 96740d8937f1548952d41d5674ef3e66cd29e2b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a>Spostamento di gruppi di risposte in un nuovo pool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Lync Server 2013 introduce un nuovo supporto per i cmdlet per lo spostamento di gruppi di risposte da un pool a un altro, anche quando il nome di dominio completo (FQDN) è diverso.

Seguire i passaggi descritti nella procedura seguente per trasferire i gruppi di risposte da un pool Front-end a un altro pool Front-end con un nome di dominio completo diverso.

<div>


> [!NOTE]  
> In un ambiente di coesistenza è possibile trasferire i gruppi di risposte solo tra&nbsp;i pool Front End di Lync Server 2013.



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a>Per trasferire i gruppi di risposte in un pool con un nome di dominio completo diverso

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Esportare i gruppi di risposte nel pool di origine. Nella riga di comando digitare:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    Ad esempio:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    Per rimuovere i gruppi di risposte dal pool di origine durante l'esportazione, includere il parametro – RemoveExportedConfiguration. Ad esempio:
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  Importare i Response Groups nel pool di destinazione e assegnare il pool di destinazione come nuovo proprietario. Nella riga di comando digitare:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    Se si vuole anche copiare le impostazioni a livello di Response Group Application dal pool di origine al pool di destinazione, includere il parametro – ReplaceExistingRgsSettings. Puoi definire solo un set di impostazioni a livello di applicazione per ogni pool. Se si copiano le impostazioni a livello di applicazione dal pool di origine al pool di destinazione, le impostazioni del pool di origine sostituiscono le impostazioni per il pool di destinazione. Se le impostazioni a livello di applicazione non vengono copiate dal pool di origine, le impostazioni esistenti del pool di destinazione si applicano ai gruppi di risposta importati.
    
    Ad esempio:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > Le impostazioni a livello di applicazione includono la configurazione predefinita per la musica in blocco, il file audio predefinito per la musica in blocco, il periodo di risponderia dell'agente e la configurazione del contesto delle chiamate. Per visualizzare queste impostazioni di configurazione, eseguire il cmdlet <STRONG>Get-CsRgsConfiguration</STRONG> . Per informazioni dettagliate su questo cmdlet, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.

    
    </div>

4.  Verificare che l'importazione abbia avuto esito positivo visualizzando la configurazione del gruppo di risposta importato eseguendo le operazioni seguenti:
    
      - Verificare che tutti i flussi di lavoro siano stati importati. Nella riga di comando digitare quanto segue:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Verificare che tutte le code siano state importate. Nella riga di comando digitare quanto segue:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Verificare che tutti i gruppi di agenti siano stati importati. Nella riga di comando digitare quanto segue:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Verificare che tutte le ore di attività siano state importate. Nella riga di comando digitare quanto segue:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - Verificare che siano stati importati tutti i set di festività. Nella riga di comando digitare quanto segue:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  Verificare che l'importazione abbia avuto successo effettuando una chiamata a uno dei gruppi di risposta e verificando che la chiamata sia gestita correttamente.

6.  Richiedere agli agenti che sono membri di gruppi di agenti formali di accedere ai gruppi di agenti nel pool di destinazione.

7.  Se i gruppi di risposte non sono stati rimossi in precedenza dal pool di origine, rimuovere i gruppi di risposte dal pool di origine. Nella riga di comando digitare:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    Ad esempio:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

