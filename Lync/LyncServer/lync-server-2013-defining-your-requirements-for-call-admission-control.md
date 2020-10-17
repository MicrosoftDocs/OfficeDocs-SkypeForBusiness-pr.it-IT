---
title: 'Lync Server 2013: definizione dei requisiti per il controllo di ammissione di chiamata'
description: 'Lync Server 2013: definizione dei requisiti per il controllo di ammissione di chiamata.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9f675ac5811e0c0c1c23dc76ebb8b4525857836
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545422"
---
# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a>Definizione dei requisiti per il controllo di ammissione di chiamata in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-28_

La pianificazione del controllo di ammissione di chiamata (CAC, Call Admission Control) richiede informazioni dettagliate sulla topologia di rete aziendale. Per pianificare più agevolmente i criteri di controllo di ammissione di chiamata, eseguire la procedura seguente.

1.  Identificare gli hub/backbone (noti come *aree di rete*) nella rete aziendale.

2.  Identificare gli uffici o le sedi (noti come *siti di rete*) in ogni area di rete.

3.  Stabilire la route di rete tra ogni coppia di aree di rete.

4.  Determinare i limiti di larghezza di banda per ogni collegamento WAN.
    
    <div>
    

    > [!NOTE]  
    > I limiti di larghezza di banda si riferiscono a quanto la larghezza di banda di un collegamento WAN viene allocata al traffico VoIP aziendale e audio/video. Se un collegamento WAN è indicato come "con larghezza di banda limitata" significa che il limite della larghezza di banda per il collegamento WAN è inferiore al traffico di picco previsto sul collegamento.

    
    </div>

5.  Identificare le subnet IP assegnate a ogni sito di rete.

Per illustrare questi concetti verrà utilizzata la topologia di rete di esempio mostrata della figura seguente.

**Topologia di esempio per il controllo di ammissione di chiamata**

