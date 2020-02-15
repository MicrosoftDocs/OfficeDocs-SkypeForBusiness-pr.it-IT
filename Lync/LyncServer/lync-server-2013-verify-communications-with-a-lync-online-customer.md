---
title: 'Lync Server 2013: verificare le comunicazioni con un cliente di Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1dffbb5d8a0e49e19c0fa5487a4af05b7e7f0155
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a>Verificare le comunicazioni con un cliente di Lync online in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-08_

Per consentire agli utenti di Lync nell'organizzazione di comunicare con gli utenti di un cliente di Microsoft Lync Online 2010, è necessario aver completato i passaggi seguenti:

  - Sono stati soddisfatti tutti i prerequisiti. Ciò include la distribuzione dei server interni e perimetrali, l'abilitazione del supporto federativo per l'organizzazione e la configurazione degli account utente. Per ulteriori informazioni, vedere [prerequisiti per la Federazione con un cliente di Lync online in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).

  - Il supporto per l'accesso al dominio è stato configurato nella distribuzione interna. Ciò include la creazione di una voce del provider host e la configurazione della distribuzione per consentire l'accesso dal dominio del cliente di Lync Online. Per ulteriori informazioni, vedere [Configure Federation support for a Lync Online Domain in Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).

  - Gli account utente sono stati configurati per il supporto della federazione. Per ulteriori informazioni, vedere [configurare l'accesso utente per la Federazione con un cliente di Lync online in Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).

Dopo aver completato tutti questi passaggi e l'amministratore del cliente Lync Online 2010 ha completato tutta la configurazione dei servizi online per supportare la Federazione con l'organizzazione, verificare le comunicazioni verificando le comunicazioni tra un interno utente dell'organizzazione e utente del cliente di Lync Online. Se la comunicazione non ha esito positivo, utilizzare lo strumento di registrazione dal server perimetrale per acquisire i file di log e di traccia per risolvere il problema. Per informazioni dettagliate sull'utilizzo dello strumento di registrazione, vedere [Open Lync Server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md) nella documentazione relativa alle operazioni. Per informazioni dettagliate sullo strumento di registrazione, vedere la documentazione dello strumento di registrazione di Lync Server 2010 nella [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)libreria TechNet all'indirizzo.

</div>

<span> </span>

</div>

</div>

</div>

