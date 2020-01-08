---
title: 'Lync Server 2013: Revisione del report certificati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a83167576746d3f90d96658b0dd3d65815f5375
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a>Revisione del report sui certificati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Il report certificati contiene tutti i certificati necessari nella distribuzione di Lync Server 2013 consigliata. Lo strumento di pianificazione rappresenta i nomi di oggetto e i nomi alternativi oggetto immessi. Il testo predefinito lasciato inedito può rappresentare una potenziale sfida per il team responsabile per richiedere e rilasciare i certificati. Le informazioni sui certificati contengono anche informazioni sulla posizione in cui il certificato può in genere essere emesso. Se l'infrastruttura non ha un'infrastruttura a chiave pubblica (PKI) interna, tutti i certificati possono essere richiesti tramite un provider di certificati pubblici. Gli utilizzi delle chiavi estese (EKU) e i campi assegna ai nel report sono molto utili per capire qual è lo scopo e la posizione per ogni certificato.

![](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Report") Amministrazione certificati certificati rapporto di amministrazione

Esaminare con attenzione e assicurarsi di comprendere l'uso e lo scopo di ogni certificato nella distribuzione. In caso di domande su cosa fa un certificato, determinare il server o il servizio a cui si sta parlando. I certificati in Lync Server 2013 vengono usati per due scopi principali:

  - MTLS (Mutual Transport Layer Security): i computer coinvolti nella comunicazione presentano ognuno un certificato che ne dimostra l'identità a un altro computer. Questa operazione è nota come autenticazione server. La comunicazione non può iniziare finché ogni computer non considera attendibile l'identità dell'altro computer.

  - Crittografia: la crittografia (Secure Sockets Layer o SSL e Transport Layer Security o TLS) è un mezzo essenziale per proteggere le comunicazioni, garantire la privacy e creare un sistema di comunicazione e collaborazione attendibile.

<div>

## <a name="see-also"></a>Vedere anche


[Esame dei rapporti amministratore in Lync Server 2013](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

