---
title: 'Lync Server 2013: infrastruttura a chiave pubblica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cee633f877a34dcf2ec0fd0b98891c62faf0bad
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512413"
---
# <a name="public-key-infrastructure-for-lync-server-2013"></a>Infrastruttura a chiave pubblica per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-13_

Microsoft Lync Server 2013 si basa su certificati per l'autenticazione del server e per stabilire una catena di attendibilità tra client e server e tra i diversi ruoli del server. Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 e Windows Server 2003 Public Key Infrastructure (PKI) fornisce l'infrastruttura per la creazione e la convalida della catena di attendibilità.

I certificati sono ID digitali. Identificano un server per nome e ne specificano le proprietà. Per assicurarsi che le informazioni su un certificato siano valide, è necessario che il certificato venga emesso da un'autorità di certificazione attendibile dai client o da altri server che si connettono al server. Se il server si connette solo ad altri client e server su una rete privata, la CA può essere una CA globale (enterprise). Se il server interagisce con entità all'esterno della rete privata, potrebbe essere necessaria una CA pubblica.

Anche se le informazioni del certificato sono valide, deve esistere la possibilità di verificare che il server che presenta il certificato sia effettivamente quello rappresentato dal certificato. Questa è la posizione in cui viene fornita la PKI di Windows.

Ogni certificato è collegato a una chiave pubblica. Il server denominato nel certificato contiene una chiave privata corrispondente nota solo a esso. Un client o un server che stabilisce la connessione utilizza la chiave pubblica per crittografare in modo casuale alcune informazioni e le invia al server. Se il server esegue la decrittografia delle informazioni e lo restituisce come testo normale, l'entità di connessione può essere sicura che il server contenga la chiave privata per il certificato e che sia quindi il server denominato sul certificato.

<div>


> [!NOTE]  
> Non tutte le autorità di certificazione pubbliche sono conformi ai requisiti dei certificati di Lync Server 2013. Si consiglia di fare riferimento all'elenco dei fornitori di autorità di certificazione pubblica certificati per le proprie esigenze di certificato pubblico. Per informazioni dettagliate, vedere Unified Communications Certificate Partners at <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A> .



</div>

<div>

## <a name="crl-distribution-points"></a>Punti di distribuzione CRL

Lync Server 2013 richiede che tutti i certificati del server contengano uno o più punti di distribuzione dell'elenco di revoche di certificati (CRL). I punti di distribuzione CRL (CDP) sono percorsi da cui è possibile scaricare i CRL allo scopo di verificare che il certificato non sia stato revocato dal momento in cui è stato emesso e che il certificato sia ancora entro il periodo di validità. Un punto di distribuzione CRL è indicato nelle proprietà del certificato come URL ed è in genere HTTP sicuro.

</div>

<div>

## <a name="enhanced-key-usage"></a>Utilizzo chiavi avanzato

Lync Server 2013 richiede che tutti i certificati del server supportino l'utilizzo delle chiavi avanzato (EKU, Enhanced Key Usage) ai fini dell'autenticazione del server. La configurazione del campo EKU per l'autenticazione del server indica che il certificato è valido ai fini dell'autenticazione dei server. Questo EKU è essenziale per MTLS. È possibile avere più di una voce in EKU, abilitando il certificato per più di uno scopo.

<div>


> [!NOTE]  
> L'EKU di autenticazione client è necessario per le connessioni MTLS in uscita da Live Communications Server 2003 e Live Communications Server 2005, ma non è più necessario. Tuttavia, questo EKU deve essere presente nei server perimetrali che si connettono a AOL tramite la connettività di messaggistica istantanea pubblica.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