![Esempio di topologia di rete di Litware Inc.](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Esempio di topologia di rete di Litware Inc.")

<div>


> [!NOTE]  
> Tutti i siti di rete sono associati a un'area di rete. Portland, Reno e Albuquerque, ad esempio, sono inclusi nell'area Nord America. In questa figura sono visualizzati solo i collegamenti WAN a cui sono applicati criteri di controllo di ammissione di chiamata, con limiti di larghezza di banda. I siti di rete Chicago, New York e Detroit sono visualizzati all'interno dell'ovale dell'area Nord America perché non presentano limitazioni di larghezza di banda e quindi non richiedono criteri di controllo di ammissione di chiamata.



</div>

I componenti di questa topologia di esempio sono spiegati nelle sezioni seguenti. Per informazioni dettagliate sulla pianificazione della topologia, inclusi i limiti relativi alla larghezza di banda, vedere [example: Gathering your requirements for Call Admission Control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).

<div>

## <a name="identify-network-regions"></a>Identificare le aree di rete

Un'area di rete rappresenta un backbone o un hub della rete.

Un backbone o un hub di rete è una parte dell'infrastruttura di rete di computer che interconnette parti diverse della rete, offrendo un percorso per lo scambio di informazioni tra LAN o subnet diverse. Un backbone può collegare reti diverse, da una piccola sede a un'area geografica più ampia. La capacità del backbone è generalmente più alta rispetto a quella delle reti che vi si connettono.

La topologia dell'esempio include tre aree di rete, ovvero Nord America, EMEA e APAC. Un'area di rete contiene un insieme di siti di rete (vedere la definizione di siti di rete più avanti in questo argomento). Collaborare con il team responsabile delle operazioni di rete per identificare le aree.

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a>Associazione di un sito centrale a ogni area di rete

Per ogni area di rete è necessario che sia definito un sito centrale di Lync Server. Il sito centrale selezionato deve avere la connettività di rete più efficiente e la larghezza di banda più ampia verso tutti gli altri siti nell'area di rete. La topologia di rete dell'esempio precedente mostra tre aree di rete, ognuna con un sito centrale che gestisce le decisioni relative al servizio Controllo di ammissione di chiamata. Per questo esempio l'associazione appropriata è illustrata nella tabella seguente.

<div>


> [!NOTE]  
> I siti centrali non corrispondono necessariamente a siti di rete. Negli esempi in questa documentazione alcuni siti centrali, come Chicago, Londra e Pechino, hanno lo stesso nome di alcuni siti di rete. Tuttavia, anche se un sito centrale e un sito di rete condividono lo stesso nome, il sito centrale è un elemento della topologia di Lync Server, mentre il sito di rete è una parte della rete globale in cui risiede la topologia di Lync Server.



</div>

### <a name="network-regions-central-sites-and-network-sites"></a>Aree di rete, siti centrali e siti di rete

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Area di rete</th>
<th>Sito Centrale</th>
<th>Siti di rete</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nord America</p></td>
<td><p>Chicago</p></td>
<td><p>Chicago</p>
<p>New York</p>
<p>Detroit</p>
<p>Portland</p>
<p>Reno</p>
<p>Albuquerque</p></td>
</tr>
<tr class="even">
<td><p>EMEA</p></td>
<td><p>Londra</p></td>
<td><p>Londra</p>
<p>Colonia</p></td>
</tr>
<tr class="odd">
<td><p>APAC</p></td>
<td><p>Pechino</p></td>
<td><p>Pechino</p>
<p>Manila</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a>Identificare i siti di rete

Un sito di rete rappresenta una località in cui l'organizzazione dispone di spazi fisici, ad esempio uffici, un gruppo di edifici o un campus. Uno spazio fisico con connettività LAN e WAN ad altri siti è considerata un sito di rete. Per iniziare, creare un inventario di tutti gli uffici dell'organizzazione. Nella topologia dell'esempio, l'area di rete Nord America è costituita dai siti di rete seguenti: New York, Chicago, Detroit, Portland, Reno e Albuquerque.

È necessario associare ogni sito di rete a un'area di rete. A seconda che il sito di rete abbia o meno un collegamento WAN limitato, al sito di rete vengono associati criteri per la larghezza di banda. Per informazioni dettagliate sui criteri di controllo di ammissione di chiamata e la larghezza di banda che è possibile allocare tramite tali criteri, vedere "Definire i criteri di larghezza di banda" di seguito in questo argomento. Per configurare i criteri di controllo di ammissione di chiamata, è necessario associare i siti di rete alle aree di rete e quindi creare i criteri di allocazione della larghezza di banda da applicare alle connessioni con larghezza di banda limitata tra un determinato sito o una particolare area e le connessioni WAN tra siti e aree.

</div>

<div>

## <a name="identify-network-links"></a>Identificare i collegamenti di rete

I collegamenti di rete rappresentano connessioni alla rete WAN fisica che collega i vari siti e aree. Nell'esempio di topologia utilizzato in questo argomento esistono due collegamenti di rete tra aree, cinque collegamenti di rete tra aree e siti e un collegamento di rete tra due siti.

I due collegamenti tra aree sono tra l'area Nord America ed EMEA, rappresentato come COLLEGAMENTO-NA-EMEA e tra APAC ed EMEA, rappresentato come COLLEGAMENTO-EMEA-APAC.

I collegamenti tra siti sono indicati dalle linee che connettono Portland, Reno e Albuquerque all'area Nord America, Manila all'area APAC e Colonia all'area EMEA. La linea tra Reno e Albuquerque mostra un collegamento di rete diretto tra questi due siti.

</div>

<div>

## <a name="define-bandwidth-policies"></a>Definire criteri di larghezza di banda

Collaborare con il team responsabile delle operazioni di rete per stabilire la quantità di larghezza di banda WAN disponibile per il traffico audio e video in tempo reale sui collegamenti WAN dell'organizzazione. I criteri di larghezza di banda vengono in genere applicati ai collegamenti WAN se l'uso della larghezza di banda è vincolato, ovvero se è previsto che sia superiore alla larghezza di banda disponibile per l'allocazione alle modalità audio e video.

I *criteri di larghezza di banda* del servizio Controllo di ammissione di chiamata definiscono la larghezza di banda massima che può essere riservata per le modalità audio e video in tempo reale. Poiché il servizio Controllo di ammissione di chiamata non limita la larghezza di banda di altri tipi di traffico, non può impedire che altri tipi di traffico dati, ad esempio trasferimenti di file di grandi dimensioni o flussi di musica, usino tutta la larghezza di banda.

I criteri di larghezza di banda per il controllo di ammissione di chiamata possono definire solo alcuni o tutti gli aspetti seguenti:

  - Larghezza di banda totale massima allocata per i contenuti audio.

  - Larghezza di banda totale massima allocata per i contenuti video.

  - Larghezza di banda massima allocata per una singola chiamata (sessione) audio.

  - Larghezza di banda massima allocata per una singola chiamata (sessione) video.

<div>


> [!NOTE]  
> Tutti i valori di larghezza di banda per il controllo di ammissione di chiamata rappresentano i limiti di larghezza di banda <EM>unidirezionale</EM> massimi.



</div>

<div>


> [!NOTE]  
> Le caratteristiche dei criteri vocali di Lync Server 2013 offrono la possibilità di ignorare i controlli dei criteri di larghezza di banda per le chiamate in arrivo all'utente (non per le chiamate in uscita inserite dall'utente). Dopo l'attivazione della sessione, il consumo di larghezza di banda verrà conteggiato accuratamente. Questa impostazione dovrebbe essere usata raramente. Per informazioni dettagliate, vedere <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">creare un criterio vocale e configurare i record di utilizzo PSTN in Lync server 2013</A> o <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

