---
title: 'Lync Server 2013: Topologie supportate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 295d0cfc212fcf09b9752c43e918861f49ec7a88
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a>Topologie supportate in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-01-14_

Lync Server 2013 supporta la distribuzione di siti in locale in un'organizzazione e l'integrazione di distribuzioni locali con distribuzioni di Lync Online, nota come distribuzione ibrida. In una distribuzione ibrida alcuni utenti vengono ospitati in locale e alcuni utenti sono ospitati online.

Per le distribuzioni locali, Lync Server 2013 supporta la distribuzione di uno o più siti che possono essere ridimensionati per soddisfare i requisiti di disponibilità e posizione elevati. È possibile strutturare questi siti e i relativi componenti in modo che soddisfino i requisiti di accesso e resilienza dell'organizzazione.

Una distribuzione locale di Lync Server 2013 è composta dalle opzioni seguenti:

  - La distribuzione deve includere almeno un sito centrale (noto anche come centro dati). Ogni sito centrale deve contenere almeno un pool Front-end Enterprise Edition o un server Standard Edition. Queste sono costituite dalle seguenti:
    
      - Pool Front end Enterprise Edition, costituito da uno o più server front-end (in genere, almeno due server front-end per la scalabilità) e un server back-end separato. Un pool Front-end può contenere un massimo di dodici server front-end. Il bilanciamento del carico è necessario per più server front-end. Per il traffico SIP, è consigliabile il bilanciamento del carico DNS, ma è supportato anche il bilanciamento del carico hardware. Se si usa il bilanciamento del carico DNS per il traffico SIP, è comunque necessario un servizio di bilanciamento del carico hardware per il traffico HTTP. È consigliabile il mirroring di SQL Server per l'elevata disponibilità dei database. Il database back-end richiede un'istanza distinta, ma è possibile collocare il database di archiviazione, il database di monitoraggio, il database di chat persistente e il database di conformità della chat persistente. Lync Server 2013 supporta l'uso di un cluster condiviso per le condivisioni file nella distribuzione. Per informazioni dettagliate sui requisiti di archiviazione del database, vedere [supporto software per database in Lync Server 2013](lync-server-2013-database-software-support.md). Per informazioni dettagliate sui requisiti di archiviazione dei file, vedere Supporto per l' [archiviazione dei file in Lync Server 2013](lync-server-2013-file-storage-support.md).
        
        <div>
        

        > [!IMPORTANT]  
        > Se si collocano i database di Lync Server, è consigliabile valutare tutti i fattori che possono influire sulla disponibilità e sulle prestazioni. Per verificare le funzionalità di failover, è consigliabile testare tutti i possibili scenari.

        
        </div>
    
      - Server Standard Edition, che include un database SQL Server Express collocato.

  - La distribuzione può anche avere uno o più siti di succursale associati a un sito centrale.

In questa sezione vengono descritti i siti e i componenti di una distribuzione di Lync Server 2013. Per informazioni dettagliate sul sito, la topologia e la pianificazione dei componenti di Lync Server 2013, vedere [nozioni di base sulla topologia prima della pianificazione di Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) e delle topologie [di riferimento in Lync Server 2013](lync-server-2013-reference-topologies.md) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'integrazione dei componenti delle versioni precedenti, vedere [percorsi di migrazione supportati e scenari di coesistenza in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).

<div>


> [!NOTE]  
> I pool allungati non sono supportati per i ruoli server front-end, Edge, Mediation e Director.



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a>Topologie e componenti del sito centrale (locale)

