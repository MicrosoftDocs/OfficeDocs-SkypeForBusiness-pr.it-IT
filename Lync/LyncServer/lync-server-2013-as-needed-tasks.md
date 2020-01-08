---
title: 'Lync Server 2013: attività necessarie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e96fd6e73e043c5ea7c476f939b3a3e06eadbdfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a>Attività necessarie in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-08-18_

Eseguire le attività seguenti in modo necessario. Sono spesso coperti anche da procedure standard:

  - **Controllo di sicurezza completo   ** È possibile eseguire regolarmente questo controllo, in risposta a un aggiornamento o alla riprogettazione del sistema di messaggistica oppure in risposta a una violazione della sicurezza tentata (o riuscita). La procedura può comportare la scansione di porte su server e firewall, verifiche di correzioni di sicurezza e test di penetrazione di terze parti.

  - **Sostituire i certificati relativi alla scadenza**   il controllo dei certificati di Lync Server è una delle attività settimanali regolari e, come parte della procedura, un amministratore deve avere un record delle date di scadenza di tutti i certificati. Questo record consente a un amministratore di creare una notifica quando un determinato certificato sta per essere scaduto e sostituito in base alle esigenze.

  - **Aggiornamento delle previsioni delle prestazioni**   aggiornare le previsioni delle prestazioni dopo un aggiornamento o una modifica della configurazione. L'organizzazione può usare le previsioni per misurare le prestazioni e rilevare i problemi che influiscono sulle prestazioni del sistema.

  - **La gestione**   della configurazione iniziale del pool aziendale di pool Enterprise, server Standard Edition e qualsiasi altro server nell'ambiente dell'organizzazione sono stati eseguiti durante la distribuzione dei singoli server. La gestione post-distribuzione di server e pool per i server standard e i pool Enterprise include le attività seguenti:
    
      - Gestione dei server front-end
    
      - Gestione delle conferenze Web
    
      - Gestione dei servizi di conferenza
    
      - Modifica delle credenziali dell'account del servizio
    
      - Gestione dei database
    
      - Avvio e arresto di servizi e disattivazione dei ruoli del server
    
      - Rimozione di server e ruoli del server, rimozione di pool e disattivazione di server e pool

  - **Gestione dell'utilizzo**   è possibile configurare Lync Server 2013 in modo da specificare le funzionalità e le funzionalità più appropriate per l'organizzazione. Sono inclusi i seguenti:
    
      - Gestione del supporto per le riunioni di conferenza Web locale
    
      - Gestione dell'uso di gruppi di distribuzione per l'invio di messaggi istantanei
    
      - Gestione di contatti, presenza e query
    
      - Configurazione del filtro della versione client
    
      - Configurazione del filtro ISTANTANEo intelligente
    
      - Configurazione dell'archiviazione, della registrazione del dettaglio delle chiamate e della conformità delle riunioni

  - ****   Gestione della connettività di Edge Server la gestione continua dei server e delle impostazioni necessarie per la connettività esterna include quanto segue:
    
      - Gestione della connettività tra server interni e Edge Server
    
      - Configurazione di interfacce e certificati interni ed esterni per Edge Server
    
      - Gestione dell'accesso dei partner federati

  - **L'amministrazione della**   rubrica che amministra i server della rubrica include le operazioni seguenti:
    
      - Configurazione della normalizzazione telefonica del server rubrica
    
      - Gestione del server rubrica dalla riga di comando

  - **** La gestione degli account utente che gestiscono gli account utente include le operazioni seguenti:   
    
      - Abilitazione degli account utente per Lync Server
    
      - Configurazione degli utenti di Lync Server tramite la procedura guidata
    
      - Configurazione delle singole proprietà degli account utente di Lync Server
    
      - Ricerca di utenti di Lync Server
    
      - Spostamento degli utenti di Lync Server
    
      - Eliminazione degli utenti di Lync Server

  - **Analisi dei file**   di log di Lync Server 2013 uno strumento molto utile, in genere usato per la risoluzione dei problemi, è lo strumento di registrazione di Lync Server 2013 descritto in dettaglio nell' [uso dello strumento di registrazione di Lync Server 2013](http://technet.microsoft.com/en-us/library/gg558599.aspx).

Poiché lo strumento di registrazione genera i file di log (in base al server), questi file di log possono essere visualizzati e analizzati usando lo strumento Snooper, se nel computer sono installati gli strumenti di Microsoft Office Server 12 Resource Kit. In caso contrario, i log possono essere analizzati anche usando un editor di testo, che è molto meno trasparente e più complesso rispetto all'uso dell'utilità Snooper.

Per visualizzare e analizzare i messaggi di protocollo

Quando si termina la sessione di debug nello strumento registrazione, fare clic su Analizza file di log per visualizzare i file di log usando lo strumento Snooper. È possibile analizzare i registri di protocollo per i componenti seguenti:

  - Lync Server SipStack (SIP)

  - Lync Server S4 (SIP)

  - Lync Server Conference signaling Traffic (C3P), tra cui MCU infra C3P e lo stato di attivazione C3P

  - Traffico per le conferenze Web di Lync Server (PSOM)

  - Client della piattaforma client per le comunicazioni unificate di Lync Server (UCCP)

  - Report sugli errori dal database di archiviazione

Per organizzare le prestazioni delle attività necessarie, vedere elenco di controllo delle operazioni necessario.

<div>


> [!IMPORTANT]  
> Per informazioni dettagliate sull'amministrazione e le procedure di gestione, vedere la Guida all'amministrazione di Microsoft Lync Server 2013.



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a>Criteri di backup (e ripristino) o impostazioni di configurazione

Lync Server 2013 consente di eseguire il backup e il ripristino dell'intero sistema. IIF di cui si vuole eseguire il backup (e quindi magari un giorno ripristinare) un singolo criterio o una singola raccolta di impostazioni di configurazione, recuperare i criteri appropriati e quindi reindirizzare l'oggetto al cmdlet Export-Clixml, che salva le informazioni sui criteri come file XML:

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

Ora puoi provare a usare RedmondClientPolicy e modificare molte delle impostazioni. Se invece si decide di ripristinare il vecchio criterio, immettere:

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

Tieni presente che questo approccio funzionerà per la maggior parte dei criteri e delle impostazioni, ma non funzionerà con alcuni degli elementi più complessi, ovvero gli elementi che contengono più oggetti secondari, ad esempio le impostazioni di configurazione del routing, che contengono molte route vocali separate.

</div>

</div>

<span> </span>

</div>

</div>

</div>

