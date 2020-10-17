---
title: 'Lync Server 2013: configurazione del routing Location-Based per le conferenze'
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
ms.openlocfilehash: bd5ada5e4af1ed4ed43434ddf4d82abc25f4cd5e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507803"
---
# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Configurazione del routing Location-Based per le conferenze in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-09-11_

L'applicazione Location-Based routing Conferencing si basa sulla configurazione del routing Location-Based Lync Server 2013. Le configurazioni principali sono le seguenti:

  - La posizione dei partecipanti che partecipano a una riunione è determinata in base al sito di rete. Un sito di rete e le subnet di rete associate devono essere definite in Lync Server per applicare il routing Location-Based.

  - Per applicare il routing Location-Based alle riunioni, i partecipanti di Lync devono essere abilitati per il routing Location-Based.

  - Per applicare il routing Location-Based degli endpoint PSTN che uniscono le riunioni, è necessario configurare il trunk SIP utilizzato per connettere gli endpoint PSTN per il routing Location-Based.

Per ulteriori informazioni sulla distribuzione e sulla configurazione di Lync Server 2013 Location-Based routing, fare riferimento a configurazione del [routing in base alla posizione](lync-server-2013-configuring-location-based-routing.md).

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>Abilitazione dell'applicazione per il routing di Location-Based Conferencing

Per impostazione predefinita, l'applicazione di conferenza di routing Location-Based è disabilitata. Prima di abilitare questa applicazione, è necessario determinare la priorità giusta da assegnare per l'applicazione. Per determinare questa priorità, eseguire il cmdlet seguente in Lync Server Management Shell:

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

In questo cmdlet, \<Pool FQDN\> è il pool in cui deve essere abilitata l'applicazione di conferenza di Routing Location-Based.

Questo cmdlet restituirà l'elenco delle applicazioni ospitate da Lync Server e il valore di priorità per ognuno di essi. L'applicazione di routing per le conferenze di Location-Based deve essere assegnata a un valore di priorità più grande dell'applicazione "UdcAgent" e più piccola delle applicazioni "DefaultRouting", "ExumRouting" e "OutboundRouting". Si consiglia di assegnare l'applicazione di conferenza di routing Location-Based un valore di priorità maggiore di un punto rispetto al valore di priorità dell'applicazione "UdcAgent".

Ad esempio, se l'applicazione "UdcAgent" ha un valore di priorità pari a "2", l'applicazione "DefaultRouting" ha un valore di priorità "8", l'applicazione "ExumRouting" ha un valore di priorità di "9" e l'applicazione "OutboundRouting" ha un valore di priorità pari a "10", quindi è necessario assegnare l'applicazione di conferenza di routing Location-Based un valore prioritario In questo modo la priorità delle applicazioni verrà eseguita nell'ordine seguente: altre applicazioni (priorità: 0 a 1), "UdcAgent" (priorità: 2), Location-Based applicazione per le conferenze di routing (priorità: 3), altre applicazioni (priorità: 4 a 8), "DefaultRouting" (priorità: 9), "ExumRouting" (priorità: 10) e "OutboundRouting" (priorità: 11).

Dopo aver individuato il valore di priorità corretto per l'applicazione di conferenza di routing Location-Based, digitare il seguente cmdlet per ogni pool di Front-End o server Standard Edition in cui gli utenti di Homes sono abilitati per il routing Location-Based:

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Ad esempio:

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Dopo aver utilizzato questo cmdlet, riavviare tutti i Front End Server nel pool o nei server Standard Edition in cui è stata abilitata l'applicazione di conferenza di routing Location-Based.

<div>


> [!IMPORTANT]  
> Location-Based l'applicazione di routing alle conferenze o ai trasferimenti consultivi non verrà applicata finché non vengono riavviati tutti i Front End Server nei pool o nei server Standard Edition.



</div>

Dopo che l'applicazione di routing per la Location-Based di distribuzione è stata abilitata e tutti i server Lync applicabili sono stati riavviati, tutte le conferenze organizzate dagli utenti di Lync abilitate per Location-Based il routing verranno monitorate per impedire il bypass a pedaggio PSTN

</div>

</div>

<span> </span>

</div>

</div>

</div>

