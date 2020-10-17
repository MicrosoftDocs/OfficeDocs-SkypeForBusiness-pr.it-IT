---
title: Informazioni sulle impostazioni di configurazione del servizio di registrazione centralizzato
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd4403bedbf6fe3b6983e6071a162ce02c16936
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527753"
---
# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Informazioni sulle impostazioni di configurazione del servizio di registrazione centralizzato in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Il servizio di registrazione centralizzato è configurato per definire la modalità di raccolta del servizio di registrazione, il modo in cui verrà raccolta, la raccolta e le impostazioni del registro. Queste impostazioni vengono definite globalmente, ovvero per l'intera distribuzione, o per un sito, ovvero un sito denominato nella distribuzione. Per tutte le attività di registrazione definite verranno utilizzate le impostazioni adatte all'identità utilizzata per i comandi di avvio, interruzione, scaricamento e ricerca dei log.

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a>Per visualizzare la configurazione del servizio di registrazione centralizzata corrente

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Digitare quanto segue al prompt della riga di comando:
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > È possibile limitare o espandere l'ambito delle impostazioni di configurazione restituite definendo <CODE>-Identity</CODE> e un ambito, ad esempio "site: Redmond" per restituire solo CsClsConfiguration per il sito Redmond. Se si desiderano informazioni dettagliate su una determinata parte della configurazione, è possibile eseguire il piping dell'output in un altro cmdlet di Windows PowerShell. Ad esempio, per ottenere informazioni dettagliate sugli scenari definiti nella configurazione per il sito "Redmond", digitare: <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE>

    
    </div>
    
    ![Output di esempio da Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Output di esempio da Get-CsClsConfiguration.")
    
    Il risultato del cmdlet consente di visualizzare la configurazione corrente del servizio di registrazione centralizzato.
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Impostazione di configurazione</th>
    <th>Descrizione</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Identità</strong></p></td>
    <td><p>Identifica l'ambito e il nome della configurazione corrente. Esistono una sola configurazione a livello globale e una sola per sito.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Scenari</strong></p></td>
    <td><p>Elenco di tutti gli scenari definiti per questa configurazione.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>SearchTerms</strong></p></td>
    <td><p>Termini di ricerca definiti per la configurazione. Office 365 o Microsoft 365, non distribuzioni locali.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>SecurityGroups</strong></p></td>
    <td><p>Gruppi di sicurezza definiti che controllano gli utenti, ovvero i membri dei gruppi di sicurezza, che possono vedere i computer in base al sito in cui si trovano. Il sito, in questo contesto, è il sito come definito in Generatore di topologie.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Regioni</strong></p></td>
    <td><p>Le aree definite vengono utilizzate per raccogliere i SecurityGroups in un'area, ad esempio EMEA.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileFolder</strong></p></td>
    <td><p>Percorso definito della posizione nei computer in cui vengono scritti i file di log. CLSAgent scrive i file di log e viene eseguito nel contesto del servizio di rete. In tal caso, %TEMP% si espande in %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>EtlFileRolloverSizeMB</strong></p></td>
    <td><p>Il parametro indica le dimensioni massime del file di log prima che venga creato un nuovo file di log traccia eventi (.etl). Viene creato un nuovo file di log quando si raggiungono le dimensioni definite anche se non è stato ancora esaurito il tempo massimo impostato in EtlFileRolloverMinutes.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileRolloverMinutes</strong></p></td>
    <td><p>Periodo di tempo massimo definito, espresso in minuti, che può trascorrere per un log prima che venga creato un nuovo file con estensione etl. Viene creato un nuovo file di log quando il timer scade anche se non sono ancora state raggiunte le dimensioni massime impostate in EtlFileRolloverSizeMB.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>TmfFileSearchPath</strong></p></td>
    <td><p>Posizione in cui cercare i file TMF (Trace Message Format). I file TMF vengono utilizzati per convertire i file binari in un formato leggibile.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalFolders</strong></p></td>
    <td><p>Percorso definito della posizione nei computer in cui vengono scritti i file di cache. CLSAgent scrive i file di cache e viene eseguito nel contesto del servizio di rete. In questo caso, %TEMP% si espande in %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. Per impostazione predefinita, i file di cache e di log vengono scritti nella stessa directory.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileNetworkFolder</strong></p></td>
    <td><p>È possibile definire un percorso UNC (Universal Naming Convention) per ricevere i file di cache durante le operazioni di registrazione.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalRetentionPeriod</strong></p></td>
    <td><p>Definito come tempo massimo, espresso in giorni, di mantenimento dei file di cache.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileMaxDiskUsage</strong></p></td>
    <td><p>Definito come percentuale dello spazio su disco che può essere utilizzato dai file di cache.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ComponentThrottleLimit</strong></p></td>
    <td><p>Definito come numero massimo di tracce al secondo che un componente può produrre prima che venga attivato il limite di velocità automatico.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ComponentThrottleSample</strong></p></td>
    <td><p>Numero di volte nell'arco di 60 secondi in cui è possibile superare ComponentThrottleLimit.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>MinimumClsAgentServiceVersion</strong></p></td>
    <td><p>Versione minima di CLSAgent di cui è consentita l'esecuzione. Questo elemento è destinato a Office 365 o Microsoft 365.</p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a>Vedere anche


[Panoramica del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))  
[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