Per ottimizzare l'uso della larghezza di banda su base per utente, tenere conto del tipo dei codec audio e video che verranno usati. In particolare, evitare di allocare una quantità di larghezza di banda insufficiente per un codec con uso previsto frequente. Viceversa, se si desidera impedire l'uso di un codec che richiede maggiore larghezza di banda, è consigliabile impostare la larghezza di banda massima per sessione su un valore sufficientemente basso da scoraggiarne l'uso. Per quando riguarda i contenuti audio, non tutti i codec sono disponibili per qualsiasi scenario. Ad esempio:

  - Le chiamate audio peer-to-peer tra gli endpoint di Lync utilizzeranno RTAudio (8kHz) o RTAudio (16kHz) quando si determina la larghezza di banda e la priorità dei codec.

  - Le chiamate in conferenza tra gli endpoint di Lync e il servizio A/V Conferencing utilizzeranno G. 722 o Siren.

  - Le chiamate alla rete PSTN (Public Switched Telephone Network) da o verso endpoint di Lync utilizzeranno G. 711 o RTAudio (8kHz).

Fare riferimento alla tabella seguente per l'ottimizzazione delle impostazioni di larghezza di banda massima per sessione.

### <a name="bandwidth-utilization-by-codecs"></a>Utilizzo della larghezza di banda in base ai codec

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Codec</th>
<th>Requisito di larghezza di banda senza correzione FEC (Forward Error Correction)</th>
<th>Requisito di larghezza di banda con correzione FEC (Forward Error Correction)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio (8kHz)</p></td>
<td><p>49,8 kbps</p></td>
<td><p>61,6 kbps</p></td>
</tr>
<tr class="even">
<td><p>RTAudio (16kHz)</p></td>
<td><p>67 kbps</p></td>
<td><p>96 kbps</p></td>
</tr>
<tr class="odd">
<td><p>Sirena</p></td>
<td><p>57,6 kbps</p></td>
<td><p>73,6 kbps</p></td>
</tr>
<tr class="even">
<td><p>G. 711</p></td>
<td><p>102 kbps</p></td>
<td><p>166 kbps</p></td>
</tr>
<tr class="odd">
<td><p>G. 722</p></td>
<td><p>105,6 kbps</p></td>
<td><p>169,6 kbps</p></td>
</tr>
<tr class="even">
<td><p>RTVideo (CIF 15 fps)</p></td>
<td><p>260 kbps</p></td>
<td><p>NA</p></td>
</tr>
<tr class="odd">
<td><p>RTVideo (VGA 30 fps)</p></td>
<td><p>610 kbps</p></td>
<td><p>NA</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> I requisiti di larghezza di banda tengono conto dell'overhead per Ethernet II, IP, UDP (User Datagram Protocol), RTP (Real-time Transport Protocol) e SRTP (Secure Real-time Transport Protocol), oltre a includere 10 kbps per l'overhead RTCP.



