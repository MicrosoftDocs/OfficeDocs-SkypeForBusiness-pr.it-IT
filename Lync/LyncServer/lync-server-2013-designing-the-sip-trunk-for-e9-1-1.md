---
title: 'Lync Server 2013: progettare il trunk SIP per E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0ca42092b33632dbc7aed84808499b13ab0843c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a>Progettazione del trunk SIP per E9-1-1 in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-03_

Lync Server usa trunk SIP per connettere una chiamata di emergenza al provider di servizi E9-1-1. È possibile configurare trunk SIP per i servizi di emergenza per E9-1-1 in un sito centrale, in più siti centrali o in ogni sito di succursale. Tuttavia, se il collegamento WAN tra il sito del chiamante e il sito che ospita il trunk SIP del servizio di emergenza non è disponibile, la chiamata effettuata da un utente nel sito disconnesso avrà bisogno di un record di utilizzo telefonico speciale nel criterio vocale dell'utente che instraderà la chiamata al ECRC tramite il gateway PSTN (Public Switched Telephone Network) locale. Lo stesso vale se i limiti delle chiamate simultanee del controllo di ammissione di chiamata sono in vigore.

<div>


> [!NOTE]  
> Esistono due modi per implementare un trunk SIP in un ambiente Lync Server: 
> <UL>
> <LI>
> <P>Usare i server di mediazione multihome che usano le interfacce indirizzate verso l'esterno per comunicare con il provider trunk SIP.</P>
> <LI>
> <P>Usare un SBC (Session Border Controller) locale per garantire un punto di demarcazione sicuro tra i servizi Mediation Server e il provider trunk SIP.</P></LI></UL>Se si sceglie quest'ultimo metodo, assicurarsi che la creazione e il modello SBC scelti siano stati certificati e supporti il passaggio dei dati della posizione (PIDF-LO) del formato dei dati della presenza durante il SIP INVITE. In caso contrario, le chiamate arriveranno presso il provider di servizi di emergenza privato delle informazioni sulla posizione. Per informazioni dettagliate su Certified SBCs, vedere "Infrastructure qualified for Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>" at.<BR>I provider di servizi E9-1-1 forniscono l'accesso a una coppia di SBCs per la ridondanza. È necessario prendere diverse decisioni per quanto riguarda la topologia di Mediation Server e la configurazione del routing delle chiamate. Si tratterà sia di SBCs come peer uguali che di usare il routing round robin per le chiamate tra di essi oppure si designa un SBC come primario e l'altro come secondario?



</div>

Per informazioni dettagliate sulla distribuzione di un trunk SIP in Lync Server, vedere [come implementare il trunking SIP in Lync server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md). Le domande seguenti consentiranno di decidere come distribuire i trunk SIP per E9-1-1.

  - **È consigliabile distribuire il trunk SIP in una connessione Internet dedicata o affittata?**  
    È importante che le chiamate di emergenza si connettano sempre. Una linea dedicata offre una connessione che non verrà superata da altri traffici sulla rete e offre la possibilità di implementare la qualità del servizio (QoS). Tenere presente che, se ci si connette a provider di servizi di emergenza tramite Internet pubblico ed è necessario garantire la riservatezza delle chiamate di emergenza, è necessaria la crittografia IPSec.

<!-- end list -->

  - **La distribuzione E9-1-1 è progettata per la tolleranza ai disastri?**  
    Poiché si tratta di una soluzione di emergenza, la resilienza è importante. Distribuire i server di mediazione primari e secondari e i trunk SIP in posizioni tolleranti al disastro. È consigliabile distribuire il server di mediazione principale più vicino agli utenti supportati e instradare le chiamate di failover tramite il Mediation Server secondario (che si trova in una posizione geografica diversa).

<!-- end list -->

  - **È necessario distribuire un trunk SIP separato per ogni filiale?**  
    Lync Server offre diverse strategie per la gestione della resilienza vocale nelle filiali, tra cui: avere reti di dati resilienti, distribuire un trunk SIP in ogni ramo o spingere le chiamate verso il gateway locale durante le interruzioni. Per informazioni dettagliate, vedere [trunking SIP del sito di succursale in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).

<!-- end list -->

  - **Il controllo di ammissione delle chiamate (CAC) è abilitato?**  
    Lync Server non gestisce le chiamate di emergenza in modo diverso rispetto a una normale chiamata. Per questo motivo, la gestione della larghezza di banda o il controllo di ammissione delle chiamate (CAC) possono avere un impatto negativo su una configurazione E9-1-1. Le chiamate di emergenza verranno bloccate o indirizzate al gateway PSTN locale se è abilitato un CAC e il limite configurato viene superato in un collegamento in cui vengono instradate le chiamate di emergenza. Come indicato in precedenza in questo argomento, tali chiamate non avranno dati sulla posizione e dovranno essere indirizzate manualmente al ECRC.

</div>

<span> </span>

</div>

</div>

</div>

