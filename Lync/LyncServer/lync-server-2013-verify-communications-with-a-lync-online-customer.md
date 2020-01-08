---
title: 'Lync Server 2013: verificare le comunicazioni con un cliente di Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6707139535ab30909f74b1a3fa51cce24374d09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a>Verificare le comunicazioni con un cliente di Lync online in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-08_

Per consentire agli utenti di Lync dell'organizzazione di comunicare con gli utenti di un cliente di Microsoft Lync Online 2010, è necessario che siano stati completati i passaggi seguenti:

  - Sono stati soddisfatti tutti i prerequisiti. Questo include la distribuzione di server interni e Edge, l'abilitazione del supporto federativo per l'organizzazione e la configurazione degli account utente. Per informazioni dettagliate, vedere [prerequisiti per la Federazione con un cliente di Lync online in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).

  - Supporto configurato per l'accesso ai domini nella distribuzione interna. Questo include la creazione di una voce del provider host e la configurazione della distribuzione per consentire l'accesso dal dominio del cliente di Lync Online. Per informazioni dettagliate, vedere [configurare il supporto federativo per un dominio Lync online in Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).

  - Configurato gli account utente per supportare la Federazione. Per informazioni dettagliate, vedere [configurare l'accesso degli utenti per la Federazione con un cliente di Lync online in Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).

Dopo aver completato tutti questi passaggi e l'amministratore del cliente di Lync Online 2010 completa tutta la configurazione dei propri servizi online per supportare la Federazione con l'organizzazione, verificare le comunicazioni provando le comunicazioni tra un interno utente dell'organizzazione e utente del cliente di Lync Online. Se la comunicazione non riesce, usare lo strumento di registrazione dall'Edge Server per acquisire i file di log e Trace per risolvere il problema. Per informazioni dettagliate sull'uso dello strumento di registrazione, vedere [aprire gli strumenti di amministrazione di Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md) nella documentazione delle operazioni. Per informazioni dettagliate sullo strumento di registrazione, vedere la documentazione dello strumento di registrazione di Lync Server 2010 nella [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)Raccolta TechNet all'indirizzo.

</div>

<span> </span>

</div>

</div>

</div>

