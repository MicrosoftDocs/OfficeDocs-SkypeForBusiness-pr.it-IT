---
title: Lync Server 2013 topologie supportate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2a74be867305f3e42d1e9e303baedbddd22f485
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a>Topologie supportate in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-01-14_

Lync Server 2013 supporta la distribuzione di siti in locale in un'organizzazione e l'integrazione di distribuzioni locali con distribuzioni di Lync Online, che è nota come distribuzione ibrida. In questo tipo di distribuzione alcuni utenti sono ospitati in locale, mentre altri online.

Per le distribuzioni locali, Lync Server 2013 supporta la distribuzione di uno o più siti che possono essere ridimensionati per soddisfare i requisiti di disponibilità elevata e posizione. È possibile strutturare tali siti e i relativi componenti in modo da soddisfare i requisiti di accesso e resilienza dell'organizzazione.

Una distribuzione locale di Lync Server 2013 è costituita dai seguenti elementi:

  - La distribuzione deve includere almeno un sito centrale, noto anche come data center. In ogni sito centrale deve essere contenuto almeno un pool Enterprise Edition Front End o un server Standard Edition, costituiti come indicato di seguito:
    
      - Pool Enterprise Edition Front End, costituito da uno o più Front End Server (in genere almeno due per la scalabilità) e un server back-end separato. Un pool Front end può contenere un massimo di dodici front end server. In presenza di più Front End Server è richiesto il bilanciamento del carico. Per il traffico SIP è consigliato il bilanciamento del carico DNS, ma è supportato anche il bilanciamento del carico hardware. Se si usa il bilanciamento del carico DNS per il traffico SIP, è comunque necessario un dispositivo di bilanciamento del carico hardware per il traffico HTTP. È consigliabile eseguire il mirroring di SQL Server per la disponibilità elevata dei database. Il database back-end richiede un'istanza separata, ma è possibile collocare insieme a esso il database di Archiviazione, il database di Monitoraggio, il database Persistent Chat e il database di Conformità Persistent Chat. Lync Server 2013 supporta l'utilizzo di un cluster condiviso per le condivisioni di file nella distribuzione. Per informazioni dettagliate sui requisiti di archiviazione dei database, vedere [database software support in Lync Server 2013](lync-server-2013-database-software-support.md). Per informazioni dettagliate sui requisiti di archiviazione dei file, vedere [file Storage Support in Lync Server 2013](lync-server-2013-file-storage-support.md).
        
        <div>
        

        > [!IMPORTANT]  
        > Se si installano i database di Lync Server, è consigliabile valutare tutti i fattori che possono influire sulla disponibilità e sulle prestazioni. Per verificare le capacità di failover, è consigliabile testare tutti gli scenari di failover.

        
        </div>
    
      - Server Standard Edition, che include un database di SQL Server Express collocato.

  - Nella distribuzione possono inoltre essere presenti uno o più siti di succursale associati a un sito centrale.

In questa sezione vengono descritti i siti e i componenti di una distribuzione di Lync Server 2013. Per informazioni dettagliate sul sito, la topologia e la pianificazione del componente di Lync Server 2013, vedere [nozioni di base sulla topologia che è necessario conoscere prima di pianificare Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) e le [topologie di riferimento in Lync Server 2013](lync-server-2013-reference-topologies.md) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'integrazione dei componenti delle versioni precedenti, vedere [supported Migration paths and Coesistence in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).

<div>


> [!NOTE]  
> I pool allungati non sono supportati per i ruoli front-end, Edge, Mediation e server Director.



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a>Topologie e componenti di un sito centrale (in locale)

