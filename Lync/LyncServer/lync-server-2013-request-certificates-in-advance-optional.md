---
title: 'Lync Server 2013: Richiedere certificati in anticipo (facoltativo)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ee4598f35bb607a9262bfeb7931e2c88e27920c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a>Richiedere certificati in anticipo (facoltativo) per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

I certificati sono necessari per tutti i server interni in cui è in uso Lync Server 2013, tra cui ogni server front end Enterprise Edition, server standard, Director, Edge Server e Mediation Server autonomo. Anche se è consigliata un'autorità di certificazione (CA) interna per i server interni, è anche possibile usare una CA pubblica. Per informazioni dettagliate sui requisiti dei certificati e sull'uso di una CA pubblica, vedere [requisiti di certificato per i server interni in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) nella documentazione relativa alla pianificazione.

La configurazione di Lync Server 2013 include la creazione guidata certificato, che facilita le attività di richiesta, assegnazione e installazione dei certificati durante la distribuzione. Se si vogliono richiedere certificati prima di installare i server, ad esempio per risparmiare tempo durante la distribuzione effettiva dei server, è possibile usare un computer in cui sono installati gli strumenti di amministrazione di Lync Server 2013 o tramite una richiesta di certificato procedura definita nell'organizzazione, purché si assicuri che i certificati siano esportabili e contengano tutti i nomi di oggetto alternativi necessari. La richiesta di certificati in anticipo è facoltativa. Se non vengono richieste in anticipo, è necessario richiederle come parte della configurazione di ogni server che richiede un certificato.

Questa documentazione di distribuzione fornisce le procedure per l'uso della creazione guidata certificati per richiedere certificati come parte del processo di configurazione, come descritto in configurare i certificati [per i server in Lync server 2013](lync-server-2013-configure-certificates-for-servers.md), [configurare i certificati per il Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md)e [installare i file per Mediation Server nelle sezioni di Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) della documentazione di distribuzione. Se si richiedono preventivamente i certificati, è necessario modificare le procedure di distribuzione dei certificati in queste sezioni, in base alle esigenze di importazione e assegnazione dei certificati invece di richiederle al momento della distribuzione.

<div>


> [!NOTE]  
> Lync Server 2013 include il supporto per i certificati SHA-256 per le connessioni da client che utilizzano i sistemi&nbsp;operativi Windows Vista,&nbsp;Windows&nbsp;Server 2008, Windows Server 2008 R2 e Windows 7 e Lync Phone Edition. Per supportare l'accesso esterno tramite SHA-256, il certificato esterno viene emesso da una CA pubblica tramite SHA-256.



</div>

</div>

<span> </span>

</div>

</div>

</div>

