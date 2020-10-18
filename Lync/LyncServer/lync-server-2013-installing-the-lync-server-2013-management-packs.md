---
title: 'Lync Server 2013: installazione dei Lync Server 2013 Management Pack'
description: 'Lync Server 2013: installazione dei Lync Server 2013 Management Pack.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbb50146474211c12dbd95801ed2b20f6bbfd8c9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573832"
---
# <a name="installing-the-lync-server-2013-management-packs"></a>Installazione dei Management Pack di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

Da solo, System Center Operations Manager è in grado di monitorare solo una piccola parte del sistema operativo Windows. Tuttavia, è possibile estendere le funzionalità di System Center Operations Manager installando Management Pack, software che determina quali elementi possono essere monitorati dal System Center Operations Manager, includendo il modo in cui devono essere monitorati gli elementi e il modo in cui devono essere attivati e segnalati gli avvisi. Microsoft Lync Server 2013 include due Management Pack di System Center Operations Manager che forniscono le funzionalità seguenti:

  - Il componente e l'User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tiene traccia dei problemi di Lync Server registrati nei registri eventi, registrati dai contatori delle prestazioni o registrati nei database di registrazione dettagli chiamata (CDR) o in qualità di esperienza (QoE). Per i problemi critici, System Center Operations Manager può essere configurato per informare immediatamente gli amministratori tramite messaggi di posta elettronica, messaggi istantanei o SMS (Short Message Service). La tecnologia SMS viene utilizzata per inviare messaggi di testo da un dispositivo mobile a un altro.
    
    <div>
    

    > [!NOTE]  
    > Per ulteriori informazioni sulla configurazione della notifica di Operations Manager, vedere Configuring Notification in the TechNet Library at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A> .

    
    </div>

  - Il Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) verifica in modo proattivo i componenti chiave di Lync Server, ad esempio l'accesso al sistema, lo scambio di messaggi istantanei o la chiamata a un telefono che si trova nella rete PSTN (Public Switched Telephone Network). Questi test vengono eseguiti utilizzando i cmdlet per le transazioni sintetiche di Lync Server. Il cmdlet **Test-CsIM** ad esempio viene utilizzato per simulare una conversazione istantanea tra due utenti di test. Se questa conversazione simulata ha esito negativo, verrà generato un avviso.

I due Management Pack inclusi in Lync Server 2013 includono un numero elevato di miglioramenti rispetto ai Management Pack utilizzati con Microsoft Lync Server 2010. Ad esempio, il Lync Server 2013 Component Management Pack non è limitato al monitoraggio di Lync Server stesso. Oltre a monitorare i registri eventi e i contatori delle prestazioni per Lync Server, il Management Pack del componente può anche tenere conto delle prestazioni e inviare avvisi per gli elementi cruciali, ad esempio:

  - **Internet Information Services (IIS)**     Gli avvisi verranno emessi se Internet Information Services non è in linea. Questo è importante perché i servizi Web di Lync Server si basano su IIS.

  - **Utilizzo**     del processo Gli avvisi verranno emessi se le risorse di sistema, ad esempio la memoria disponibile, cominciano a funzionare in basso. Questi avvisi verranno emessi anche se Lync Server non è responsabile dell'utilizzo del sistema elevato.

  - Eventi di errore del **computer**     Gli avvisi verranno emessi nel caso di un problema hardware o software che minacci la redditività di un server. Ad esempio, gli amministratori di Lync Server riceveranno una notifica se un server sembra rischiare di riscontrare un errore del disco rigido.

I nuovi Management Pack inoltre offrono funzionalità di segnalazione avanzate. I nuovi rapporti per Lync Server 2013 includono:

  - Report di disponibilità dello **scenario end to end**     Questo rapporto descrive in dettaglio la disponibilità/tempo di uptime per i servizi chiave di Lync Server, ad esempio la registrazione o la presenza.

  - **Rapporto capacità**     Utilizzando le informazioni sui contatori delle prestazioni, questo rapporto illustra le tendenze per i componenti di sistema, ad esempio la disponibilità della memoria e l'utilizzo del processore

  - **Report componente**     In questo report sono elencati i generatori di avvisi principali raggruppati in base al componente Lync Server.

Oltre a questi rapporti predefiniti, i Management Pack per Lync Server 2013 segnalano automaticamente gli avvisi per l'affidabilità delle chiamate (metriche misurate tramite registrazione dettagli chiamata) e gli Stati QoE (metriche misurate in base alla qualità dell'esperienza). Se è stata abilitata la registrazione dettagli chiamata, è possibile esaminare gli avvisi relativi all'affidabilità delle chiamate eseguendo la procedura seguente dalla console di System Center Operations Manager:

  - Espandere **Monitoring**, **Microsoft Lync Server 2013 Health** e **Call Reliability and Media Quality** e quindi fare clic su **Call Reliability**.

Per visualizzare gli avvisi relativi alla qualità delle esperienze, eseguire questa procedura dalla console di System Center Operations Manager:

  - Espandere **Monitoring**, **Microsoft Lync Server 2013 Health**, **Call Reliability and Media Quality** e quindi **Media Quality**.

I Management Pack per Lync Server 2013 ora utilizzano l'individuazione a livello di computer invece del meccanismo di individuazione centrale utilizzato in Microsoft Lync Server 2010. Questo significa che ogni agente del centro di sistema si riscoprirà e ne riferirà la presenza al server di gestione centrale. L'utilizzo dell'individuazione a livello di computer semplifica l'amministrazione dell'infrastruttura del centro di sistema e consente anche diverse versioni dei Management Pack di Lync Server (ad esempio, i Management Pack per Lync Server 2010 e i Management Pack per Lync Server 2013) per coesistere.

</div>

<span> </span>

</div>

</div>

</div>