Anche se la topologia di un sito centrale deve includere un pool Front-end o un server Standard Edition, ogni sito centrale può contenere anche le operazioni seguenti:

  - Più pool Front-End, che possono essere nello stesso dominio o in domini diversi. Tuttavia, tutti i server front-end in un pool Front-end e il server back-end per il pool devono essere nello stesso dominio.

  - Più server Standard Edition.

  - Office Web Apps Server, usato con le applicazioni Web di Office in Lync Server 2013 per gestire la condivisione e il rendering delle presentazioni di Microsoft PowerPoint.

  - Edge Server o pool di Edge nella rete perimetrale, se si vuole che la distribuzione supporti i partner federati, la connettività di messaggistica istantanea pubblica, un gateway XMPP (Extensible Messaging and Presence Protocol), l'accesso degli utenti remoti, la partecipazione di un utente anonimo alle riunioni, o messaggistica unificata di Exchange. Non è possibile collocare qualsiasi altro ruolo del server con un server perimetrale. È consigliabile supportare il bilanciamento del carico DNS, se necessario, ma anche il bilanciamento del carico hardware. L'interfaccia perimetrale interna e l'interfaccia perimetrale esterna devono usare lo stesso tipo di bilanciamento del carico. Non è possibile usare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra. Per informazioni dettagliate sui requisiti di bilanciamento del carico e sul supporto, vedere [pianificazione per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) nella documentazione relativa alla pianificazione e [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione.

  - Mediation Server o pool, se si vuole supportare i servizi di conferenza telefonica aziendale o le conferenze telefoniche con accesso esterno in un pool Front-end presso il sito centrale. A seconda di come si distribuisce il supporto VoIP aziendale, è possibile collocare il Mediation Server in un pool Front-End (impostazione predefinita) oppure distribuire un server di mediazione autonomo o un pool. È possibile usare il bilanciamento del carico del DNS, dell'hardware o dell'applicazione (se necessario) per distribuire il traffico da un peer del gateway del pool di Mediation Server, incluso un gateway PSTN, un IP-PBX o un SBC. Per informazioni dettagliate sulla pianificazione della topologia di Mediation Server appropriata, vedere [linee guida per la distribuzione di Mediation Server in Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) nella documentazione relativa alla pianificazione.

  - Server di chat persistente, se si vuole consentire agli utenti di partecipare a conversazioni multiparte, basate su argomenti che persistono nel tempo. Per ottenere maggiore capacità e maggiore affidabilità, la topologia può includere più computer che eseguono il server di chat persistente. Non è possibile collocare il server di chat persistente con altri ruoli del server in un pool aziendale. È tuttavia possibile collocare il server di chat persistente in un server Standard Edition. La chat persistente richiede un database e, se implementi la conformità della chat persistente, un database di conformità della chat persistente, ma i database possono essere collocati nel database di archiviazione, nel database di monitoraggio o nel server back-end di un'edizione aziendale Pool Front-end. Per informazioni dettagliate sulla pianificazione della topologia del server di chat persistente appropriata, vedere [pianificazione del server di chat persistente in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) nella documentazione relativa alla pianificazione.

  - Monitoraggio, se si vuole supportare la raccolta di dati per la qualità audio/video (QoE) e la registrazione dei dettagli delle chiamate (CDR) per le conferenze VoIP aziendale e A/V nella distribuzione. Facoltativamente, è possibile installare Microsoft System Center Operations Manager (in precedenza Microsoft Operations Manager), che usa il monitoraggio dei dati CDR e QoE per generare avvisi in tempo reale che mostrano lo stato di affidabilità delle chiamate e la qualità dei contenuti multimediali. Il monitoraggio, quando viene distribuito, è collocato nei server front-end o in un server Standard Edition. Il monitoraggio richiede un database, ma il database può essere collocato nel database di archiviazione, nel database di chat persistente, nel database di conformità della chat persistente o nel server back-end di un pool di front-end Enterprise Edition.

  - Archiviazione, se si vuole archiviare le comunicazioni di messaggistica istantanea e il contenuto della riunione (per motivi di conformità) nella distribuzione. L'archiviazione, quando viene distribuita, è collocata nei server front-end o in un server Standard Edition. Lo spazio di archiviazione richiede la distribuzione di un database di archiviazione o l'integrazione con lo spazio di archiviazione di Exchange 2013. Se si usano entrambi, che è noto come *modalità mista*, lo spazio di archiviazione di Exchange 2013 viene usato per archiviare i dati di archiviazione per gli utenti residenti in Exchange 2013 e il database di archiviazione viene usato per archiviare i dati per tutti gli altri utenti della distribuzione. Se è necessario un database di archiviazione, il database può essere collocato nel database di monitoraggio, nel database di chat persistente, nel database di conformità della chat persistente o nel server back-end di un pool Front-end. Per informazioni dettagliate sulla pianificazione della topologia di archiviazione appropriata, vedere [pianificazione dell'archiviazione in Lync Server 2013](lync-server-2013-planning-for-archiving.md) nella documentazione relativa alla pianificazione.

  - Pool di Director o Director, se si vuole semplificare la resilienza e il reindirizzamento delle richieste degli utenti di Lync Server 2013 al pool Home dell'utente, che può essere un pool di front-end Enterprise Edition o un server Standard Edition. È consigliabile distribuire un pool di Director o Director in ogni sito centrale che supporta l'accesso degli utenti esterni e in ogni sito centrale in cui vengono distribuiti uno o più pool di front-end. Ogni pool di Director può contenere un massimo di dieci direttori. Un amministratore non può essere collocato in un altro ruolo del server. Per informazioni dettagliate sulla pianificazione della topologia di Director appropriata, vedere [scenari per il Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) nella documentazione relativa alla pianificazione.

  - Proxy inverso, che non è un componente 2013 di Lync Server, ma è obbligatorio se si vuole supportare la condivisione di contenuto Web per gli utenti federati o per supportare il traffico di mobilità. Non è possibile collocare un server proxy inverso con qualsiasi ruolo del server Lync Server 2013, ma è possibile implementare il supporto del proxy inverso per una distribuzione di Lync Server 2013 configurando il supporto di un server proxy inverso esistente nell'organizzazione usato per altri applicazioni. Per informazioni dettagliate sui server proxy inverso, vedere [configurazione dei server proxy inversa per Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) nella documentazione relativa alla distribuzione.

<div>


> [!NOTE]  
> In Lync Server 2013, i servizi di conferenza A/V, il monitoraggio e l'archiviazione vengono eseguiti nei server front-end e non sono più ruoli server distinti.



</div>

Tutti i pool Front-end e i server Standard Edition distribuiti in un sito centrale condividono una delle operazioni seguenti distribuite per il sito centrale:

  - Pool di Director o Director

  - Mediation Server o pool autonomo

  - Server Office Web Apps

  - Edge Server o pool di Edge

  - Server o pool di chat persistente

  - Monitoraggio

  - Archiviazione

<div>


> [!NOTE]  
> Se si vuole supportare l'integrazione della messaggistica unificata di Exchange 2013, è possibile implementare un server Messaggistica unificata di Exchange con la distribuzione di Lync Server 2013, ma non è un componente del sito di Lync Server 2013.



</div>

Più siti centrali possono anche condividere una delle operazioni seguenti distribuite in un unico sito centrale:

  - Mediation Server o pool autonomo

  - Edge Server o pool di Edge

  - Server o pool di chat persistente

  - Archiviazione

  - Monitoraggio

<div>


> [!NOTE]  
> Un server di messaggistica unificata di Exchange può essere implementato con la distribuzione di Lync Server 2013 e condiviso da più siti centrali, ma non è un componente del sito di Lync Server 2013.



</div>

Per informazioni dettagliate sui ruoli e le funzionalità del server Lync Server 2013, vedere ruoli del server [in Lync server 2013](lync-server-2013-server-roles.md) nella documentazione relativa alla pianificazione.

Per un riepilogo del supporto della collocazione dei server di Lync Server 2013, vedere [collocazione del server supportata in Lync server 2013](lync-server-2013-supported-server-collocation.md).

Oltre ai ruoli e alle funzionalità del server descritti in precedenza in questa sezione, Lync Server 2013 include componenti e opzioni aggiuntivi, che possono includere alcuni o tutti gli elementi seguenti:

  - Firewall

  - Gateway PSTN (se si distribuisce VoIP aziendale)

  - Server Messaggistica unificata di Exchange

  - Bilanciamento del carico DNS

  - Dispositivi di bilanciamento del carico hardware

  - Database di SQL Server

  - Condivisioni file

Per informazioni dettagliate su tutte le caratteristiche, i componenti e le opzioni di Lync Server 2013, vedere la documentazione relativa alla pianificazione.

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a>Topologie e componenti del sito di succursale (locale)

Un sito di succursale è associato a un sito centrale e ogni appliance Survivable Branch in un sito di succursale è associato a un pool di front end Enterprise Edition o a un server Standard Edition nel sito centrale associato. I siti di succursale dipendono dal sito centrale per la maggior parte delle loro funzionalità, quindi i componenti in un sito di succursale contengono solo i seguenti:

  - Un Survivable Branch Appliance, che combina un gateway PSTN (Public Switched Telephone Network) con alcune funzionalità di Lync Server. Un Mediation Server può essere collocato con l'istanza del registrar in Survivable Branch Appliance ed è possibile distribuire un server di mediazione autonomo o un pool di server di mediazione.

  - Un Survivable Branch Server, un server che utilizza Windows Server che include il software di registrazione e mediazione server di Lync Server 2013 installato.

  - Un gateway PSTN autonomo (non incluso in Survivable Branch Appliance) e un Mediation Server autonomo.

I requisiti per i Survivable Branch Server corrispondono ai requisiti per qualsiasi ruolo del server Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

