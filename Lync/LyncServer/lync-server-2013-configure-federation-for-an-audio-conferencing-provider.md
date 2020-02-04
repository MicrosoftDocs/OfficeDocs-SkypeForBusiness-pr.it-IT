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
ms.openlocfilehash: c5c1ca77b2f68a2285fb15d65c19631323a03bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a>Configurare la Federazione per un provider di servizi di audioconferenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-07-24_

Se si vuole usare un provider di servizi di audioconferenza (ACP) nella distribuzione ibrida (Lync Server locale con Lync Online), è necessario configurare la Federazione tra la distribuzione locale di Lync e il partner ACP come server partner consentito. È possibile configurare la Federazione aggiungendo il dominio partner ACP e il server perimetrale (può anche essere chiamato proxy di accesso) nell'elenco dei domini federati per la distribuzione locale. Il partner ACP deve quindi aggiungere il nome di dominio completo del pool di Edge Server locale all'elenco dei domini federati consentiti. Contattare il provider ACP per altri partner di detailsYour ACP deve quindi aggiungere il nome di dominio completo del pool di Edge Server locale all'elenco dei domini federati consentiti.

  - **Aggiunta del dominio ACP e del server perimetrale come dominio federato consentito**
    
    Per aggiungere il dominio ACP come server partner consentito (dominio federato consentito), seguire i passaggi descritti in [configurare il supporto per i domini esterni consentiti in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md). Per il server perimetrale, aggiungere il nome di dominio completo del server Edge del partner ACP. Potrebbe essere necessario contattare il partner ACP per ottenere il nome di dominio completo per il server perimetrale, che può anche essere indicato dal proprio proxy di accesso per i paesi ACP.

  - **Specificare il nome di dominio completo del pool di Edge Server per il partner ACP**
    
    Il partner ACP deve configurare la Federazione per aggiungere il dominio locale come server partner consentito aggiungendo il nome FQDN del pool di Edge Server come dominio federato consentito.

</div>

<span> </span>

</div>

</div>

</div>

