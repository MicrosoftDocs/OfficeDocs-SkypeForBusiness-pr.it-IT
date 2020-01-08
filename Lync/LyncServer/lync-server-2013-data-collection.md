---
title: 'Lync Server 2013: Raccolta dati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df4f19df012dfeac7576cc5b39d749564a4350a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a>Raccolta dati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

Nel software di comunicazione di Microsoft Lync Server 2013 è possibile eseguire Microsoft Lync Server 2013, strumento di pianificazione senza documentare gli indirizzi IP esistenti e quelli previsti e i nomi di dominio completi (FQDN) del server perimetrale, ma è molto più difficile da eseguire senza causare errori di configurazione. Ad esempio, se è necessaria una coesistenza per un periodo di tempo, un errore comune consiste nel riutilizzare gli FQDN da una distribuzione di Edge esistente per la distribuzione di Edge di Lync Server 2013. Se gli indirizzi IP e i nomi di dominio completi esistenti e proposti sono stati scritti in un foglio di calcolo, una tabella o un'altra maschera visiva, è possibile evitare problemi di configurazione durante l'installazione.

<div>


> [!WARNING]  
> Se sono state usate versioni precedenti dello strumento di pianificazione, è possibile che sia stato usato lo strumento per creare la topologia e il documento della topologia esportato per l'uso in Generatore di topologia per pubblicare la topologia. La possibilità di esportare la topologia è stata rimossa dallo strumento pianificazione. L'uso di una versione precedente dello strumento di pianificazione per creare un documento di topologia per Lync Server 2013 è fortemente sconsigliato e produrrà risultati imprevisti.



</div>

Di conseguenza, l'approccio consigliato consiste nell'usare il modello di raccolta dati seguente, che corrisponde alla topologia di Edge, per raccogliere i vari indirizzi IP e FQDN che è necessario immettere nello strumento di pianificazione. Documentando la configurazione corrente e proposta, è possibile inserire i valori nel contesto appropriato per l'ambiente di produzione. È quindi necessario pensare a come configurare la coesistenza e le funzionalità, ad esempio URL semplici, condivisioni di file e bilanciamento del carico.

Per distribuire correttamente Microsoft Lync Server 2013, è necessario comprendere l'interazione e l'affidabilità dei singoli componenti. Raccogliendo i dati dall'infrastruttura di rete e del server esistente e applicando le indicazioni per la pianificazione in queste sezioni, è possibile integrare i componenti del server Edge di Lync Server 2013 nell'infrastruttura.

Introdotta nella [scelta di una topologia in Lync Server 2013](lync-server-2013-choosing-a-topology.md), esistono tre architetture principali con due varianti, per un totale di cinque possibili scenari di distribuzione. Uno di questi scenari sarà il punto di partenza per la raccolta di dati. Gli indirizzi IP, i nomi dei server e i nomi di dominio sono esempi che coincidono con i diagrammi di certificato, firewall e DNS corrispondenti che illustrano in dettaglio le informazioni necessarie per una soluzione di pianificazione completa. I diagrammi e il riempimento del certificato richiesto, i valori DNS e firewall sono particolarmente importanti nelle comunicazioni cross-team in cui la gestione dell'autorità di certificazione, la configurazione del firewall e il DNS vengono gestiti da team diversi dal team che pianificare la distribuzione. I diagrammi contengono informazioni sui componenti necessari che possono essere usati per comunicare questi requisiti per la collaborazione tra team.

I diagrammi forniti sono intenzionalmente generici, ma consentono la raccolta di tutti i dati pertinenti che sarebbero necessari per la comunicazione dei requisiti in uno scenario cross team in cui networking, firewall, creazione e gestione di certificati, server la distribuzione e la gestione del server vengono gestite da gruppi diversi. I dettagli necessari per la configurazione di reti, firewall, porte e protocolli, certificati e server sono inestimabili quando è in corso la distribuzione di Lync Server.

**Edge Server e pool Edge**

![7624717a-CE99-4AE8-A929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-CE99-4AE8-A929-2c4d74a2e47d")

**Proxy inverso**

![cf63fc50-2D11-4334-AFC8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2D11-4334-AFC8-2d664ba1b6bb")

**Pool di Director o Director**

![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")

</div>

<span> </span>

</div>

</div>

</div>

