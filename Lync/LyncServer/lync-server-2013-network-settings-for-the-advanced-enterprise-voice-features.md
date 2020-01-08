---
title: 'Lync Server 2013: impostazioni di rete per le funzionalità vocali avanzate di Enterprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d633d111e9df09cde57b91f32f4592b7f80c9f26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a>Impostazioni di rete per le funzionalità vocali avanzate di Enterprise in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-10_

Lync Server include tre funzionalità vocali avanzate per l'organizzazione: controllo di ammissione delle chiamate (CAC), servizi di emergenza (E9-1-1) e bypass multimediale. Queste funzionalità condividono determinati requisiti di configurazione per le aree di rete, i siti di rete e l'associazione di ogni subnet nella topologia di Lync Server con un sito di rete. Per informazioni dettagliate sulla pianificazione della distribuzione di queste funzionalità, vedere:

  - [Pianificazione del servizio Controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)

  - [Pianificazione per i servizi di emergenza (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [Pianificazione del bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

Per informazioni dettagliate sulla distribuzione di ognuna di queste funzionalità, vedere [distribuzione di funzionalità vocali avanzate di Enterprise in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) nella documentazione relativa alla distribuzione.

Questo argomento offre una panoramica dei requisiti di configurazione comuni a tutte e tre le funzionalità avanzate di VoIP aziendale.

<div>

## <a name="network-regions"></a>Aree di rete

Un'area di rete è un hub di rete o backbone di rete usato solo nella configurazione del controllo di ammissione alle chiamate (CAC), E9-1-1 e bypass multimediale.

<div>


> [!NOTE]  
> Le aree di rete non corrispondono alle aree dei servizi di conferenza telefonica con accesso esterno di Lync Server, che sono necessarie per associare i numeri di Access per i servizi di conferenza telefonica con chiamata in ingresso con uno o più piani di dial Lync Server Per informazioni dettagliate sulle aree dei servizi di conferenza telefonica con accesso esterno, vedere Requisiti per i servizi di conferenza telefonica <A href="lync-server-2013-dial-in-conferencing-requirements.md">con accesso esterno in Lync Server 2013</A> nella documentazione relativa alla pianificazione.



</div>

Il CAC richiede che ogni area di rete disponga di un sito centrale Lync Server associato, che gestisce il traffico multimediale all'interno dell'area geografica, ossia prende decisioni in base a criteri configurati, per quanto riguarda la possibilità di una sessione audio o video in tempo reale essere stabilito). I siti centrali di Lync Server non rappresentano posizioni geografiche, bensì gruppi logici di server configurati come pool o set di pool. Per informazioni dettagliate sui siti centrali, vedere [topologie di riferimento in Lync Server 2013](lync-server-2013-reference-topologies.md) nella documentazione relativa alla pianificazione. Vedere anche [topologie supportate in Lync Server 2013](lync-server-2013-supported-topologies.md) nella documentazione relativa alla supportabilità.

Per configurare un'area di rete, è possibile usare la scheda **aree** nella sezione **configurazione di rete** del pannello di controllo di Lync Server oppure eseguire i cmdlet **New-CsNetworkRegion** o **Set-CsNetworkRegion** Lync Server Management Shell. Per istruzioni, vedere [creare o modificare un'area di rete in Lync server 2013](lync-server-2013-create-or-modify-a-network-region.md) nella documentazione di distribuzione oppure fare riferimento alla documentazione di Lync Server Management Shell.

Le stesse definizioni di area di rete sono condivise da tutte e tre le funzionalità vocali avanzate di Enterprise. Se sono già state create aree di rete per una caratteristica, non è necessario creare nuove aree di rete per le altre funzionalità. Può tuttavia essere necessario modificare una definizione di area di rete esistente per applicare impostazioni specifiche delle caratteristiche. Ad esempio, se sono state create aree di rete per E9-1-1 (che non richiedono un sito centrale associato) e, in seguito, si distribuisce il controllo di ammissione di chiamata, è necessario modificare ogni definizione di area di rete per specificare un sito centrale.

Per associare un sito centrale di Lync Server a un'area di rete, è necessario specificare il nome del sito centrale utilizzando la sezione **configurazione di rete** del pannello di controllo di Lync Server oppure eseguendo i cmdlet **New-CsNetworkRegion** o **Set-CsNetworkRegion** Lync Server Management Shell. Per istruzioni, vedere [creare o modificare un'area di rete in Lync server 2013](lync-server-2013-create-or-modify-a-network-region.md) nella documentazione di distribuzione oppure fare riferimento alla documentazione di Lync Server Management Shell.