</div>

I codec G.722.1 e Siren sono simili, ma offrono velocità in bit diverse.

G. 722, il codec predefinito per le conferenze di Lync Server, è completamente diverso dai codec G. 722.1 e Siren.

Il codec Siren viene utilizzato in Lync Server nei casi seguenti:

  - Se i criteri di larghezza di banda sono impostati su un valore troppo basso per l'uso di G.722

  - Se un client Communications Server 2007 o Communications Server 2007 R2 si connette a un servizio Lync Server Conferencing (poiché tali client non supportano il codec G. 722).

### <a name="bandwidth-utilization-by-scenario"></a>Utilizzo della larghezza di banda in base allo scenario

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Scenario</th>
<th>Requisito di larghezza di banda ottimizzata per la quantità (kbps)</th>
<th>Requisito di larghezza di banda per la modalità con bilanciamento (kbps)</th>
<th>Requisito di larghezza di banda ottimizzata per la qualità (kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamate audio peer-to-peer</p></td>
<td><p>45 kbps</p></td>
<td><p>62 kbps</p></td>
<td><p>91 kbps</p></td>
</tr>
<tr class="even">
<td><p>Conferenze telefoniche</p></td>
<td><p>53 kbps</p></td>
<td><p>101 kbps</p></td>
<td><p>165 kbps</p></td>
</tr>
<tr class="odd">
<td><p>Chiamate PSTN (tra Lync 2013 e il gateway PSTN, con il bypass multimediale)</p></td>
<td><p>97 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="even">
<td><p>Chiamate PSTN (tra Lync 2013 e Mediation Server, senza bypass multimediale)</p></td>
<td><p>45 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="odd">
<td><p>Chiamate PSTN (tra Mediation Server e gateway PSTN, senza bypass multimediale)</p></td>
<td><p>97 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="even">
<td><p>Chiamate di Lync-Polycom</p></td>
<td><p>101 kbps</p></td>
<td><p>101 kbps</p></td>
<td><p>101 kbps</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a>Identificare le subnet IP

Per ogni sito di rete sarà necessario collaborare con l'amministratore della rete per stabilire quali subnet IP sono assegnate a ogni sito di rete. Se l'amministratore della rete ha già organizzato le subnet IP in aree di rete e siti di rete, il lavoro risulterà notevolmente semplificato.

In questo esempio, al sito New York nell'area Nord America sono assegnate le subnet IP seguenti: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si supponga che Bob, che di solito lavora a Detroit, si sposti nell'ufficio di New York per un corso di formazione. Quando accende il suo computer e si connette alla rete, al computer verrà assegnato un indirizzo IP in uno dei quattro intervalli prenotati per New York, ad esempio 172.29.80.103.

<div>


> [!WARNING]  
> Le subnet IP specificate durante la configurazione della rete nel server devono corrispondere al formato specificato dai computer client per poter essere utilizzate correttamente per il bypass multimediale. Un client Lync prende l'indirizzo IP locale e maschera l'indirizzo IP con la subnet mask associata. Durante la determinazione dell'ID di bypass associato a ogni client, la funzione di registrazione confronterà l'elenco delle subnet IP associate a ogni sito di rete con la subnet fornita dal client per individuare una corrispondenza esatta. Per questo motivo è importante che le subnet immesse durante la configurazione della rete nel server siano subnet effettive, anziché virtuali. Se si implementa il servizio Controllo di ammissione di chiamata ma non Media Bypass, il servizio Controllo di ammissione di chiamata funzionerà in modo corretto anche se si configurano subnet virtuali.<BR>Ad esempio, se un client accede a un computer con un indirizzo IP di 172.29.81.57 con una subnet mask IP 255.255.255.0, Lync 2013 richiederà l'ID di bypass associato a subnet 172.29.81.0. Se la subnet è definita come 172.29.0.0/16, anche se il client appartiene alla subnet virtuale, la funzione di registrazione non la considererà una corrispondenza esatta perché cerca nello specifico la subnet 172.29.81.0. Pertanto, è importante che l'amministratore entri nelle subnet esattamente come indicato dai client Lync (che vengono provisionati con subnet durante la configurazione di rete in modo statico o tramite DHCP).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

