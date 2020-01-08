---
title: Requisiti per l'infrastruttura di rete di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc1f74705469bf3a024d84848942eae972e0a629
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a>Requisiti per l'infrastruttura di rete per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-18_

La scheda scheda di rete di ogni server nella topologia di Lync Server 2013 deve supportare almeno 1 Gigabit al secondo (Gbps). In generale, è consigliabile connettere tutti i ruoli del server all'interno della topologia di Lync Server tramite una rete LAN (Local Area Network) a bassa latenza e ad alta larghezza di banda. Le dimensioni della LAN dipendono dalle dimensioni della topologia:

  - Nelle topologie standard Edition i server devono essere in una rete che supporta 1 Gbps Ethernet o equivalente.

  - Nelle topologie del pool Front-end la maggior parte dei server dovrebbe essere in una rete che supporta più di 1 Gbps, in particolare quando si supportano la condivisione di applicazioni e conferenze audio/video (A/V).

Per l'integrazione PSTN (Public Switched Telephone Network), è possibile integrare tramite linee T1/E1 o trunking SIP.

<div>

## <a name="audiovideo-network-requirements"></a>Requisiti di rete audio/video

I requisiti di rete per audio/video (A/V) in una distribuzione di Lync Server includono i seguenti:

  - Se si distribuisce un singolo Edge Server o un pool di Edge tramite il bilanciamento del carico DNS, è possibile configurare il firewall esterno come NAT. Non è possibile configurare il firewall interno come NAT. Per informazioni dettagliate su questi requisiti, vedere [determinare i requisiti per il firewall e la porta a/V esterni per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) nella documentazione relativa alla pianificazione.
    
    <div>
    

    > [!IMPORTANT]  
    > Se si ha un pool di bordi e si usa un dispositivo di bilanciamento del carico hardware, è necessario usare gli indirizzi IP pubblici in tutti i server perimetrali e non è possibile usare il NAT per i server o il pool di dispositivi NAT, ad esempio il firewall o un altro dispositivo di infrastruttura che NAT inbou ND o traffico in uscita). Per informazioni dettagliate, vedere <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Edge consolidato basato su riassunto della porta con i dispositivi di bilanciamento del carico hardware in Lync Server 2013</A> nella documentazione relativa alla pianificazione per l'accesso degli utenti esterni.

    
    </div>

  - Se l'organizzazione usa un'infrastruttura QoS (Quality of Service), il sottosistema multimediale è progettato per funzionare all'interno di questa infrastruttura esistente.

  - Se si usa Internet Protocol Security (IPsec), è consigliabile disabilitare IPsec sugli intervalli di porte usati per il traffico A/V. Per informazioni dettagliate, vedere [Eccezioni IPsec in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) nella documentazione relativa alla pianificazione.

Per garantire una qualità media ottimale, eseguire le operazioni seguenti:

  - Eseguire il provisioning dei collegamenti di rete per supportare la velocità effettiva di 65 kilobit al secondo (Kbps) per flusso audio e 500 kbps per ogni flusso video, se abilitato, durante i periodi di utilizzo massimo. Una sessione audio o video bidirezionale è costituita da due flussi.

  - Per far fronte a picchi imprevisti nel traffico sopra questo livello e ad un maggiore utilizzo nel tempo, gli endpoint multimediali di Lync Server possono adattarsi alle diverse condizioni di rete e supportare carichi di tre volte la velocità effettiva (Vedi paragrafo precedente) per l'audio e il video mentre si è ancora mantenere una qualità accettabile. Tuttavia, non presupporre che questa adattabilità supporti una rete sottoposta a provisioning. In una rete sottoposta a provisioning, la capacità degli endpoint multimediali di Lync Server di gestire in modo dinamico le diverse condizioni di rete, ad esempio la perdita temporanea di pacchetti elevati, viene ridotta.

  - Per i collegamenti di rete in cui il provisioning è estremamente costoso e difficile, potrebbe essere necessario prendere in considerazione il provisioning per un volume di traffico più basso. In questo scenario, l'elasticità degli endpoint multimediali di Lync Server assorbe la differenza tra il volume del traffico e il livello di traffico massimo, a scapito di una certa riduzione della qualità vocale. Inoltre, c'è una diminuzione dello spazio di lavoro altrimenti disponibile per assorbire picchi improvvisi nel traffico.

  - Per i collegamenti che non è possibile eseguire correttamente il provisioning a breve termine, ad esempio un sito con collegamenti WAN molto scarsi, è consigliabile disabilitare il video per alcuni utenti.

  - Eseguire il provisioning della rete per garantire un massimo ritardo finale (latenza) di 150 millisecondi (MS) in caricamento massimo. La latenza è l'unica compromissione della rete che i componenti multimediali di Lync Server non possono ridurre ed è importante trovare ed eliminare i punti deboli.

  - Per i server che utilizzano software antivirus, includere tutti i server che utilizzano Lync Server nell'elenco delle eccezioni per garantire prestazioni e qualità audio ottimali.

</div>

<div>

## <a name="conferencing-network-requirements"></a>Requisiti di rete per i servizi di conferenza

La larghezza di banda usata per scaricare il contenuto delle conferenze dal server Internet Information Services (IIS) dipende dalle dimensioni del contenuto caricato.

</div>

</div>

<span> </span>

</div>

</div>

</div>

