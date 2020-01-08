---
title: 'Lync Server 2013: installazione di Lync Server 2013 Management Pack'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fea443225744bfd0d0e2dfa90a317ffa4cc890ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a>Installazione dei Management Pack di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

Di per sé, System Center Operations Manager è in grado di monitorare solo una piccola parte del sistema operativo Windows. È tuttavia possibile estendere le funzionalità di System Center Operations Manager installando Management Pack, un software che detta gli elementi che System Center Operations Manager può monitorare, incluso il monitoraggio degli elementi e la modalità di visualizzazione degli avvisi attivato e segnalato. Microsoft Lync Server 2013 include due Management Pack di System Center Operations Manager che fornisce le funzionalità seguenti:

  - Il componente e User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tiene traccia dei problemi di Lync Server registrati nei registri eventi, registrati da contatori delle prestazioni oppure registrati nei record dettagli chiamata (CDR) o nella qualità dell'esperienza (QoE) database. Per problemi critici, System Center Operations Manager può essere configurato per informare immediatamente gli amministratori tramite posta elettronica, messaggio istantaneo o messaggistica SMS (Short Message Service). SMS è la tecnologia usata per inviare SMS da un dispositivo mobile a un altro.
    
    <div>
    

    > [!NOTE]  
    > Per altre informazioni sulla configurazione della notifica di Operations Manager, vedere Configurazione della notifica in TechNet <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>Library at.

    
    </div>

  - Il Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) verifica in modo proattivo i componenti principali di Lync Server, ad esempio l'accesso al sistema, lo scambio di messaggi istantanei o l'esecuzione di chiamate a un telefono che si trova nel telefono con commutazioni pubbliche rete (PSTN). Questi test vengono eseguiti usando i cmdlet di transazione sintetica di Lync Server. Ad esempio, il cmdlet **Test-CsIM** viene usato per simulare una conversazione di messaggistica istantanea tra una coppia di utenti di test. Se la conversazione di messaggistica simulata non riesce, verrà generato un avviso.

I due Management Pack inclusi in Lync Server 2013 includono un numero elevato di miglioramenti nei Management Pack usati con Microsoft Lync Server 2010. Ad esempio, il pacchetto di gestione dei componenti di Lync Server 2013 non si limita a monitorare Lync Server stesso. Oltre a monitorare i registri eventi e i contatori delle prestazioni per Lync Server, il Management Pack del componente può anche tenere traccia delle prestazioni e inviare avvisi per elementi cruciali, ad esempio:

  - **Gli avvisi di Internet Information Services (IIS)**   verranno emessi se Internet Information Services è offline. Questo è importante perché i servizi Web di Lync Server si basano su IIS.

  - ****   Gli avvisi per l'uso del processo verranno emessi se le risorse di sistema, ad esempio la memoria disponibile, iniziano a funzionare in basso. Questi avvisi verranno emessi anche se Lync Server non è responsabile dell'uso elevato del sistema.

  - **Gli avvisi sugli eventi**   di errore del computer verranno emessi in caso di problemi hardware o software che minacciano la redditività di un server. Ad esempio, gli amministratori di Lync Server verranno informati se un server sembra essere in pericolo di un errore del disco rigido.

I nuovi Management Pack includono anche report avanzati. I nuovi report per Lync Server 2013 includono:

  - **Report disponibilità scenario finale**   questo report descrive in dettaglio la disponibilità/uptime dei servizi principali di Lync Server, ad esempio registrazione o presenza.

  - **Report capacità con**   le informazioni sui contatori delle prestazioni, questo report Mostra le tendenze per i componenti di sistema, ad esempio la disponibilità della memoria e l'uso del processore

  - **Report componente questo**   report elenca i generatori di avvisi principali raggruppati in base al componente Lync Server.

Oltre a questi report predefiniti, i Management Pack per Lync Server 2013 segnalano automaticamente gli avvisi sia per l'affidabilità delle chiamate (metriche misurate in base alla registrazione dei dettagli delle chiamate) che per gli Stati QoE (metriche misurate in base alla qualità dell'esperienza). Se è stata abilitata la registrazione dei dettagli delle chiamate, è possibile esaminare gli avvisi di affidabilità delle chiamate completando la procedura seguente dalla console di System Center Operations Manager:

  - Espandi **monitoraggio**, Espandi **Microsoft Lync Server 2013 Health**, Espandi l' **affidabilità delle chiamate e la qualità degli elementi multimediali**e quindi fai clic su **affidabilità chiamata**.

Per visualizzare gli avvisi relativi alla qualità dell'esperienza, eseguire questa procedura dalla console di System Center Operations Manager:

  - Espandi **monitoraggio**, Espandi **Microsoft Lync Server 2013 Health**, Espandi l' **affidabilità delle chiamate e la qualità degli elementi multimediali**e quindi Espandi **qualità multimediale**.

I Management Pack per Lync Server 2013 ora usano l'individuazione a livello di computer anziché il meccanismo di individuazione centralizzato usato in Microsoft Lync Server 2010. Questo significa che ogni agente del centro di sistema si rivela in sostanza e ne segnala l'esistenza al server di gestione centrale. L'uso dell'individuazione a livello di computer semplifica l'amministrazione dell'infrastruttura del centro di sistema e consente anche diverse versioni di Lync Server Management Pack, ad esempio Management Pack per Lync Server 2010 e Management Pack per Lync Server 2013, per coesistere.

</div>

<span> </span>

</div>

</div>

</div>

