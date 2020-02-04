---
title: 'Lync Server 2013: Configurare le interfacce di rete per i server perimetrali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfbae47a5f5e99e603e3f095a2e07dbb9b49515f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a>Configurare le interfacce di rete per i server perimetrali in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

Ogni Edge Server è un computer multihome con interfacce esterne e interne. Le impostazioni DNS (adapter Domain Name System) dipendono dalla presenza di server DNS nella rete perimetrale. Se nel perimetro sono presenti server DNS, è necessario che dispongano di una zona contenente uno o più record DNS per il server o il pool di hop successivo, ovvero un pool di Director o di front-end designato, e per le query esterne che fanno riferimento alle ricerche dei nomi ad altri server DNS pubblici. Se nel perimetro non sono presenti server DNS, gli Edge Server usano server DNS esterni per risolvere le ricerche di nomi Internet e ogni Edge Server usa un HOST per risolvere i nomi dei server dell'hop successivo in indirizzi IP.

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" />Nota sulla sicurezza:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Per motivi di sicurezza, è consigliabile non avere l'accesso dei server Edge a un server DNS situato nella rete interna.</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a>Per configurare le interfacce con i server DNS nella rete perimetrale

1.  Installare due schede di rete per ogni server perimetrale, uno per l'interfaccia di rivestimento interno e uno per l'interfaccia esterna.
    
    <div>
    

    > [!IMPORTANT]  
    > Le subnet interne ed esterne non devono essere instradate tra loro.

    
    </div>

2.  Nell'interfaccia esterna configurare tre indirizzi IP statici nella subnet della rete perimetrale esterna (nota anche come DMZ, zona demilitarizzata e subnet schermata) e puntare il gateway predefinito all'interfaccia interna del firewall esterno. Configurare le impostazioni DNS della scheda in maniera che puntino a una coppia di server DNS perimetrali.
    
    <div>
    

    > [!NOTE]  
    > È possibile usare un solo indirizzo IP per questa interfaccia, ma per eseguire questa operazione è necessario modificare le assegnazioni della porta in valori non standard. Questa operazione viene determinata quando si crea la topologia in Generatore di topologie.

    
    </div>

3.  Nell'interfaccia interna configurare un indirizzo IP statico nella subnet della rete perimetrale interna e non impostare un gateway predefinito. Configurare le impostazioni DNS adapter in maniera che puntino ad almeno un server DNS, preferibilmente una coppia di server DNS perimetrali.

4.  Creare route statiche permanenti sull'interfaccia interna per tutte le reti interne in cui risiedono i client, i server Lync Server 2013 e la messaggistica unificata di Exchange.

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a>Per configurare le interfacce senza server DNS nella rete perimetrale

1.  Installare due schede di rete per ogni server perimetrale, uno per l'interfaccia di rivestimento interno e uno per l'interfaccia esterna.
    
    <div>
    

    > [!IMPORTANT]  
    > Le subnet interne ed esterne non devono essere instradate tra loro.

    
    </div>

2.  Nell'interfaccia esterna configurare tre indirizzi IP statici nella subnet della rete perimetrale esterna. È anche possibile configurare il gateway predefinito nell'interfaccia esterna. Ad esempio, Definisci il router che si affaccia su Internet o il firewall esterno come gateway predefinito. Configurare le impostazioni DNS in maniera che puntino a un server DNS, preferibilmente a una coppia di server DNS esterni.
    
    <div>
    

    > [!NOTE]  
    > È possibile, ma non consigliabile, usare il minor numero di un indirizzo IP per l'interfaccia esterna. Per consentire il funzionamento, è necessario modificare le assegnazioni della porta in valori non standard e non la porta predefinita 443 che è in genere "firewall friendly" per la comunicazione client. Puoi determinare l'impostazione dell'indirizzo IP e le impostazioni della porta quando crei la topologia in Generatore di topologie.

    
    </div>

3.  Nell'interfaccia interna configurare un indirizzo IP statico nella subnet della rete perimetrale interna e non impostare un gateway predefinito. Abbandonare le impostazioni DNS della scheda vuoto.

4.  Creare route statiche permanenti sull'interfaccia interna per tutte le reti interne in cui risiedono i client Lync o i server che utilizzano Lync Server 2013.

5.  Modificare il file HOST in ogni Edge Server in modo che contenga un record per il server hop successivo o l'IP virtuale (VIP) (il record sarà il Director, il server Standard Edition o un pool Front-end configurato come indirizzo hop successivo di Edge Server in Generatore di topologia). Se si usa il bilanciamento del carico DNS, includere una riga per ogni membro del pool hop successivo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