Una topologia di un sito centrale deve includere un solo pool Front End o un solo server Standard Edition, tuttavia ogni sito centrale può includere anche gli elementi seguenti:

  - Più pool Front End, che possono trovarsi nello stesso dominio o in domini diversi. Tutti i Front End Server di un pool Front End e il relativo server back-end devono tuttavia trovarsi nello stesso dominio.

  - Più server Standard Edition.

  - Server Office Web Apps, utilizzato con Office Web Applications in Lync Server 2013 per gestire la condivisione e il rendering delle presentazioni di Microsoft PowerPoint.

  - Un server perimetrale o un pool di Edge nella propria rete, se si desidera che la distribuzione supporti i partner federati, la connettività per la messaggistica istantanea pubblica, un gateway XMPP (Extensible Messaging and Presence Protocol), l'accesso utente remoto, la partecipazione degli utenti anonimi alle riunioni, o messaggistica unificata di Exchange. Non è possibile collocare altri ruoli del server con un server perimetrale. È consigliabile usare il bilanciamento del carico DNS, se appropriato, ma è supportato anche il bilanciamento del carico hardware. L'interfaccia perimetrale interna e quella esterna devono utilizzare lo stesso tipo di bilanciamento del carico. Non è possibile utilizzare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra. Per informazioni dettagliate sui requisiti e il supporto per il bilanciamento del carico, vedere [Planning for External User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) nella documentazione relativa alla pianificazione e [distribuzione di accesso utente esterno in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione.

  - Mediation Server o pool, se si desidera supportare le conferenze telefoniche con accesso esterno o VoIP aziendale in un pool Front End nel sito centrale. A seconda del modo in cui si distribuisce il supporto VoIP aziendale, è possibile collocare il Mediation Server in un pool Front End (impostazione predefinita) oppure distribuire un server o un pool di Mediation autonomo. È possibile utilizzare il bilanciamento del carico DNS, hardware o applicazioni, se necessario, per distribuire il traffico da un peer gateway del pool di Mediation Server, tra cui un gateway PSTN, un IP-PBX o un SBC (Session Border Control) del trunk SIP. Per informazioni dettagliate sulla pianificazione della topologia del Mediation Server appropriato, vedere [Deployment Guidelines for Mediation Server in Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) nella documentazione relativa alla pianificazione.

  - Server Chat persistente, se si desidera che gli utenti siano in grado di partecipare a conversazioni a più parti, basate su argomenti che persistono nel tempo. Per offrire maggiore capacità e maggiore affidabilità, la topologia può includere più computer che eseguono il server Chat persistente. Non è possibile collocare il server Chat persistente con altri ruoli del server in un pool Enterprise. Tuttavia, è possibile collocare il server Chat persistente in un server Standard Edition. La chat persistente richiede un database e, se si implementa la conformità Persistent Chat, un database di conformità di chat persistente, ma i database possono essere collocati con il database di archiviazione, il database di monitoraggio o il server back-end di un'edizione Enterprise Pool Front end. Per informazioni dettagliate sulla pianificazione della topologia del server Chat persistente, vedere [Planning for Persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) nella documentazione relativa alla pianificazione.

  - Monitoraggio, se si desidera supportare la raccolta dati per la qualità audio/video percepita dagli utenti (QoE) e la registrazione dettagli chiamata per le conferenze audio/video e il VoIP aziendale nella distribuzione. Facoltativamente, è possibile installare Microsoft System Center Operations Manager (in precedenza Microsoft Operations Manager), in cui vengono utilizzati i dati di monitoraggio CDR e QoE per generare avvisi quasi in tempo reale che mostrano l'integrità dell'affidabilità delle chiamate e la qualità dei supporti. Quando viene distribuito, Monitoraggio viene collocato nei Front End Server o in un server Standard Edition. Monitoraggio richiede un database che può essere tuttavia collocato insieme al database di Archiviazione, al database Persistent Chat, al database di Conformità Persistent Chat o nel server back-end di un pool Enterprise Edition Front End.

  - Archiviazione, se si vuole archiviare le comunicazioni di messaggistica istantanea e il contenuto delle riunioni (per motivi di conformità) nella distribuzione. Quando viene distribuita, Archiviazione viene collocata nei Front End Server o in un server Standard Edition. L'archiviazione di archiviazione richiede la distribuzione di un database di archiviazione o l'integrazione con l'archiviazione di Exchange 2013. Se si utilizzano entrambi, ovvero la *modalità mista*, lo spazio di archiviazione di Exchange 2013 viene utilizzato per archiviare i dati di archiviazione per gli utenti ospitati in Exchange 2013 e il database di archiviazione viene utilizzato per archiviare i dati di tutti gli altri utenti della distribuzione. Se è richiesto un database di archiviazione, questo può essere collocato nel database di Monitoraggio, nel database Persistent Chat, nel database di Conformità Persistent Chat o nel server back-end di un pool Enterprise Edition Front End. Per informazioni dettagliate sulla pianificazione della topologia di archiviazione appropriata, vedere [Planning for archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) nella documentazione relativa alla pianificazione.

  - Server Director o del pool di server Director, se si desidera semplificare la resilienza e il reindirizzamento delle richieste degli utenti di Lync 2013 al pool di casa dell'utente, che può essere un pool Enterprise Edition front end o uno Standard Edition. È consigliabile distribuire un Director o un pool di server Director in ogni sito centrale che supporta l'accesso degli utenti esterni e in ogni sito centrale in cui vengono distribuiti uno o più pool Front End. Ogni pool di server Director può includere un massimo di dieci Director. Non è possibile collocare un Director con altri ruoli del server. Per informazioni dettagliate sulla pianificazione della topologia del Director appropriata, vedere [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) nella documentazione relativa alla pianificazione.

  - Proxy inverso, che non è un componente di Lync Server 2013, ma è obbligatorio se si desidera supportare la condivisione di contenuto Web per gli utenti federati o per il supporto del traffico per dispositivi mobili. Non è possibile collocare un server proxy inverso con qualsiasi ruolo del server Lync Server 2013, ma è possibile implementare il supporto del proxy inverso per una distribuzione di Lync Server 2013 configurando il supporto su un server proxy inverso esistente nell'organizzazione utilizzato per altri applicazioni. Per informazioni dettagliate sui server proxy inversi, vedere [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) nella documentazione relativa alla distribuzione.

<div>


> [!NOTE]  
> In Lync Server 2013, A/V Conferencing, monitoraggio e archiviazione eseguiti nei front end server e non sono più ruoli del server distinti.



</div>

Tutti i pool Front End e i server Standard Edition distribuiti nel sito centrale condividono gli elementi seguenti distribuiti per il sito centrale:

  - Director o pool di server Director

  - Mediation Server autonomo o pool di Mediation Server

  - server Office Web Apps

  - Server perimetrale o pool di server perimetrali

  - Pool o server Persistent Chat

  - Monitoraggio

  - Archiviazione

<div>


> [!NOTE]  
> Un server di messaggistica unificata di Exchange può essere implementato con la distribuzione di Lync Server 2013 se si desidera supportare l'integrazione della messaggistica unificata di Exchange 2013, ma non è un componente del sito Lync Server 2013.



</div>

Più siti centrali possono inoltre condividere gli elementi seguenti distribuiti in un sito centrale:

  - Mediation Server autonomo o pool di Mediation Server

  - Server perimetrale o pool di server perimetrali

  - Pool o server Persistent Chat

  - Archiviazione

  - Monitoraggio

<div>


> [!NOTE]  
> Un server di messaggistica unificata di Exchange può essere implementato con la distribuzione di Lync Server 2013 e condiviso da più siti centrali, ma non è un componente del sito Lync Server 2013.



</div>

Per informazioni dettagliate sui ruoli e le funzionalità del server Lync Server 2013, vedere [Server Roles in Lync server 2013](lync-server-2013-server-roles.md) nella documentazione relativa alla pianificazione.

Per un riepilogo del supporto della collocazione dei server di Lync Server 2013, vedere [supported server Collocation in Lync server 2013](lync-server-2013-supported-server-collocation.md).

Oltre ai ruoli del server e alle funzionalità descritti in precedenza in questa sezione, Lync Server 2013 include componenti e opzioni aggiuntivi, che possono includere alcuni o tutti gli elementi seguenti:

  - Firewall

  - Gateway PSTN (con la distribuzione di VoIP aziendale)

  - Server Messaggistica unificata di Exchange

  - Bilanciamento del carico DNS

  - Dispositivi di bilanciamento del carico hardware

  - Database di SQL Server

  - Condivisioni file

Per informazioni dettagliate su tutte le funzionalità, i componenti e le opzioni di Lync Server 2013, vedere la documentazione relativa alla pianificazione.

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a>Topologie e componenti di un sito di succursale (in locale)

Un sito di succursale è associato a un sito centrale e ogni Survivable Branch Appliance di un sito di succursale è associato a un pool Enterprise Edition Front End o a un server Standard Edition del sito centrale associato. Poiché i siti di succursale dipendono dal sito centrale per la maggior parte delle funzionalità, i componenti di un sito di succursale includono solo gli elementi seguenti:

  - Survivable Branch Appliance, che combina un gateway PSTN (Public Switched Telephone Network) con alcune funzionalità di Lync Server. Un Mediation Server può essere collocato con l'istanza del servizio di registrazione nel Survivable Branch Appliance ed è possibile distribuire un Mediation Server autonomo o un pool di Mediation Server.

  - Survivable Branch Server, che è un server che esegue Windows Server in cui è installato Lync Server 2013 registrar e il software Mediation Server.

  - Un gateway PSTN autonomo (che non fa parte del Survivable Branch Appliance) e un Mediation Server autonomo.

I requisiti per i Survivable Branch Server sono gli stessi dei requisiti per qualsiasi ruolo del server Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

