---
title: 'Lync Server 2013: infrastruttura a chiave pubblica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fb79340b29ab4bfa6942d2b2cb62483c79b4ce9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a>Infrastruttura a chiave pubblica per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-13_

Microsoft Lync Server 2013 si basa su certificati per l'autenticazione del server e stabilisce una catena di trust tra client e server e tra i diversi ruoli del server. Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 e infrastruttura a chiave pubblica (PKI) di Windows Server 2003 fornisce l'infrastruttura per stabilire e convalidare questa catena di attendibilità.

I certificati sono ID digitali. Identificano un server per nome e ne specificano le proprietà. Per assicurarsi che le informazioni su un certificato siano valide, il certificato deve essere emesso da una CA considerata attendibile dai client o da altri server che si connettono al server. Se il server si connette solo con altri client e server su una rete privata, la CA può essere una CA aziendale. Se il server interagisce con entità esterne alla rete privata, potrebbe essere richiesta una CA pubblica.

Anche se le informazioni sul certificato sono valide, ci deve essere un modo per verificare che il server che presenta il certificato sia effettivamente quello rappresentato dal certificato stesso. È qui che entra in gioco la PKI di Windows.

Ogni certificato è collegato a una chiave pubblica. Il server indicato sul certificato contiene una chiave privata corrispondente di sua esclusiva conoscenza. Un client o un server che si connette utilizza la chiave pubblica per crittografare una parte di informazioni casuali e la invia al server. Se il server decrittografa le informazioni e le restituisce come testo normale, l'entità che si connette può essere certa che il server detenga la chiave privata corrispondente al certificato e pertanto sia il server indicato sul certificato.

<div>


> [!NOTE]  
> Non tutte le CA pubbliche soddisfano i requisiti dei certificati di Lync Server 2013. Ti consigliamo di fare riferimento all'elenco dei fornitori di CA pubblici certificati per le tue esigenze per i certificati pubblici. Per informazioni dettagliate, vedere partner per i certificati di <A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>comunicazioni unificate.



</div>

<div>

## <a name="crl-distribution-points"></a>Punti di distribuzione CLR

Lync Server 2013 richiede che tutti i certificati server contengano uno o più punti di distribuzione dell'elenco di revoche di certificati (CRL). I punti di distribuzione CRL (CDP) sono posizioni da cui è possibile scaricare i CRL per verificare che il certificato non sia stato revocato dal momento in cui è stato rilasciato e che rientri ancora nel periodo di validità. Un punto di distribuzione CRL viene indicato nelle proprietà del certificato come URL e in genere è protetto da HTTP.

</div>

<div>

## <a name="enhanced-key-usage"></a>Utilizzo chiavi avanzato

Lync Server 2013 richiede che tutti i certificati server supportino l'uso di chiavi avanzate (EKU) per l'autenticazione del server. La configurazione del campo EKU per l'autenticazione del server indica che il certificato è valido ai fini dell'autenticazione dei server. Tale EKU è essenziale per MTLS. È possibile avere più di una voce in EKU, abilitando il certificato per più di uno scopo.

<div>


> [!NOTE]  
> L'EKU di autenticazione client è necessario per le connessioni MTLS in uscita da Live Communications Server 2003 e Live Communications Server 2005, ma non è più necessario. Tuttavia, questo EKU deve essere presente in Edge Server che si connettono a AOL per mezzo della connettività di messaggistica istantanea pubblica.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

