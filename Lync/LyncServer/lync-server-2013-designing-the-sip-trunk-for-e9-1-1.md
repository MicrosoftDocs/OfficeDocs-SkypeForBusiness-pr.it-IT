---
title: 'Lync Server 2013: progettazione del trunk SIP per il servizio E9-1-1'
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
ms.openlocfilehash: 920eecbdb456e3b643da9f935e2586dea7e6e165
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a>Progettazione del trunk SIP per il servizio E9-1-1 in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-03_

Lync Server utilizza trunk SIP per connettere una chiamata di emergenza al provider di servizi E9-1-1. È possibile configurare trunk SIP per i servizi di emergenza per il servizio E9-1-1 in un sito centrale, in più siti centrali o in ogni sito di succursale. Tuttavia, se il collegamento WAN tra il sito del chiamante e il sito che ospita il trunk SIP del servizio di emergenza non è disponibile, una chiamata effettuata da un utente nel sito disconnesso avrà bisogno di un record di utilizzo telefonico speciale nel criterio vocale dell'utente che instraderà la chiamata al ECRC tramite il gateway PSTN (Public Switched Telephone Network). Lo stesso vale se i limiti di chiamata simultanei del controllo di ammissione di chiamata sono attivati.

<div>


> [!NOTE]  
> Esistono due modi per implementare un trunk SIP in un ambiente Lync Server: 
> <UL>
> <LI>
> <P>Utilizzare i Mediation Server multihomed che utilizzano le interfacce indirizzate al pubblico verso l'esterno per comunicare con il provider trunk SIP.</P>
> <LI>
> <P>Utilizzare un session border controller (SBC) locale per fornire un punto di delimitazione sicuro tra i Mediation Server e i servizi del provider del trunk SIP.</P></LI></UL>Se si sceglie il secondo metodo, accertarsi che la marca e il modello SBC scelti siano stati certificati e supporti il passaggio dei dati di posizione del formato dell'oggetto (PIDF-LO) dei dati sulla presenza come parte del relativo invito SIP. In caso contrario, le chiamate arriveranno al provider di servizi di emergenza privato delle informazioni sulla posizione. Per informazioni dettagliate sulle SBCs certificate, vedere "Infrastructure qualified for Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A>" all'indirizzo.<BR>I provider di servizi E9-1-1 forniscono l'accesso a una coppia di SBCs per la ridondanza. È necessario prendere diverse decisioni in merito alla topologia di Mediation Server e alla configurazione del routing delle chiamate. Si tratterà sia di SBCs come peer uguali che di utilizzare il routing round robin per le chiamate tra di essi oppure si designa un SBC come primario e l'altro come secondario?



</div>

Per informazioni dettagliate sulla distribuzione di un trunk SIP in Lync Server, vedere [come implementare il trunking SIP in Lync server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md). Le domande seguenti consentiranno di decidere come distribuire i trunk SIP per il servizio E9-1-1.

  - **È necessario distribuire il trunk SIP su una connessione Internet dedicata affittata o condivisa?**  
    È importante che le chiamate di emergenza si connettano sempre. Una linea dedicata fornisce una connessione che non verrà interrotta da altro traffico sulla rete e fornisce la possibilità di implementare la qualità del servizio (QoS). Tenere presente che se si sta effettuando la connessione a provider di servizi di emergenza tramite Internet pubblico ed è necessario garantire la riservatezza delle chiamate di emergenza, è necessaria la crittografia IPSec.

<!-- end list -->

  - **La distribuzione di E9-1-1 è progettata per la tolleranza di emergenza?**  
    Poiché si tratta di una soluzione di emergenza, è importante una resilienza. Distribuire i Mediation Server primari e secondari e i trunk SIP nei percorsi con tolleranza di emergenza. È consigliabile distribuire il Mediation Server primario più vicino agli utenti che supportano e instradare le chiamate di failover tramite il Mediation Server secondario (che si trova in una posizione geografica diversa).

<!-- end list -->

  - **È necessario distribuire un trunk SIP separato per ogni succursale?**  
    In Lync Server sono disponibili diverse strategie per la gestione della resilienza vocale nelle succursali, tra cui: una rete di dati resilienti, la distribuzione di un trunk SIP in ogni branch o la pressione delle chiamate verso il gateway locale durante le interruzioni. Per ulteriori informazioni, vedere [trunking SIP del sito di succursale in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).

<!-- end list -->

  - **Il controllo di ammissione di chiamata è abilitato?**  
    Lync Server non gestisce le chiamate di emergenza in modo diverso rispetto a una normale chiamata. Per questo motivo, la gestione della larghezza di banda o il controllo di ammissione di chiamata (CAC) può avere un impatto negativo su una configurazione di E9-1-1. Le chiamate di emergenza verranno bloccate o instradate al gateway PSTN locale se un CAC è abilitato e il limite configurato viene superato su un collegamento in cui vengono instradate le chiamate di emergenza. Come indicato in precedenza in questo argomento, tali chiamate non disporranno di dati di posizione e devono essere instradate manualmente al ECRC.

</div>

<span> </span>

</div>

</div>

</div>

