---
title: Configurare gli scenari di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d108cc3a2c49c40eb04c9039c83689fb8c5abf4c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499943"
---
# <a name="configure-lync-server-2013-scenarios"></a>Configurare gli scenari di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-12-28_

Per eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013 (LyncPerfTool), è innanzitutto necessario configurare la topologia di Lync Server 2013 per gli scenari che verranno eseguiti. Se Lync Server 2013 non è configurato o non è configurato in modo errato, nella maggior parte dei casi la simulazione del caricamento avrà esito negativo. Con lo strumento Lync Server 2013 stress and performance sono stati forniti esempi di script Lync Server Management Shell e file di risorse di base che è possibile utilizzare come punto di partenza per la configurazione di Lync Server 2013. In questo argomento vengono descritti gli esempi di Windows PowerShell forniti. Si noti che non è l'obiettivo di questo argomento descrivere la modalità di configurazione di Lync Server 2013 in generale. Per informazioni dettagliate sull'utilizzo di Windows PowerShell in Lync Server 2013, vedere la documentazione di Lync Server Management Shell all'indirizzo <https://technet.microsoft.com/library/gg398474.aspx> .

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a>Informazioni sull'esecuzione di script di Lync Server Management Shell

Sono stati forniti script di Lync Server Management Shell che possono essere utilizzati in preparazione per l'esecuzione di simulazione del carico. Poiché gli script sono destinati alla simulazione del carico, sono semplici e permissivi e pertanto potrebbero non essere appropriati per la produzione. Tutti gli script sono esempi e devono essere esaminati e, in alcuni casi, modificati per riflettere la topologia. Come minimo, si prevede che lo scenario del servizio Response Group (RGS) debba essere modificato in modo da specificare gli agenti assegnati ai gruppi di agenti. Tuttavia, si ha la possibilità di non simulare questo carico.

<div>


> [!WARNING]  
> Fare attenzione a esaminare e comprendere gli esempi forniti. Gli script sovrascrivono le impostazioni esistenti nella topologia.



</div>

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'utilizzo di Windows PowerShell e Lync Server Management Shell, vedere il Blog di Lync Server 2013 Windows PowerShell all'indirizzo <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A> .



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a>Moniker versione client dello strumento di stress e prestazioni

Potrebbe essere necessario configurare i criteri di controllo della versione client se sono state modificate le impostazioni dai valori predefiniti. Per informazioni dettagliate, vedere la sezione relativa alla configurazione delle versioni client supportate all'indirizzo <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx> . Lo strumento Lync Server 2013 stress and performance utilizza le seguenti versioni di agente utente per impostazione predefinita durante la comunicazione con Lync Server 2013:

  - LSPT/15.0.0.0 (strumento di stress e prestazioni di Lync Server 2013)

  - OCPHONE/.0.522

Si tratta del client per dispositivi mobili (UCWA) in LyncPerfTool:

  - UCWA Perf Tool/Web Conference

  - UCWA Perf Tool/mobile

</div>

</div>

<span> </span>

</div>

</div>

</div>

