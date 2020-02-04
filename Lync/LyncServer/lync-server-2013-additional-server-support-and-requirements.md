---
title: 'Lync Server 2013: Requisiti e supporto per i server aggiuntivi'
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
ms.openlocfilehash: 3f111b80bc88b632ff1020f45e899f220edeb7d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a>Requisiti e supporto per i server aggiuntivi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-12-09_

Oltre al supporto software descritto nelle altre sezioni della documentazione relativa alla supportabilità, Lync Server 2013 ha le seguenti limitazioni di supporto:

  - Lync Server 2013 supporta il DNS (Domain Name System) e il bilanciamento del carico hardware per ruoli server specifici. Supporta anche il bilanciamento del carico delle applicazioni per Mediation Server, se necessario. Per informazioni dettagliate su quando usarle, vedere la documentazione relativa alla pianificazione.

  - Lync Server 2013 usa il protocollo DLX (Distribution List Expansion Protocol) per espandere le liste di distribuzione. Questo protocollo specifica anche il metodo di servizio Web usato per ottenere l'appartenenza a una lista di distribuzione. Microsoft Exchange Server supporta i gruppi dinamici a cui non sono assegnati membri in modo statico. Archiviano invece le query che vengono valutate quando il gruppo viene espanso. DLX non supporta le liste di distribuzione dinamiche. Questa limitazione di DLX si applica a tutte le versioni di Lync Server.

  - La procedura guidata Abilita utente non supporta la conversione automatica di caratteri non inglesi in un URI conforme a SIP, quindi è necessario modificare manualmente l'indirizzo SIP.

  - Per i server che esegue il software antivirus, vedere [esclusioni della scansione antivirus per Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) per le esclusioni di virus suggerite e altre raccomandazioni relative alla sicurezza.

  - Se si usa IPsec, è consigliabile disabilitare IPsec sugli intervalli di porte usati per il traffico audio e video. Per informazioni dettagliate, vedere [Eccezioni IPsec in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) nella documentazione relativa alla pianificazione.

  - Se l'organizzazione usa un'infrastruttura QoS (Quality of Service), il sottosistema multimediale è progettato per funzionare all'interno di questa infrastruttura esistente. Per informazioni dettagliate sull'implementazione di QoS, vedere [gestione della qualità del servizio (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) nella documentazione Operations.

  - È supportato l'uso del firewall del sistema operativo. Lync Server 2013 gestisce le eccezioni del firewall per il firewall del sistema operativo, ad eccezione del software di database di Microsoft SQL Server. Per informazioni dettagliate sui requisiti di SQL Server firewall, vedere la documentazione di SQL Server.

  - Le interfacce esterne usate per implementare il supporto per l'accesso degli utenti esterni devono trovarsi in una subnet separata, *non* nella stessa rete delle interfacce interne.

  - La funzionalità XMPP di Lync Server 2013 è testata e supportata da Microsoft per la Federazione della messaggistica istantanea con Google Talk. Per qualsiasi altro sistema XMPP, contattare il fornitore di terze parti per verificare che supportino la Federazione con Lync Server 2013 e per eventuali suggerimenti per la distribuzione o la risoluzione dei problemi.

  - Con il rilascio degli aggiornamenti cumulativi di Lync Server 2013:2013 luglio, Lync Server 2013 ora supporta l'autenticazione a due fattori. Per altre informazioni, vedere [autenticazione a due fattori in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).

  - La maggior parte dei server interni richiede un tipo di certificato definito come **Open Authentication** (OAuth). È necessario richiedere e assegnare un certificato OAuth durante la **richiesta, installare e assegnare** la fase certificati della distribuzione guidata di Lync Server. La dimensione minima per una chiave di certificato OAuth è 1024 bit. Se si richiede un certificato con una lunghezza di chiave inferiore a 2048 bit, è possibile che venga visualizzato un avviso. Per evitare potenziali problemi se viene applicata una lunghezza di chiave di 2048 anziché avvisata, è consigliabile usare sempre una lunghezza di chiave di 2048 per i certificati OAuth.

  - Lync Server 2013 e Microsoft Exchange Server 2010 Service Pack 1 (SP1) funzionano con il supporto per gli algoritmi FIPS (Federal Information Processing Standard) 140-2 se i sistemi operativi Windows Server 2008 R2 sono configurati per l'uso degli algoritmi FIPS 140-2 per crittografia di sistema. Per implementare il supporto FIPS, è necessario configurare ogni server in cui è in esecuzione Lync Server 2013 per supportarlo. Per informazioni dettagliate sugli algoritmi conformi FIPS e su come implementare il supporto FIPS, vedere l'articolo 811833 della Microsoft Knowledge Base "crittografia sistema: usare gli algoritmi conformi a FIPS per la crittografia, l'hashing e la firma dell'impostazione di sicurezza in Windows XP e [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)nelle versioni successive di Windows at. Per informazioni dettagliate sul supporto e le limitazioni di FIPS 140-2 in Exchange 2010, vedere "Exchange 2010 SP1 e supporto per gli algoritmi di conformità [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)FIPS".

Lync Server 2013 richiede l'installazione di altri software su componenti specifici prima o durante la distribuzione. Questo include il software disponibile con il sistema operativo, il software scaricabile e il software che viene installato automaticamente durante l'installazione di Lync Server 2013. Di seguito è riportato un elenco di software aggiuntivo che può essere necessario:

  - Windows Update

  - Windows Identity Foundation

  - Microsoft .NET 4,5 Framework

  - Microsoft Visual C++ 2012 ridistribuibile
    
    <div>
    

    > [!NOTE]  
    > Microsoft Visual C++ 2012 Redistributable viene installato automaticamente durante l'installazione di Lync Server 2013. Non è consigliabile installare e usare altre versioni.

    
    </div>

  - Modulo di riscrittura URL versione 2,0 ridistribuibile

  - Runtime in formato Windows Media

  - Versione 3,0 di Windows PowerShell

  - Plug-in del browser di Microsoft Silverlight 4 (Silverlight 4.0.50524.0 o la versione più recente per il pannello di controllo di Lync Server)

  - Strumenti dei servizi di dominio Active Directory

Alcuni di questi requisiti software si applicano solo a specifici ruoli o componenti del server. Per informazioni dettagliate su questi requisiti software, vedere [requisiti software aggiuntivi per Lync Server 2013](lync-server-2013-additional-software-requirements.md) nella documentazione relativa alla pianificazione.

</div>

<span> </span>

</div>

</div>

</div>

