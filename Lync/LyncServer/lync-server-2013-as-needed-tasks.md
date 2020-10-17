---
title: 'Lync Server 2013: attività necessarie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98b4323374c9801ec07930941a0daa3635b04e43
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529543"
---
# <a name="as-needed-tasks-in-lync-server-2013"></a>Attività necessarie in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-08-18_

Eseguire le attività seguenti in base alle esigenze. Essi sono spesso anche coperti da procedure standard:

  - **Controllo completo della sicurezza   ** È possibile eseguire questa verifica regolarmente, in risposta a un aggiornamento o riprogettazione del sistema di messaggistica, o in risposta a una violazione della protezione tentata (o riuscita). La procedura può comportare l'analisi delle porte sui server e sui firewall, sulle verifiche delle correzioni di sicurezza e sui test di penetrazione di terze parti.

  - **Sostituire i certificati per la scadenza**     Controllare i certificati di Lync Server è una delle attività settimanali regolari e, nell'ambito della procedura, un amministratore deve disporre di un record di tutte le date di scadenza dei certificati. Questo record consente a un amministratore di creare una notifica quando un determinato certificato sta per essere scaduto e sostituito in base alle esigenze.

  - **Aggiornamento delle linee di base**     delle prestazioni Aggiornare le linee di base delle prestazioni dopo un aggiornamento o una modifica della configurazione. L'organizzazione può utilizzare le linee di base per misurare le modifiche alle prestazioni e rilevare i problemi che influiscono sulle prestazioni del sistema.

  - **Gestione del pool Enterprise**     La configurazione iniziale di pool Enterprise, server Standard Edition e qualsiasi altro server nell'ambiente dell'organizzazione sono state eseguite durante la distribuzione dei singoli server. La gestione dopo la distribuzione di server e pool per i server Standard Edition e i pool Enterprise include le attività seguenti:
    
      - Gestione dei Front End Server
    
      - Gestione delle conferenze Web
    
      - Gestione delle conferenze
    
      - Modifica delle credenziali dell'account di servizio
    
      - Gestione dei database
    
      - Avvio e arresto di servizi e disattivazione dei ruoli del server
    
      - Rimozione di server e ruoli del server, rimozione di pool e disattivazione di server e pool

  - **Gestione dell'utilizzo**     È possibile configurare Lync Server 2013 per fornire le funzionalità e le funzionalità più appropriate per l'organizzazione. Sono incluse le attività seguenti:
    
      - Gestione del supporto per le riunioni di Web Conferencing locali
    
      - Gestione dell'utilizzo di gruppi di distribuzione per l'invio di messaggi istantanei
    
      - Gestione di contatti, presenza e query
    
      - Configurazione del filtro delle versioni client
    
      - Configurazione del filtro di messaggistica istantanea intelligente
    
      - Configurazione dell'archiviazione, registrazione dettagli chiamata e conformità alle riunioni

  - **Gestione della connettività**     dei server perimetrali La gestione continua dei server e delle impostazioni necessarie per fornire la connettività esterna include gli elementi seguenti:
    
      - Gestione della connettività tra server interni e server perimetrali
    
      - Configurazione di interfacce e certificati interni ed esterni per server perimetrali
    
      - Gestione dell'accesso dei partner federati

  - **Amministrazione della rubrica**     L'amministrazione dei server della rubrica include gli elementi seguenti:
    
      - Configurazione della normalizzazione del telefono del server rubrica
    
      - Gestione del server della rubrica dalla riga di comando

  - **Gestione degli account utente**     La gestione degli account utente include gli elementi seguenti:
    
      - Abilitazione degli account utente per Lync Server
    
      - Configurazione degli utenti di Lync Server tramite la procedura guidata
    
      - Configurazione di singole proprietà dell'account utente di Lync Server
    
      - Ricerca di utenti di Lync Server
    
      - Spostamento degli utenti di Lync Server
    
      - Eliminazione degli utenti di Lync Server

  - **Analisi dei file**     di registro di Lync Server 2013 Uno strumento molto utile, generalmente utilizzato per la risoluzione dei problemi, è lo strumento di registrazione di Lync Server 2013 descritto in dettaglio nell' [utilizzo dello strumento di registrazione di Lync server 2013](https://technet.microsoft.com/library/gg558599.aspx).

Poiché lo strumento di registrazione genera file di registro (per ogni server), questi file di registro possono essere visualizzati e analizzati utilizzando lo strumento Snooper, se gli strumenti di Microsoft Office Server 12 Resource Kit sono installati nel computer. In caso contrario, i registri possono essere analizzati anche utilizzando un editor di testo, molto meno trasparente e più complesso rispetto all'utilizzo dell'utilità Snooper.

Per visualizzare e analizzare i messaggi di protocollo

Nello strumento di registrazione, dopo aver terminato la sessione di debug, fare clic su Analizza file di registro per visualizzare i file di registro utilizzando lo strumento Snooper. È possibile analizzare i registri di protocollo per i componenti seguenti:

  - Lync Server SipStack (SIP)

  - Lync Server S4 (SIP)

  - Lync Server Conferencing signaling Traffic (C3P), tra cui MCU infra C3P e Focus C3P

  - Traffico Web Conferencing di Lync Server (PSOM)

  - Client della piattaforma client per le comunicazioni unificate di Lync Server (UCCP)

  - Segnalazioni di errori dal database di archiviazione

Per facilitare l'organizzazione delle prestazioni delle attività necessarie, vedere As-Needed checklist Operations.

<div>


> [!IMPORTANT]  
> Per le procedure dettagliate per l'amministrazione e la gestione, vedere la Guida all'amministrazione di Microsoft Lync Server 2013.



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a>Criteri di backup (e ripristino) o impostazioni di configurazione

Lync Server 2013 consente di eseguire il backup e il ripristino dell'intero sistema. Se si desidera eseguire il backup (e quindi magari un giorno di ripristino) un singolo criterio o una singola raccolta di impostazioni di configurazione, recuperare il criterio appropriato e quindi eseguire il piping dell'oggetto al cmdlet Export-Clixml, che salva le informazioni sui criteri come file XML:

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

È ora possibile provare a utilizzare RedmondClientPolicy e modificare molte impostazioni. Se si decide invece di ripristinare i criteri obsoleti, immettere quanto segue:

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

Si noti che questo approccio funzionerà per la maggior parte dei criteri e delle impostazioni, ma non funzionerà con alcuni degli elementi più complessi, ovvero gli elementi che contengono più oggetti secondari, ad esempio le impostazioni di configurazione del routing, che contengono molte route vocali separate.

</div>

</div>

<span> </span>

</div>

</div>

</div>

