---
title: 'Lync Server 2013: Procedure per il ripristino di emergenza dei Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5325f84ff5bf5a0f8d9d1a856110e0ac18b37d93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a>Procedure per il ripristino di emergenza dei Response Group in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Durante la fase di failover del ripristino di emergenza, i gruppi di risposte si trovano in più pool: nel pool principale (non disponibile) e nel pool di backup. I gruppi di risposte in entrambi i pool hanno lo stesso nome e lo stesso proprietario (il pool principale), ma hanno genitori diversi. Durante questo periodo i cmdlet di Response Group funzionano in modo leggermente diverso. Assicurarsi di usare i parametri specificati nella procedura seguente. Per informazioni dettagliate sul funzionamento dei cmdlet durante la fase di failover, vedere l'articolo di Blog di NextHop "Lync Server 2013: recupero di Response Groups durante [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)il ripristino di emergenza". Questo articolo di Blog si applica anche alla versione rilasciata di Lync Server 2013.

Seguire i passaggi descritti nella procedura seguente per preparare ed eseguire il ripristino di emergenza per il servizio Response Group di Lync Server.

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a>Per eseguire il failover e il failover del gruppo di risposte

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire in routine i backup. Nella riga di comando digitare:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    Ad esempio:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  Durante un'interruzione, dopo il failover nel pool di backup, importare i Response Groups nel pool di backup. Nella riga di comando digitare:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    Se si vogliono sostituire le impostazioni a livello di applicazione nel pool di backup con le impostazioni del pool principale, includere il parametro – ReplaceExistingSettings. Ad esempio:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > Se non Sostituisci le impostazioni nel pool di backup e il pool principale non può essere recuperato, le impostazioni del pool principale andranno perse. Per informazioni dettagliate, vedere <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">pianificazione del ripristino di emergenza di Response Group in Lync Server 2013</A>.

    
    </div>

4.  Verificare che l'importazione abbia avuto esito positivo visualizzando i gruppi di risposta importati. I gruppi di risposta importati continuano a essere di proprietà del pool principale. Effettuare le seguenti operazioni:
    
      - Visualizzare tutti i flussi di lavoro nel pool di backup di proprietà del pool principale e verificare che siano inclusi tutti i flussi di lavoro del pool principale. Nella riga di comando digitare:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Ad esempio:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - Visualizzare tutte le code nel pool di backup di proprietà del pool principale e verificare che siano incluse tutte le code di pool primarie. Nella riga di comando digitare:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Ad esempio:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Visualizzare tutti i gruppi di agenti nel pool di backup di proprietà del pool principale e verificare che siano inclusi tutti i gruppi di agenti di pool primari. Nella riga di comando digitare:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Ad esempio:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Visualizzare tutte le ore di attività nel pool di backup di proprietà del pool principale e verificare che siano incluse tutte le ore del pool principale. Nella riga di comando digitare:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Ad esempio:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Visualizzare tutti i set di festività nel pool di backup di proprietà del pool principale e verificare che siano inclusi tutti i set di festività principali del pool. Nella riga di comando digitare:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Ad esempio:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    In alternativa, puoi visualizzare tutti i gruppi di risposte nel pool di backup, inclusi quelli di proprietà del pool principale e quelli di proprietà del pool di backup, usando il parametro – ShowAll anziché il parametro – Owner. Ad esempio:
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > Devi usare il parametro – ShowAll o il parametro – Owner. Se non si usa uno di questi parametri, i gruppi di risposta importati nel pool di backup non verranno elencati nei risultati restituiti dai cmdlet.

    
    </div>

5.  Verificare che l'importazione abbia avuto successo effettuando una chiamata a un gruppo di risposte importato e verificando che la chiamata sia gestita correttamente.

6.  Richiedere agli agenti che sono membri di gruppi di agenti formali di accedere ai gruppi di agenti nel pool di backup.

7.  Gestire e modificare i gruppi di risposta importati come di consueto.
    
    <div>
    

    > [!IMPORTANT]  
    > Mentre i gruppi di risposte si trovano nel pool di backup, è necessario usare Lync Server Management Shell per gestirli. Non è possibile usare il pannello di controllo di Lync Server per gestire i gruppi di risposta importati nel pool di backup.

    
    </div>

8.  Dopo il ripristino del pool principale e il failback, esportare i gruppi di risposta di pool primari importati nel pool di backup. Nella riga di comando digitare:
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  Importare di nuovo i gruppi di risposte nel pool principale. Nella riga di comando digitare:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    Ad esempio:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > Se si ricompila un pool durante il recupero, sia con lo stesso nome di dominio completo o con uno diverso (FQDN), è necessario usare il parametro – OverwriteOwner. Come regola generale, è sempre possibile usare il parametro – OverwriteOwner quando si importano nuovamente i gruppi di risposte nel pool principale.

    
    </div>
    
    Se si è distribuito un nuovo pool (con lo stesso FQDN o un nome di dominio completo diverso) per sostituire il pool principale e si vuole usare le impostazioni a livello di applicazione dal pool di backup per il nuovo pool, includere il parametro – ReplaceExistingSettings. Nella riga di comando digitare:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    Ad esempio:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > Se non si vuole sostituire le impostazioni a livello di applicazione e il file audio predefinito per la musica in blocco per il nuovo pool con le impostazioni del pool di backup, il nuovo pool utilizzerà le impostazioni a livello di applicazione predefinite.

    
    </div>

10. Verificare che l'importazione di nuovo nel pool principale abbia avuto successo visualizzando la configurazione del gruppo di risposta importata. Effettuare le seguenti operazioni:
    
      - Visualizzare tutti i flussi di lavoro nel pool principale e verificare che siano inclusi tutti i flussi di lavoro importati. Nella riga di comando digitare:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Ad esempio:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - Visualizzare tutte le code nel pool principale e verificare che siano incluse tutte le code importate. Nella riga di comando digitare:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Ad esempio:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Visualizzare tutti i gruppi di agenti nel pool principale e verificare che siano inclusi tutti i gruppi di agenti importati. Nella riga di comando digitare:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        Ad esempio:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Visualizzare tutte le ore di attività nel pool principale e verificare che siano incluse tutte le ore di attività importate. Nella riga di comando digitare:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Ad esempio:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Visualizzare tutti i set di festività nel pool principale e verificare che siano inclusi tutti i set di festività importati. Nella riga di comando digitare:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Ad esempio:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. Verificare che l'importazione abbia avuto successo effettuando una chiamata a un gruppo di risposte importato e verificando che la chiamata sia gestita correttamente.

12. Facoltativamente, rimuovere i gruppi di risposte di proprietà del pool principale dal pool di backup. Nella riga di comando digitare:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    Ad esempio:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > Questo passaggio consente di creare un nuovo file con la configurazione esportata e quindi di rimuoverlo dal pool di backup.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

