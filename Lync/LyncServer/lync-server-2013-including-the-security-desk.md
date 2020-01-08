---
title: 'Lync Server 2013: incluso il servizio di sicurezza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Including the security desk
ms:assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398299(v=OCS.15)
ms:contentKeyID: 48184084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41c60b7f67f22393bf4a6972e68b2d0bdc2ca8a9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="including-the-security-desk-in-lync-server-2013"></a>Incluso il servizio di sicurezza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-02_

La società può richiedere che il servizio di sicurezza venga coinvolto in una chiamata di emergenza. Per decidere come integrare il servizio di sicurezza nella distribuzione di E9-1-1, è necessario rispondere alle domande seguenti.

  - **Si vuole che il desk di sicurezza venga avvisato quando è presente una chiamata di emergenza?**  
    È possibile configurare i criteri di posizione per consentire a Lync Server di inviare avvisi di messaggistica istantanea agli indirizzi SIP di Lync di uno o più addetti alla sicurezza. Questi avvisi contengono il nome, il numero e la posizione della persona che effettua la chiamata di emergenza e facilitano il personale di sicurezza nell'assistenza per la situazione di emergenza.

<!-- end list -->

  - **Si vuole eseguire una conferenza sul banco di sicurezza in ogni chiamata di emergenza?**  
    Se supportato dal provider del servizio servizi di emergenza, è possibile configurare i criteri di posizione per includere un numero di callback con ogni chiamata di emergenza. Questo numero viene quindi usato dal provider per organizzare il personale di sicurezza dell'organizzazione in chiamate di emergenza. Questa conferenza può essere configurata nel criterio della posizione in modo unidirezionale (solo in ascolto) o bidirezionale (bidirezionali).

<div>


> [!NOTE]  
> Se lo si desidera, è possibile configurare personale di emergenza diverso per ogni criterio di posizione. In questo modo, puoi personalizzare la risposta per diverse aree all'interno della tua azienda oppure creare comportamenti diversi per le chiamate di emergenza che hanno origine dall'interno invece che all'esterno della rete. È possibile usare i gruppi di distribuzione per specificare il personale che si vuole inviare.



</div>

</div>

<span> </span>

</div>

</div>

</div>

