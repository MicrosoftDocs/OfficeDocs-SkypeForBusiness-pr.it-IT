---
title: Requisiti dell'infrastruttura di rete di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93e68a7aecd8c1390993d25d23668813cad0abbf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a>Requisiti dell'infrastruttura di rete per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-18_

La scheda della scheda di rete di ogni server nella topologia di Lync Server 2013 deve supportare almeno 1 Gigabit al secondo (Gbps). In generale, è consigliabile connettere tutti i ruoli del server nella topologia di Lync Server con una bassa latenza e una rete LAN (Local Area Network) di larghezza di banda elevata. Le dimensioni della rete LAN dipendono da quelle della topologia:

  - Nelle topologie standard Edition i server devono trovarsi in una rete che supporta 1 Gbps Ethernet o equivalente.

  - Nelle topologie del pool Front End, la maggior parte dei server deve trovarsi in una rete che supporta più di 1 Gbps, soprattutto quando si supportano le conferenze audio/video (A/V) e la condivisione di applicazioni.

È possibile supportare l'integrazione della rete PSTN (Public Switched Telephone Network) utilizzando linee T1/E1 o il trunking SIP.

<div>

## <a name="audiovideo-network-requirements"></a>Requisiti di rete audio/video

I requisiti di rete per audio/video (A/V) in una distribuzione di Lync Server includono quanto segue:

  - Se si sta distribuendo un singolo server perimetrale o un pool di Edge utilizzando il bilanciamento del carico DNS, è possibile configurare il firewall esterno come NAT. Non è possibile configurare il firewall interno come NAT. Per informazioni dettagliate su questi requisiti, vedere [Determine External a/V firewall and Port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) nella documentazione relativa alla pianificazione.
    
    <div>
    

    > [!IMPORTANT]  
    > Se si dispone di un pool di server perimetrali e si utilizza un dispositivo di bilanciamento del carico hardware, è necessario utilizzare gli indirizzi IP pubblici su ciascuno dei server perimetrali e non è possibile utilizzare il NAT per il pool o il gruppo del computer NAT (ad esempio, il firewall o un altro dispositivo di infrastruttura che NAT inbou traffico in uscita o ND). Per informazioni dettagliate, vedere <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Riepilogo delle porte-Edge consolidato in scala con i dispositivi di bilanciamento del carico hardware in Lync Server 2013</A> nella documentazione relativa alla pianificazione per l'accesso degli utenti esterni.

    
    </div>

  - Se nell'organizzazione è prevista un'infrastruttura di qualità del servizio (QoS), il sottosistema multimediale è progettato per essere utilizzato nell'infrastruttura esistente.

  - Se si utilizza IPSec (Internet Protocol security), è consigliabile disabilitarlo per gli intervalli di porte usati per il traffico A/V. Per informazioni dettagliate, vedere [IPSec Exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) nella documentazione relativa alla pianificazione.

Per garantire una qualità multimediale ottimale, eseguire le operazioni seguenti:

  - Effettuare il provisioning dei collegamenti di rete in modo da supportare la velocità effettiva di 65 kilobit al secondo (Kbps) per flusso audio e 500 Kbps per flusso video, se abilitati, durante i periodi di picco di utilizzo. Una sessione audio o video bidirezionale è costituita da due flussi.

  - Per far fronte a picchi imprevisti nel traffico al di sopra di questo livello e aumentare l'utilizzo nel tempo, gli endpoint multimediali di Lync Server possono adattarsi a diverse condizioni di rete e supportare carichi pari a tre volte la velocità effettiva (vedere il paragrafo precedente) per l'audio e il video, mentre ancora mantenere la qualità accettabile. Questa adattabilità non deve tuttavia lasciar supporre che venga supportata una rete sottodimensionata. In una rete sottoposta a provisioning, la capacità degli endpoint multimediali di Lync Server di gestire dinamicamente le diverse condizioni di rete, ad esempio la perdita temporanea di pacchetti elevati, è ridotta.

  - Per i collegamenti di rete in cui il provisioning è un'operazione estremamente costosa e difficile, potrebbe essere necessario valutare la possibilità di effettuare il provisioning per un volume di traffico inferiore. In questo scenario, lasciare che l'elasticità degli endpoint multimediali di Lync Server assorba la differenza tra il volume del traffico e il livello di traffico di picco, a scapito di una certa riduzione della qualità vocale. Si verifica inoltre una riduzione della capacità aggiuntiva altrimenti disponibile per assorbire picchi di traffico improvvisi.

  - Per i collegamenti di cui non è possibile effettuare correttamente il provisioning in tempi brevi, ad esempio un sito con collegamenti WAN insufficienti, valutare la possibilità di disabilitare la funzionalità video per alcuni utenti.

  - Eseguire il provisioning della rete per garantire un massimo ritardo end-to-end (latenza) di 150 millisecondi (MS) sotto carico di picco. Latenza è l'unica compromissione della rete che i componenti multimediali di Lync Server non possono ridurre ed è importante individuare ed eliminare i punti deboli.

  - Per i server che eseguono il software antivirus, includere tutti i server che eseguono Lync Server nell'elenco delle eccezioni per garantire prestazioni ottimali e qualità audio.

</div>

<div>

## <a name="conferencing-network-requirements"></a>Requisiti di rete per le conferenze

La larghezza di banda utilizzata per scaricare il contenuto delle conferenze dal server Internet Information Services (IIS) dipende dalle dimensioni del contenuto caricato.

</div>

</div>

<span> </span>

</div>

</div>

</div>