</div>

<div>

## <a name="network-sites"></a>Siti di rete

Un sito di rete rappresenta una posizione geografica, ad esempio una filiale, un ufficio regionale o una sede principale. Ogni sito di rete deve essere associato a una specifica area di rete.

<div>


> [!NOTE]  
> I siti di rete vengono usati solo dalle funzionalità vocali avanzate di Enterprise. Non corrispondono ai siti della filiale configurati nella topologia di Lync Server. Per informazioni dettagliate sui siti di succursale, vedere <A href="lync-server-2013-reference-topologies.md">topologie di riferimento in Lync Server 2013</A> nella documentazione relativa alla pianificazione. Vedere anche <A href="lync-server-2013-supported-topologies.md">topologie supportate in Lync Server 2013</A> nella documentazione relativa alla supportabilità.



</div>

Per configurare un sito di rete e associarlo a un'area di rete, è possibile usare la sezione **configurazione di rete** del pannello di controllo di Lync Server oppure eseguire i cmdlet di Lync Server Management Shell **New-CsNetworkSite** o **Set-CsNetworkSite** . Per informazioni dettagliate, vedere [creare o modificare un sito di rete in Lync server 2013](lync-server-2013-create-or-modify-a-network-site.md) nella documentazione di distribuzione oppure fare riferimento alla documentazione di Lync Server Management Shell.

</div>

<div>

## <a name="identify-ip-subnets"></a>Identificare le subnet IP

Per ogni sito di rete, è necessario collaborare con l'amministratore di rete per determinare le subnet IP assegnate a ogni sito di rete. Se l'amministratore di rete ha già organizzato le subnet IP nelle aree di rete e nei siti di rete, il lavoro è semplificato in modo significativo.

Ad esempio, il sito di New York nell'area Nord America può essere assegnato alle subnet IP seguenti: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Se Bob, che lavora di solito a Detroit, viaggia all'ufficio di New York per la formazione, accende il computer e si connette alla rete, il computer otterrà un indirizzo IP in uno dei quattro intervalli assegnati a New York, ad esempio 172.29.80.103.

<div>


> [!WARNING]  
> Le subnet IP specificate durante la configurazione di rete nel server devono corrispondere al formato fornito dai computer client per essere correttamente usati per il bypass multimediale. Un client Lync prende l'indirizzo IP locale e maschera l'indirizzo IP con la subnet mask associata. Quando si determina l'ID di bypass associato a ogni client, il registrar confronterà l'elenco delle subnet IP associate a ogni sito di rete rispetto alla subnet fornita dal client per una corrispondenza esatta. Per questo motivo, è importante che le subnet immesse durante la configurazione di rete sul server siano subnet effettive anziché sottoreti virtuali. Se si distribuisce il controllo di ammissione alle chiamate, ma non il bypass multimediale, il controllo di ammissione delle chiamate funzionerà correttamente anche se si configurano sottoreti virtuali.<BR>Ad esempio, se un client Lync accede a un computer con un indirizzo IP di 172.29.81.57 con una subnet mask IP 255.255.255.0, richiederà l'ID di bypass associato alla subnet 172.29.81.0. Se la subnet è definita come 172.29.0.0/16, anche se il client appartiene alla subnet virtuale, il registrar non considererà questa corrispondenza perché il registrar Cerca specificamente la subnet 172.29.81.0. Di conseguenza, è importante che l'amministratore immetta le subnet esattamente come fornite dai client Lync (che vengono provisionati con le subnet durante la configurazione di rete, sia in modo statico che tramite DHCP).



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a>Associazione di subnet con i siti di rete

Ogni subnet nella rete aziendale deve essere associata a un sito di rete, ovvero ogni subnet deve essere associata a una posizione geografica. Questa associazione di subnet consente alle funzionalità vocali avanzate dell'organizzazione di individuare gli endpoint geograficamente. Ad esempio, l'individuazione degli endpoint consente a CAC di regolare il flusso di dati audio e video in tempo reale da e verso il sito di rete.

Per associare subnet a siti di rete, è possibile usare la sezione **configurazione di rete** del pannello di controllo di Lync Server oppure usare Lync Server Management Shell. Per istruzioni, vedere [associare una subnet a un sito di rete in Lync server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) nella documentazione di distribuzione oppure fare riferimento alla documentazione di Lync Server Management Shell.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione del servizio Controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
[Pianificazione per i servizi di emergenza (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[Pianificazione del bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

