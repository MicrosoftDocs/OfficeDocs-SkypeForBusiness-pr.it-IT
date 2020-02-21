---
title: 'Lync Server 2013: configurare la Federazione per un provider di servizi di audioconferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation for an audio conferencing provider
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn510996(v=OCS.15)
ms:contentKeyID: 60595883
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 679fe6ae6f11823d55070508b506864b1839d054
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a>Configurare la Federazione per un provider di servizi di audioconferenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-07-24_

Se si desidera utilizzare un provider di servizi di audioconferenza (ACP) nella distribuzione ibrida (Lync Server locale con Lync Online), è necessario configurare la Federazione tra la distribuzione di Lync locale e il partner ACP come server partner consentito. È possibile configurare la Federazione aggiungendo il dominio del partner ACP e il server perimetrale (può anche essere denominato proxy di accesso) all'elenco dei domini federati per la distribuzione locale. Il partner ACP deve quindi aggiungere il nome FQDN del pool di server perimetrali locale all'elenco dei domini federati consentiti. Contattare il provider ACP per ulteriori detailsYour partner ACP è quindi necessario aggiungere il nome di dominio completo del pool di server perimetrali locale all'elenco dei domini federati consentiti.

  - **Aggiunta del dominio ACP e del server perimetrale come dominio federato consentito**
    
    Per aggiungere il dominio ACP come server partner consentito (dominio federato consentito), seguire la procedura illustrata in [configurare il supporto per i domini esterni consentiti in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md). Per il server perimetrale, aggiungere il nome di dominio completo del server perimetrale del partner ACP. Potrebbe essere necessario contattare il partner ACP per ottenere il nome di dominio completo per il server perimetrale, che può anche essere definito dal proprio ACP come proxy di accesso.

  - **Specificare il nome di dominio completo del pool di server perimetrali per il partner ACP**
    
    È necessario che il partner ACP configuri la Federazione per aggiungere il dominio locale come server partner consentito aggiungendo l'FQDN del pool di server perimetrali come dominio federato consentito.

</div>

<span> </span>

</div>

</div>

</div>

