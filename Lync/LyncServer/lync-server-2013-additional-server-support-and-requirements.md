---
title: 'Lync Server 2013: requisiti e supporto per i server aggiuntivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d8eb02f0cf178807c656520787024d79ab0f09b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a>Requisiti e supporto per i server aggiuntivi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-12-09_

Oltre al supporto software descritto nelle altre sezioni della documentazione relativa alla supportabilità, Lync Server 2013 presenta le limitazioni di supporto seguenti:

  - Lync Server 2013 supporta DNS (Domain Name System) e bilanciamento del carico hardware per ruoli del server specifici. Laddove appropriato, è inoltre supportato il bilanciamento del carico delle applicazioni per Mediation Server. Per informazioni dettagliate su quando utilizzare ciascun tipo di bilanciamento del carico, vedere la documentazione relativa alla pianificazione.

  - Lync Server 2013 utilizza il protocollo DLX (Distribution List Expansion Protocol) per espandere le liste di distribuzione. Questo protocollo specifica inoltre il metodo del servizio Web utilizzato per ottenere i membri di una lista di distribuzione. Microsoft Exchange Server supporta i gruppi dinamici che non dispongono di membri a essi assegnati in modo statico. In tali gruppi sono invece archiviate query valutate durante l'espansione del gruppo. Il protocollo DLX non supporta le liste di distribuzione dinamiche. Questa limitazione del DLX si applica a tutte le versioni di Lync Server.

  - Poiché la procedura guidata Abilita utenti non supporta la conversione automatica di caratteri non inglesi in un URI compatibile con SIP, è necessario modificare l'indirizzo SIP manualmente.

  - Per i server che eseguono il software antivirus, fare riferimento alle [esclusioni di analisi antivirus per Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) per le esclusioni dei virus consigliate e altre raccomandazioni relative alla sicurezza.

  - Se si utilizza IPsec, è consigliabile disabilitarlo negli intervalli di porte utilizzati per il traffico audio e video. Per informazioni dettagliate, vedere [IPSec Exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) nella documentazione relativa alla pianificazione.

  - Se nell'organizzazione è prevista un'infrastruttura di qualità del servizio (QoS), il sottosistema multimediale è progettato per essere utilizzato nell'infrastruttura esistente. Per informazioni dettagliate sull'implementazione di QoS, vedere [Managing Quality of Service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) nella documentazione relativa alle operazioni.

  - L'utilizzo del firewall del sistema operativo è supportato. Lync Server 2013 gestisce le eccezioni del firewall per il firewall del sistema operativo, tranne che per il software di database di Microsoft SQL Server. Per informazioni dettagliate sui requisiti del firewall di SQL Server, vedere la documentazione di SQL Server.

  - Le interfacce esterne utilizzate per implementare il supporto per l'accesso utente esterno devono trovarsi in una subnet distinta e *non* nella stessa rete delle interfacce interne.

  - La funzionalità XMPP di Lync Server 2013 è testata e supportata da Microsoft per la federazione di messaggistica istantanea con Google Talk. Per altri sistemi XMPP, contattare il fornitore di terze parti per verificare l'eventuale supporto della federazione con Lync Server 2013 e per indicazioni per la distribuzione o la risoluzione dei problemi.

  - Con la versione di Lync Server 2013 aggiornamenti cumulativi: luglio 2013, Lync Server 2013 ora supporta l'autenticazione a due fattori. Per ulteriori informazioni, vedere [autenticazione a due fattori in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).

  - La maggior parte dei server interni richiede un tipo di certificato definito come **autenticazione aperta** (OAuth). È necessario richiedere e assegnare un certificato OAuth durante la fase di **richiesta, installazione e assegnazione dei certificati** della distribuzione guidata di Lync Server. La dimensione minima per una chiave del certificato OAuth è di 1024 bit. È possibile che venga visualizzato un messaggio di avviso se si richiede un certificato con una lunghezza di chiave inferiore a 2048 bit. Per evitare potenziali problemi nel caso in cui venga applicata una lunghezza della chiave di 2048 anziché avvisata, è consigliabile utilizzare sempre una lunghezza di chiave di 2048 per i certificati OAuth.

  - Lync Server 2013 e Microsoft Exchange Server 2010 Service Pack 1 (SP1) operano con il supporto per gli algoritmi FIPS (Federal Information Processing Standard) 140-2 se i sistemi operativi Windows Server 2008 R2 sono configurati per l'utilizzo degli algoritmi FIPS 140-2 per crittografia del sistema. Per implementare il supporto FIPS, è necessario configurare ogni server su cui è in esecuzione Lync Server 2013 per supportarlo. Per informazioni dettagliate sugli algoritmi FIPS conformi e su come implementare il supporto FIPS, vedere l'articolo 811833 della Microsoft Knowledge Base "crittografia del sistema: utilizzare gli algoritmi FIPS conformi per la crittografia, l'hashing e la firma delle impostazioni di sicurezza in Windows XP e [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)nelle versioni successive di Windows all'indirizzo. Per informazioni dettagliate sul supporto e le limitazioni di FIPS 140-2 in Exchange 2010, vedere "Exchange 2010 SP1 and Support for FIPS compliant algorithms [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)" at.

Lync Server 2013 richiede l'installazione di altri software su componenti specifici prima o durante la distribuzione. Questo include il software disponibile con il sistema operativo, il software scaricabile e il software che viene installato automaticamente durante l'installazione di Lync Server 2013. Di seguito è disponibile un elenco di software aggiuntivo che può essere necessario:

  - Windows Update

  - Windows Identity Foundation

  - Microsoft .NET 4,5 Framework

  - Microsoft Visual C++ 2012 Redistributable
    
    <div>
    

    > [!NOTE]  
    > Microsoft Visual C++ 2012 Redistributable viene installato automaticamente quando si installa Lync Server 2013. Non è consigliabile installare e utilizzare altre versioni.

    
    </div>

  - URL Rewrite Module 2.0 Redistributable

  - Runtime formato Windows Media

  - Windows PowerShell versione 3,0

  - Plug-in del browser Microsoft Silverlight 4 (Silverlight 4.0.50524.0 o la versione più recente per il Pannello di controllo di Lync Server)

  - Strumenti di servizi di dominio Active Directory

Alcuni di questi requisiti software si applicano solo a ruoli del server o componenti specifici. Per informazioni dettagliate su questi requisiti software, vedere [Additional Software Requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) nella documentazione relativa alla pianificazione.

</div>

<span> </span>

</div>

</div>

</div>

