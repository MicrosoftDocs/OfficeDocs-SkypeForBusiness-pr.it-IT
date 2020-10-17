---
title: 'Lync Server 2013: impostazioni di rete per le funzionalità di VoIP aziendale avanzate'
description: 'Lync Server 2013: impostazioni di rete per le funzionalità di VoIP aziendale avanzate.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42f04ba78a4cd2114e6ecffb5b92a7a54facb0df
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561422"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a>Impostazioni di rete per le funzionalità di VoIP aziendale avanzate in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-10_

Lync Server dispone di tre funzionalità di VoIP aziendale avanzate: controllo di ammissione di chiamata (CAC), servizi di emergenza (E9-1-1) e bypass multimediale. Tali caratteristiche condividono alcuni requisiti di configurazione per le aree di rete, i siti di rete e l'associazione di ogni subnet nella topologia di Lync Server con un sito di rete. Per informazioni dettagliate sulla pianificazione della distribuzione di queste caratteristiche, vedere:

  - [Pianificazione del controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)

  - [Pianificazione per i servizi di emergenza (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [Pianificazione del bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

Per informazioni dettagliate sulla distribuzione di ognuna di queste funzionalità, vedere [Deploying Advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) nella documentazione relativa alla distribuzione.

In questo argomento viene fornita una panoramica dei requisiti di configurazione comuni a tutte e tre le funzionalità di VoIP aziendale avanzate.

<div>

## <a name="network-regions"></a>Aree di rete

Un'area di rete è un hub o un backbone di rete utilizzato solo nella configurazione dei servizi Controllo di ammissione di chiamata, E9-1-1 e Media Bypass.

<div>


> [!NOTE]  
> Le aree di rete non corrispondono alle aree di conferenza telefonica con accesso esterno di Lync Server, che sono necessarie per associare i numeri delle conferenze telefoniche con chiamata in ingresso con uno o più dial plan di Lync Server. Per informazioni dettagliate sulle aree di conferenza telefonica con accesso esterno, vedere Servizi di <A href="lync-server-2013-dial-in-conferencing-requirements.md">conferenza telefonica con accesso esterno in Lync Server 2013</A> nella documentazione relativa alla pianificazione.



</div>

Per ogni area di rete è necessario un sito centrale Lync Server associato, che gestisce il traffico multimediale all'interno dell'area (ovvero che consente di prendere decisioni basate sui criteri configurati, per determinare se è possibile stabilire o meno una sessione audio o video in tempo reale). I siti centrali di Lync Server non rappresentano posizioni geografiche, ma piuttosto gruppi logici di server configurati come pool o come set di pool. Per informazioni dettagliate sui siti centrali, vedere [Reference Topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) nella documentazione relativa alla pianificazione. Vedere anche [topologie supportate in Lync Server 2013](lync-server-2013-supported-topologies.md) nella documentazione relativa alla supportabilità.

Per configurare un'area di rete, è possibile utilizzare la scheda **aree** nella sezione **configurazione di rete** del pannello di controllo di Lync Server oppure eseguire i cmdlet **New-CsNetworkRegion** o **Set-CsNetworkRegion** di Lync Server Management Shell. Per istruzioni, vedere [creare o modificare un'area di rete in Lync server 2013](lync-server-2013-create-or-modify-a-network-region.md) nella documentazione relativa alla distribuzione o fare riferimento alla documentazione di Lync Server Management Shell.

Le stesse definizioni di aree di rete sono condivise da tutte e tre le funzionalità di VoIP aziendale avanzate. Se sono già state create aree di rete per una caratteristica, non è necessario creare nuove aree di rete per le altre caratteristiche. Potrebbe tuttavia essere necessario modificare una definizione di area di rete esistente per applicare impostazioni specifiche della caratteristica. Se, ad esempio, sono state create aree di rete per il servizio E9-1-1 (che non richiede un sito centrale associato) e successivamente si distribuisce il servizio Controllo di ammissione di chiamata, è necessario modificare ognuna delle definizioni di area di rete per specificare un sito centrale.

Per associare un sito centrale di Lync Server a un'area di rete, è necessario specificare il nome del sito centrale utilizzando la sezione **configurazione di rete** del pannello di controllo di Lync Server oppure eseguendo i cmdlet **New-CsNetworkRegion** o **Set-CsNetworkRegion** di Lync Server Management Shell. Per istruzioni, vedere [creare o modificare un'area di rete in Lync server 2013](lync-server-2013-create-or-modify-a-network-region.md) nella documentazione relativa alla distribuzione o fare riferimento alla documentazione di Lync Server Management Shell.

</div>

<div>

## <a name="network-sites"></a>Siti di rete

Un sito di rete rappresenta una posizione geografica, ad esempio una succursale, una filiale o la sede principale. Ogni sito di rete deve essere associato a un'area di rete specifica.

<div>


> [!NOTE]  
> I siti di rete vengono utilizzati solo dalle funzionalità avanzate di VoIP aziendale. Non sono gli stessi dei siti di succursale configurati nella topologia di Lync Server. Per informazioni dettagliate sui siti di succursale, vedere <A href="lync-server-2013-reference-topologies.md">Reference Topologies in Lync Server 2013</A> nella documentazione relativa alla pianificazione. Vedere anche <A href="lync-server-2013-supported-topologies.md">topologie supportate in Lync Server 2013</A> nella documentazione relativa alla supportabilità.



</div>

Per configurare un sito di rete e associarlo a un'area di rete, è possibile utilizzare la sezione **configurazione di rete** del pannello di controllo di Lync Server oppure eseguire il cmdlet **New-CsNetworkSite** o **Set-CsNetworkSite** di Lync Server Management Shell. Per ulteriori informazioni, vedere [creare o modificare un sito di rete in Lync server 2013](lync-server-2013-create-or-modify-a-network-site.md) nella documentazione relativa alla distribuzione o fare riferimento alla documentazione di Lync Server Management Shell.

</div>

<div>

## <a name="identify-ip-subnets"></a>Identificare le subnet IP

Per ogni sito di rete sarà necessario collaborare con l'amministratore di rete per stabilire quali subnet IP sono assegnate a ogni sito di rete. Se l'amministratore di rete ha già organizzato le subnet IP in aree di rete e siti di rete, il lavoro risulterà notevolmente semplificato.

In questo esempio, al sito New York nell'area Nord America sono assegnate le subnet IP seguenti: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si supponga che Bob, che di solito lavora a Detroit, si sposti nell'ufficio di New York per un corso di formazione. Quando accende il suo computer e si connette alla rete, al computer verrà assegnato un indirizzo IP in uno dei quattro intervalli allocati a New York, ad esempio 172.29.80.103.

<div>


> [!WARNING]  
> Le subnet IP specificate durante la configurazione della rete nel server devono corrispondere al formato specificato dai computer client per poter essere utilizzate correttamente per Media Bypass. Un client Lync prende l'indirizzo IP locale e maschera l'indirizzo IP con la subnet mask associata. Durante la determinazione dell'ID bypass associato a ogni client, tramite la funzione di registrazione viene confrontato l'elenco delle subnet IP associate a ogni sito di rete con la subnet fornita dal client per individuare una corrispondenza esatta. Per questo motivo, è importante che le subnet immesse durante la configurazione della rete nel server siano subnet effettive, anziché virtuali. Se si implementa il servizio Controllo di ammissione di chiamata ma non Media Bypass, il servizio Controllo di ammissione di chiamata funzionerà in modo corretto anche se si configurano subnet virtuali.<BR>Ad esempio, se un client Lync accede a un computer con un indirizzo IP di 172.29.81.57 con una subnet mask IP 255.255.255.0, richiederà l'ID di bypass associato alla subnet 172.29.81.0. Se la subnet è definita come 172.29.0.0/16, anche se il client appartiene alla subnet virtuale, la funzione di registrazione non la considererà una corrispondenza esatta perché cerca nello specifico la subnet 172.29.81.0. Pertanto, è importante che l'amministratore entri nelle subnet esattamente come indicato dai client Lync (che vengono provisionati con le subnet durante la configurazione di rete, sia in modo statico che tramite il protocollo DHCP (Dynamic Host Configuration Protocol).



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a>Associazione di subnet a siti di rete

Ogni subnet della rete aziendale deve essere associata a un sito di rete (ovvero ogni subnet deve essere associata a una posizione geografica). Questa associazione di subnet consente alle funzionalità di VoIP aziendale avanzate di individuare i punti finali in modo geografico. L'individuazione degli endpoint consente, ad esempio, al servizio Controllo di ammissione di chiamata di regolare il flusso di dati audio e video in tempo reale da e verso il sito di rete.

Per associare subnet a siti di rete, è possibile utilizzare la sezione **configurazione di rete** del pannello di controllo di Lync Server oppure è possibile utilizzare Lync Server Management Shell. Per istruzioni, vedere [associare una subnet a un sito di rete in Lync server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) nella documentazione relativa alla distribuzione o fare riferimento alla documentazione di Lync Server Management Shell.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione del controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
[Pianificazione per i servizi di emergenza (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[Pianificazione del bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

