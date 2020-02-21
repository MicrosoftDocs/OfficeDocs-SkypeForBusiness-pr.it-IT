---
title: 'Lync Server 2013: configurazione del routing in base alla posizione per le conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bc901b9ef1b4b358771427f44d220631e4a40ee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Configurazione del routing in base alla posizione per le conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-09-11_

L'applicazione per le conferenze di routing basata sulla posizione si basa sulla configurazione del routing in base alla posizione di Lync Server 2013. Le configurazioni principali sono le seguenti:

  - La posizione dei partecipanti che partecipano a una riunione è determinata in base al sito di rete. Un sito di rete e le subnet di rete associate devono essere definite in Lync Server per applicare il routing basato sulla posizione.

  - Per applicare il routing in base alla posizione delle riunioni, i partecipanti di Lync devono essere abilitati per il routing in base alla posizione.

  - Per applicare il routing in base alla posizione degli endpoint PSTN che uniscono le riunioni, è necessario configurare il trunk SIP utilizzato per connettere gli endpoint PSTN per il routing basato sulla posizione.

Per ulteriori informazioni sulla distribuzione e sulla configurazione del routing in base alla posizione di Lync Server 2013, fare riferimento a configurazione del [routing in base alla posizione](lync-server-2013-configuring-location-based-routing.md).

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>Abilitazione dell'applicazione per le conferenze di routing in base alla posizione

L'applicazione per le conferenze di routing basata sulla posizione è disabilitata per impostazione predefinita. Prima di abilitare questa applicazione, è necessario determinare la priorità giusta da assegnare per l'applicazione. Per determinare questa priorità, eseguire il cmdlet seguente in Lync Server Management Shell:

Get-CsServerApplication-Identity Service: Registrar\<: FQDN del pool\>

In questo cmdlet, \<il nome\> di dominio completo del pool è il pool in cui deve essere abilitata l'applicazione per le conferenze di routing basata sulla posizione.

Questo cmdlet restituirà l'elenco delle applicazioni ospitate da Lync Server e il valore di priorità per ognuno di essi. L'applicazione per le conferenze di routing basata sul percorso deve essere assegnata a un valore di priorità più grande dell'applicazione "UdcAgent" e più piccola delle applicazioni "DefaultRouting", "ExumRouting" e "OutboundRouting". Si consiglia di assegnare l'applicazione per le conferenze di routing basata sulla posizione un valore di priorità maggiore di un punto rispetto al valore di priorità dell'applicazione "UdcAgent".

Ad esempio, se l'applicazione "UdcAgent" ha un valore di priorità pari a "2", l'applicazione "DefaultRouting" ha un valore di priorità "8", l'applicazione "ExumRouting" ha un valore di priorità di "9" e l'applicazione "OutboundRouting" ha un valore di priorità pari a "10" è consigliabile assegnare l'applicazione per le conferenze di routing basata sul percorso come valore prioritario "3". In questo modo la priorità delle applicazioni verrà eseguita nell'ordine seguente: altre applicazioni (priorità: 0 a 1), "UdcAgent" (priorità: 2), applicazione per le conferenze di routing basata sulla posizione (priorità: 3), altre applicazioni (priorità: da 4 a 8), " DefaultRouting "(priorità: 9)," ExumRouting "(priorità: 10) e" OutboundRouting "(priorità: 11).

Dopo aver individuato il valore di priorità corretto per l'applicazione di conferenza di routing basata sulla posizione, digitare il seguente cmdlet per ogni pool Front-end o server Standard Edition in cui gli utenti di Home sono abilitati per il routing basato sulla posizione:

New-CsServerApplication-Identity Service: Registrar\<: FQDN\>pool/LBRouting- \<priorità applicazione\> prioritaria-abilitato $true-Critical $true-Urihttps://www.microsoft.com/LCS/LBRouting

Ad esempio:

New-CsServerApplication-Identity Service Registrar:LS2013CU2LBRPool. contoso. com/LBRouting-Priority 3-Enabled $true-Critical $true-Urihttps://www.microsoft.com/LCS/LBRouting

Dopo aver utilizzato questo cmdlet, riavviare tutti i Front End Server nel pool o nei server Standard Edition in cui è stata abilitata l'applicazione per le conferenze di routing in base alla posizione.

<div>


> [!IMPORTANT]  
> L'applicazione del routing basato sul percorso a conferenze o trasferimenti consultivi non viene applicata finché non vengono riavviati tutti i Front End Server nei pool o nei server Standard Edition.



</div>

Dopo che l'applicazione per le conferenze di routing basata sulla posizione è stata abilitata e tutti i server Lync applicabili sono stati riavviati, tutte le conferenze organizzate dagli utenti di Lync abilitate per il routing in base alla posizione verranno monitorate per impedire il bypass a pedaggio PSTN

</div>

</div>

<span> </span>

</div>

</div>

</div>

