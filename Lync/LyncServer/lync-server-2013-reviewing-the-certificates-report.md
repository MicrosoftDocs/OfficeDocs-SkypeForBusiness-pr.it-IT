---
title: 'Lync Server 2013: Revisione del rapporto sui certificati'
description: 'Lync Server 2013: Revisione del rapporto sui certificati.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2133e2f70c78217788d84251c2035a9115bc3283
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578462"
---
# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a>Revisione del rapporto sui certificati in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Il rapporto certificati contiene tutti i certificati necessari nella distribuzione di Lync Server 2013 consigliata. Lo strumento di pianificazione rappresenta i nomi soggetto e i nomi alternativi del soggetto immessi. Il testo predefinito che viene lasciato inedito potrebbe rappresentare una possibile sfida per il team responsabile della richiesta e dell'emissione dei certificati. Nelle informazioni sui certificati sono inoltre incluse informazioni sull'origine da cui in genere viene emesso il certificato. Se l'infrastruttura non dispone di un'infrastruttura a chiave pubblica (PKI), tutti i certificati possono essere richiesti tramite un provider di certificati pubblico. I campi relativi agli utilizzi chiave avanzati e alla destinazione del rapporto sono molto utili per comprendere lo scopo e il percorso di ogni certificato.

![Rapporto di amministrazione dei certificati](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Rapporto di amministrazione dei certificati")

Esaminare attentamente e assicurarsi di comprendere l'utilizzo e lo scopo di ogni certificato nella distribuzione. Se si verifica un problema relativo a un certificato, determinare il server o il servizio a cui si sta parlando. I certificati in Lync Server 2013 vengono utilizzati per due scopi principali:

  - Mutual Transport Layer Security (MTLS) – i computer coinvolti nella comunicazione presentano ciascuno un certificato che dimostra la propria identità a un altro computer. Questa operazione è nota come autenticazione del server. La comunicazione non può iniziare finché ogni computer non considera attendibile l'identità dell'altro computer.

  - Crittografia: la crittografia (Secure Sockets Layer, o SSL e Transport Layer Security, o TLS) è uno strumento fondamentale per la protezione delle comunicazioni, per assicurare la privacy e per creare un sistema di comunicazioni e collaborazione attendibile.

<div>

## <a name="see-also"></a>Vedere anche


[Revisione dei rapporti dell'amministratore in Lync Server 2013](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

