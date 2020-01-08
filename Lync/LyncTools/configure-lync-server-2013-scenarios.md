---
title: Configurare gli scenari di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93ad7a3be8b69c956b1cca0f1d1554a5fa288f17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-scenarios"></a>Configurare gli scenari di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-12-28_

Per eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013 (LyncPerfTool), la topologia di Lync Server 2013 deve essere prima configurata per gli scenari che verranno eseguiti. Se Lync Server 2013 non è configurato o è configurato in modo non corretto, nella maggior parte dei casi non verrà eseguita la simulazione di caricamento. Con lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013 sono stati forniti gli script di Lync Server Management Shell e i file di risorse di base che è possibile usare come punto di partenza per la configurazione di Lync Server 2013. Questo argomento descrive gli esempi di Windows PowerShell forniti. Si noti che non è l'obiettivo di questo argomento descrivere come configurare Lync Server 2013 in generale. Per informazioni dettagliate sull'uso di Windows PowerShell in Lync Server 2013, vedere la documentazione di Lync Server Management <https://technet.microsoft.com/en-us/library/gg398474.aspx>shell all'indirizzo.

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a>Informazioni sull'uso degli script di Lync Server Management Shell

Sono stati forniti gli script di Lync Server Management Shell che possono essere usati in preparazione per l'uso della simulazione di caricamento. Poiché gli script sono destinati alla simulazione del carico, sono semplici e permissivi e pertanto potrebbero non essere appropriati per la produzione. Tutti gli script sono esempi e devono essere rivisti e, in alcuni casi, modificati per riflettere la topologia. Come minimo, ci aspettiamo che lo scenario di Response Group Service (RGS) debba essere modificato per specificare gli agenti assegnati ai gruppi di agenti. Tuttavia, hai la possibilità di non simulare questo carico.

<div>


> [!WARNING]  
> Fare attenzione a rivedendo e capendo gli esempi forniti. Gli script sovrascriveranno le impostazioni esistenti nella topologia.



</div>

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'uso di Windows PowerShell e Lync Server Management Shell, vedere il Blog di Lync Server 2013 di <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>Windows PowerShell.



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a>Moniker della versione client dello strumento stress e prestazioni

Potrebbe essere necessario configurare i criteri di controllo della versione client se sono state modificate le impostazioni dei valori predefiniti. Per informazioni dettagliate, vedere la pagina relativa alla <https://technet.microsoft.com/en-us/library/gg412832(v=ocs.15).aspx>configurazione delle versioni client supportate. Lo strumento di monitoraggio dello stress e delle prestazioni di Lync Server 2013 usa le versioni seguenti dell'agente utente per impostazione predefinita durante la comunicazione con Lync Server 2013:

  - LSPT/15.0.0.0 (strumento per lo stress e le prestazioni di Lync Server 2013)

  - OCPHONE/.0.522

Questi sono per il client Mobility (UCWA) in LyncPerfTool:

  - Strumento Perf UCWA/conferenza Web

  - Strumento Perf UCWA/mobile

</div>

</div>

<span> </span>

</div>

</div>

</div>

