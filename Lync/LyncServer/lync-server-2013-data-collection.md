---
title: 'Lync Server 2013: raccolta dati'
description: 'Lync Server 2013: raccolta dati.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1808a68081ee453a56eabdaf264eb53ab5a1ef4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553782"
---
# <a name="data-collection-in-lync-server-2013"></a>Raccolta dati in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-08_

In Microsoft Lync Server 2013 Communications Software, è possibile eseguire Microsoft Lync Server 2013, strumento di pianificazione senza documentare gli indirizzi IP e i nomi di dominio completi (FQDN) esistenti e proposi, ma è molto più difficile farlo senza causare errori di configurazione. Ad esempio, se la coesistenza è necessaria per un determinato periodo di tempo, un errore comune consiste nel riutilizzare gli FQDN da una distribuzione perimetrale esistente per la distribuzione di Lync Server 2013 Edge. Prendendo nota degli indirizzi IP esistenti e proposti e degli FQDN in un foglio di calcolo, in una tabella oppure in un altro tipo di modulo grafico, si evitano problemi di configurazione durante l'installazione.

<div>


> [!WARNING]  
> Se sono state utilizzate versioni precedenti dello strumento di pianificazione, è possibile che sia stato utilizzato lo strumento per creare la topologia e il documento della topologia esportato per l'utilizzo in Generatore di topologie per pubblicare la topologia. La possibilità di esportare la topologia è stata rimossa dallo strumento di pianificazione. L'utilizzo di una versione precedente dello strumento di pianificazione per creare un documento di topologia per Lync Server 2013 è fortemente sconsigliato e produrrà risultati imprevisti.



</div>

Pertanto, l'approccio consigliato consiste nell'utilizzare il modello di raccolta dati seguente, che corrisponde alla topologia perimetrale, per raccogliere i vari FQDN e gli indirizzi IP che dovranno essere immessi nello strumento di pianificazione. Documentando la configurazione corrente e quella proposta, è possibile inserire i valori nel contesto corretto per l'ambiente di produzione. Si è inoltre costretti a valutare come configurare la coesistenza e funzionalità come URL semplici, condivisioni file e bilanciamento del carico.

Per distribuire correttamente Microsoft Lync Server 2013, è necessario comprendere l'interazione e l'affidamento sui singoli componenti. Raccogliendo i dati dall'infrastruttura di rete e del server esistente e applicando le indicazioni relative alla pianificazione in queste sezioni, è possibile integrare i componenti del server perimetrale di Lync Server 2013 nell'infrastruttura.

Introdotta nella [scelta di una topologia in Lync Server 2013](lync-server-2013-choosing-a-topology.md), esistono tre architetture principali con due varianti, per un totale di cinque possibili scenari di distribuzione. Uno di questi scenari rappresenterà il punto di partenza per la raccolta dei dati. Gli indirizzi IP, i nomi dei server e i nomi di dominio sono esempi che coincidono con il certificato, il firewall e i diagrammi DNS corrispondenti che descrivono in dettaglio le informazioni richieste per una soluzione di pianificazione completa. I diagrammi e la compilazione dei valori richiesti per certificato, DNS e firewall sono particolarmente importanti per le comunicazioni tra team, nei casi in cui la gestione dell'Autorità di certificazione, della configurazione del firewall e del sistema DNS è responsabilità di team diversi dal team che si occupa della pianificazione della distribuzione. I diagrammi offrono informazioni sui componenti necessari che è possibile utilizzare per la comunicazione dei requisiti nell'ottica della collaborazione tra team.

I diagrammi forniti sono intenzionalmente generali, ma consentono la raccolta di dati pertinenti che sarebbero necessari per la comunicazione dei requisiti in uno scenario di collaborazione tra team, nel quale la rete, i firewall, la creazione e la gestione dei certificati, la distribuzione dei server e la gestione dei server sono affidati a gruppi diversi. La disponibilità dei dettagli necessari per la configurazione di rete, firewall, porte e protocolli, certificati e server risulta inestimabile quando è in corso la distribuzione di Lync Server.

**Server perimetrale e pool perimetrale**

![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")

**Proxy inverso**

![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")

**Director o pool di server Director**

![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")

</div>

<span> </span>

</div>

</div>

</div>

