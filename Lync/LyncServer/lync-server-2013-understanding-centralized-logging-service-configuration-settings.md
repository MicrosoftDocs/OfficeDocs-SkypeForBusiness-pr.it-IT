---
title: Informazioni sulle impostazioni di configurazione del servizio di registrazione centralizzata
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a4f9a6a2db8cb4726abc65553fc4482d349f38f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Informazioni sulle impostazioni di configurazione del servizio di registrazione centralizzata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Il servizio di registrazione centralizzato è configurato per definire il modo in cui il servizio di registrazione è destinato a raccogliere, come raccoglie, da dove raccoglierà e quali sono le impostazioni del log. Puoi definire queste impostazioni a livello globale (ovvero, per l'intera distribuzione) o per un sito (ovvero un sito denominato nella distribuzione). Tutte le registrazioni definitive utilizzeranno le impostazioni appropriate per l'identità usata per i comandi per avviare, arrestare, svuotare e cercare i registri.

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a>Per visualizzare la configurazione del servizio di registrazione centralizzata corrente

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Digitare quanto segue al prompt della riga di comando:
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > È possibile limitare o espandere l'ambito delle impostazioni di configurazione restituite definendo <CODE>-Identity</CODE> e un ambito, ad esempio "site: Redmond", per restituire solo il CsClsConfiguration per il sito Redmond. Per informazioni dettagliate su una determinata parte della configurazione, è possibile reindirizzare l'output in un altro cmdlet di Windows PowerShell. Ad esempio, per ottenere informazioni dettagliate sugli scenari definiti nella configurazione per il sito "Redmond", digitare:<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE>

    
    </div>
    
    ![Esempio di output di Get-CsClsConfiguration.] (images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Esempio di output di Get-CsClsConfiguration.")
    
    Il risultato del cmdlet Visualizza la configurazione corrente del servizio di registrazione centralizzata.
    
    
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
    <td><p><strong>Identity</strong></p></td>
    <td><p>Identifica l'ambito e il nome per questa configurazione. Esiste una sola configurazione globale e una configurazione per ogni sito.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Scenari</strong></p></td>
    <td><p>Elenco di tutti gli scenari definiti per questa configurazione.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>SearchTerms</strong></p></td>
    <td><p>Termini di ricerca definiti per la configurazione. Office 365, non distribuzioni locali.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>SecurityGroups</strong></p></td>
    <td><p>I gruppi di sicurezza definiti che controllano chi, ovvero i membri dei gruppi di sicurezza, possono vedere i computer in base al sito in cui si trovano. Il sito, in questo contesto, è il sito definito in Generatore di topologie.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Aree geografiche</strong></p></td>
    <td><p>Le aree definite vengono usate per raccogliere SecurityGroups in un'area geografica, ad esempio EMEA.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileFolder</strong></p></td>
    <td><p>Percorso definito nella posizione in cui vengono scritti i file di log nei computer. CLSAgent scrive i file di log e viene eseguito nel contesto del servizio di rete. In questo caso,% TEMP% si espande in%WINDIR%\ServiceProfiles\NetworkService\AppData\Local</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>EtlFileRolloverSizeMB</strong></p></td>
    <td><p>Il parametro indica la dimensione massima del file di log prima che venga creato un nuovo file di log di traccia eventi (ETL). Viene creato un nuovo file di log quando viene raggiunta la dimensione definita anche se il tempo massimo impostato in EtlFileRolloverMinutes non è ancora stato raggiunto.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileRolloverMinutes</strong></p></td>
    <td><p>Intervallo di tempo massimo definito, in minuti, che un log può trascorrere prima che venga creato un nuovo file con estensione ETL. Viene creato un nuovo file di log quando il timer scade anche se la dimensione massima impostata in EtlFileRolloverSizeMB non è ancora stata raggiunta.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>TmfFileSearchPath</strong></p></td>
    <td><p>Posizione in cui cercare i file di formato del messaggio di traccia. I file di formato del messaggio di traccia vengono usati per convertire i file binari in un formato leggibile.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalFolders</strong></p></td>
    <td><p>Percorso definito nella posizione in cui vengono scritti i file di cache nei computer. CLSAgent scrive i file della cache ed è in esecuzione nel contesto del servizio di rete. In questo caso,% TEMP% si espande in%WINDIR%\ServiceProfiles\NetworkService\AppData\Local. Per impostazione predefinita, i file di cache e i file di log vengono scritti nella stessa directory.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileNetworkFolder</strong></p></td>
    <td><p>Puoi definire un percorso UNC (Universal Naming Convention) per ricevere i file della cache durante le operazioni di registrazione.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalRetentionPeriod</strong></p></td>
    <td><p>Definito come il tempo massimo, in giorni, in cui vengono conservati i file della cache.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileMaxDiskUsage</strong></p></td>
    <td><p>Definita come percentuale di spazio su disco che può essere usata dai file di cache.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ComponentThrottleLimit</strong></p></td>
    <td><p>Definito come numero massimo di tracce al secondo che un componente può produrre prima che venga attivato il limitatore automatico della valvola a farfalla.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ComponentThrottleSample</strong></p></td>
    <td><p>Numero di volte in 60 secondi che il ComponentThrottleLimit può essere superato.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>MinimumClsAgentServiceVersion</strong></p></td>
    <td><p>La versione minima di CLSAgent è consentita per l'esecuzione. Questo elemento è destinato a Office 365.</p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a>Vedere anche


[Panoramica del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))  
[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

