---
title: Controllo di ammissione di chiamata con un PBX o un gateway PSTN di terze parti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc11c30f6383eab3ba83755b5583b47126e8c962
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a>Controllo di ammissione di chiamata in Lync Server 2013 con un gateway PSTN o un PBX di terze parti

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-20_

In questo argomento vengono descritti alcuni esempi del modo in cui il controllo di ammissione di chiamata può essere distribuito sul collegamento tra l'interfaccia gateway del Mediation Server e un gateway PSTN (Public Switched Telephone Network) di terze parti o un sistema PBX (Private Branch Exchange).

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>Caso 1: CAC tra il Mediation Server e un gateway PSTN

È possibile distribuire il servizio di controllo di ammissione sul collegamento WAN dall'interfaccia del gateway del Mediation Server a un gateway PSTN o PBX di terze parti.

**Caso 1: CAC tra il Mediation Server e un gateway PSTN**

![Caso 1: CAC tra il gateway PSTN di Mediation Server](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Caso 1: CAC tra il gateway PSTN di Mediation Server")

In questo esempio viene applicato il servizio di controllo di ammissione tra il Mediation Server e un gateway PSTN. Se un utente client di Lync nel sito di rete 1 inserisce una chiamata PSTN tramite il gateway PSTN nel sito di rete 2, il file multimediale scorre attraverso il collegamento WAN. Pertanto, vengono eseguiti due controlli CAC per ogni sessione PSTN:

  - Tra l'applicazione client Lync e il Mediation Server

  - Tra il Mediation Server e il gateway PSTN

Questo metodo funziona sia per le chiamate PSTN in arrivo a un client nel sito di rete 1 che per le chiamate PSTN in uscita provenienti da un'applicazione client nel sito di rete 1.

<div>


> [!NOTE]
> Verificare che la subnet IP a cui appartiene il gateway PSTN sia configurata e associata a sito di rete 2.<BR>Verificare che la subnet IP alla quale appartengono entrambe le interfacce del Mediation Server sia configurata e associata al sito di rete 1.<BR>Per ulteriori informazioni, vedere <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associare una subnet a un sito di rete in Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>Caso 2: CAC tra il Mediation Server e un PBX di terze parti con il punto di terminazione multimediale

Questa configurazione è simile al caso 1. In entrambi i casi, il Mediation Server sa quale dispositivo termina i file multimediali all'estremità opposta del collegamento WAN e l'indirizzo IP del gateway PSTN o del PBX con il punto di terminazione multimediale è configurato sul Mediation Server come hop successivo.

**Caso 2: CAC tra il Mediation Server e un PBX di terze parti con MTP**

![Caso 2: CAC tra Mediation Server PBX con MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Caso 2: CAC tra Mediation Server PBX con MTP")

In questo esempio viene applicato il servizio di controllo di ammissione tra il Mediation Server e il sistema PBX/MTP. Se un utente client di Lync nel sito di rete 1 inserisce una chiamata PSTN tramite il sistema PBX/MTP che si trova nel sito di rete 2, il file multimediale scorre attraverso il collegamento WAN. Pertanto, per ogni sessione PSTN vengono eseguiti due controlli CAC:

  - Tra l'applicazione client Lync e il Mediation Server

  - Tra il Mediation Server e il sistema PBX/MTP

Questo metodo funziona sia per le chiamate PSTN in arrivo a un client nel sito di rete 1 che per le chiamate PSTN in uscita provenienti da un client nel sito di rete 1.

<div>


> [!NOTE]
> Verificare che la subnet IP a cui appartiene il MTP sia configurata e associata al sito di rete 2.<BR>Verificare che la subnet IP alla quale appartengono entrambe le interfacce del Mediation Server sia configurata e associata al sito di rete 1.<BR>Per ulteriori informazioni, vedere <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associare una subnet a un sito di rete in Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>Caso 3: CAC tra il Mediation Server e un PBX di terze parti senza un punto di terminazione multimediale

Il caso 3 è leggermente diverso rispetto ai primi due casi. Se non è presente alcun MTP sul PBX di terze parti, per una richiesta di sessione in uscita al sistema PBX di terze parti, il Mediation Server non sa dove i contenuti multimediali verranno terminati nel limite del PBX. In questo caso, il contenuto multimediale scorre direttamente tra il Mediation Server e il dispositivo endpoint di terze parti.

**Caso 3: CAC tra il Mediation Server e un PBX di terze parti senza MTP**

![Caso 3: CAC tra Mediation Server PBX no MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Caso 3: CAC tra Mediation Server PBX no MTP")

In questo esempio, se un utente client di Lync nel sito di rete 1 inserisce una chiamata a un utente tramite il sistema PBX, il Mediation Server è in grado di eseguire controlli CAC solo sul lato proxy (tra l'applicazione client Lync e Mediation Server). Poiché il Mediation Server non dispone di informazioni sul dispositivo endpoint durante la richiesta della sessione, non è possibile eseguire controlli CAC sul collegamento WAN (tra il Mediation Server e l'endpoint di terze parti) prima dello stabilimento di chiamata. Dopo che la sessione è stata stabilita, tuttavia, Mediation Server facilita la contabilità per la larghezza di banda utilizzata nel trunk.

Per le chiamate che hanno origine dall'endpoint di terze parti, le informazioni sul dispositivo endpoint sono disponibili al momento della richiesta di sessione e il controllo CAC può essere eseguito su entrambi i lati del Mediation Server.

<div>


> [!NOTE]
> Verificare che la subnet IP a cui appartengono i dispositivi endpoint sia configurata e associata a sito di rete 2.<BR>Verificare che la subnet IP alla quale appartengono entrambe le interfacce del Mediation Server sia configurata e associata al sito di rete 1.<BR>Per ulteriori informazioni, vedere <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associare una subnet a un sito di rete in Lync Server 2013</A>.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

