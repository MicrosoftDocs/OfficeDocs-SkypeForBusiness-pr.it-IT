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
ms.openlocfilehash: d9ea90f30dcd9ec9fdde2e6f4db25e7d27ad12cd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Configurazione del routing in base alla posizione per le conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-09-11_

L'applicazione di conferenza di routing basata sulla posizione si basa sulla configurazione del routing basato sulla posizione di Lync Server 2013. Le configurazioni principali sono le seguenti:

  - La posizione dei partecipanti che partecipano a una riunione viene determinata in base al sito di rete. Un sito di rete e le subnet di rete associate devono essere definiti in Lync Server per applicare il routing basato sulla posizione.

  - Per applicare il routing basato sulla posizione delle riunioni, i partecipanti di Lync devono essere abilitati per il routing basato sulla posizione.

  - Per applicare il routing basato sulla posizione degli endpoint PSTN che partecipano alle riunioni, il trunk SIP usato per connettere gli endpoint PSTN deve essere configurato per il routing basato sulla posizione.

Per altre informazioni sulla distribuzione e configurazione del routing basato sulla posizione di Lync Server 2013, vedere Configurazione del [routing basato sulla posizione](lync-server-2013-configuring-location-based-routing.md).

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>Abilitazione dell'applicazione per i servizi di conferenza di routing basato sulla posizione

L'applicazione di conferenza di routing basata sulla posizione è disabilitata per impostazione predefinita. Prima di abilitare questa applicazione, devi determinare la priorità giusta da assegnare per l'applicazione. Per determinare questa priorità, eseguire il cmdlet seguente in Lync Server Management Shell:

Get-CsServerApplication-Identity Service: Registrar\<: FQDN del pool\>

In questo cmdlet il \<nome di\> dominio completo del pool è il pool in cui deve essere abilitata l'applicazione per i servizi di conferenza di routing basato sulla posizione.

Questo cmdlet restituirà l'elenco delle applicazioni ospitate da Lync Server e il valore di priorità per ognuno di essi. All'applicazione per i servizi di conferenza di routing basato sulla posizione deve essere assegnato un valore di priorità maggiore dell'applicazione "UdcAgent" e minore delle applicazioni "DefaultRouting", "ExumRouting" e "OutboundRouting". Ti consigliamo di assegnare l'applicazione per i servizi di conferenza di routing basato sulla posizione un valore prioritario di un punto superiore al valore di priorità dell'applicazione "UdcAgent".

Ad esempio, se l'applicazione "UdcAgent" ha un valore Priority di "2", l'applicazione "DefaultRouting" ha un valore Priority "8", l'applicazione "ExumRouting" ha un valore Priority di "9" e l'applicazione "OutboundRouting" ha un valore di priorità "10" quindi Devi assegnare l'applicazione per i servizi di conferenza di routing basato sulla posizione un valore prioritario "3". In questo modo la priorità delle applicazioni viene applicata nell'ordine seguente: altre applicazioni (priorità: da 0 a 1), "UdcAgent" (priorità: 2), applicazione per i servizi di conferenza di routing basato sulla posizione (priorità: 3), altre applicazioni (priorità: da 4 a 8), " DefaultRouting "(priorità: 9)," ExumRouting "(priorità: 10) e" OutboundRouting "(priorità: 11).

Dopo aver trovato il valore di priorità corretto per l'applicazione di conferenza di routing basata sulla posizione, digitare il cmdlet seguente per ogni pool Front-end o server Standard Edition che gli utenti di Homes hanno abilitato per il routing basato sulla posizione:

New-CsServerApplication-Identity Service: Registrar\<: FQDN\>del pool/LBRouting \<-Priority\> Application Priority-Enabled $true-Critical $true-Urihttp://www.microsoft.com/LCS/LBRouting

Ad esempio:

New-CsServerApplication-Identity Service Registrar:LS2013CU2LBRPool. contoso. com/LBRouting-Priority 3-Enabled $true-Critical $true-Urihttp://www.microsoft.com/LCS/LBRouting

Dopo aver usato questo cmdlet, riavviare tutti i server front-end nel pool o nei server Standard Edition in cui è stata abilitata l'applicazione per i servizi di conferenza di routing basato sulla posizione.

<div>


> [!IMPORTANT]  
> Le imposte di routing basate sulla posizione su conferenze o trasferimenti consultivi non verranno applicate fino a quando non vengono riavviati tutti i server front-end nei pool o i server Standard Edition.



</div>

Dopo che l'applicazione per i servizi di conferenza di routing basato sulla posizione è stata abilitata e tutti i server Lync applicabili sono stati riavviati, tutte le conferenze organizzate dagli utenti di Lync abilitate per il routing basato sulla posizione verranno monitorate per evitare il bypass a pedaggio PSTN

</div>

</div>

<span> </span>

</div>

</div>

</div>

