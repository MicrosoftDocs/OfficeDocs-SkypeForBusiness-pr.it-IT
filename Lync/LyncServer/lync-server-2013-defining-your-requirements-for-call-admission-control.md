---
title: "Lync Server 2013: Definizione dei requisiti dell'organizzazione per il controllo di ammissione di chiamata"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7737d303c7239df451c71b4f92d4dcd8dfe5b2e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a>Definizione dei requisiti dell'organizzazione per il controllo di ammissione di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-28_

Pianificazione per il controllo di ammissione alle chiamate (CAC) richiede informazioni dettagliate sulla topologia di rete aziendale. Per pianificare i criteri di controllo dell'ammissione alle chiamate, eseguire le operazioni seguenti.

1.  Identificare gli hub/backbone (chiamati aree di *rete*) all'interno della rete aziendale.

2.  Identificare gli uffici o le posizioni (detti *siti di rete*) all'interno di ogni area di rete.

3.  Determinare la route di rete tra ogni coppia di aree della rete.

4.  Determinare i limiti di larghezza di banda per ogni collegamento WAN.
    
    <div>
    

    > [!NOTE]  
    > I limiti di larghezza di banda si riferiscono alla quantità di larghezza di banda di un collegamento WAN assegnata al traffico VoIP aziendale e audio/video. Quando un collegamento WAN viene descritto come "vincolato alla larghezza di banda", il collegamento WAN ha un limite di larghezza di banda inferiore al traffico di picco previsto sul collegamento.

    
    </div>

5.  Identificare le subnet IP assegnate a ogni sito di rete.

Per spiegare questi concetti, useremo la topologia di rete di esempio mostrata nella figura seguente.

**Topologia di esempio per il controllo dell'ammissione alle chiamate**

Esempio di topologia di rete Inc. ![Litware]di(images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc.")

<div>


> [!NOTE]  
> Tutti i siti di rete sono associati a un'area di rete. Ad esempio, Portland, Reno e Albuquerque sono inclusi nell'area Nord America. In questa figura sono mostrati solo i collegamenti WAN con i criteri di CAC, con limiti di larghezza di banda. I siti di rete di Chicago, New York e Detroit sono visualizzati all'interno dell'area geografica Nord America, perché non sono vincolati alla larghezza di banda e quindi non richiedono criteri di CAC.



</div>

I componenti della topologia di esempio sono descritti nelle sezioni seguenti. Per informazioni dettagliate sulla pianificazione della topologia, inclusi i limiti di larghezza di banda, vedere [esempio: raccolta dei requisiti per il controllo dell'ammissione delle chiamate in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).

<div>

## <a name="identify-network-regions"></a>Identificare le aree di rete

Un'area di rete rappresenta un backbone di rete o un hub di rete.

Un backbone o un hub di rete fa parte dell'infrastruttura di rete di computer che interconnette diverse parti della rete, fornendo un percorso per lo scambio di informazioni tra LAN o subnet diverse. Una backbone può legare insieme diverse reti da una piccola posizione a un'area geografica ampia. La capacità della colonna vertebrale è in genere maggiore rispetto a quella delle reti che si connettono.

La topologia di esempio include tre aree di rete: Nord America, EMEA e APAC. Un'area di rete contiene una raccolta di siti di rete (vedere la definizione dei siti di rete più avanti in questo argomento). Collaborare con il team delle operazioni di rete per identificare le aree di rete.

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a>Associazione di un sito centrale a ogni area di rete

Il CAC richiede che sia definito un sito centrale di Lync Server per ogni area di rete. Il sito centrale è selezionato con la connettività di rete migliore e la larghezza di banda più alta per tutti gli altri siti all'interno dell'area di rete. L'esempio precedente della topologia di rete mostra tre aree di rete, ognuna con un sito centrale che gestisce le decisioni di CAC. Nell'esempio precedente l'associazione appropriata è illustrata nella tabella seguente.

<div>


> [!NOTE]  
> I siti centrali non corrispondono necessariamente ai siti di rete. Negli esempi di questa documentazione, alcuni siti centrali, ovvero Chicago, Londra e Pechino, condividono lo stesso nome dei siti di rete. Tuttavia, anche se un sito centrale e un sito di rete condividono lo stesso nome, il sito centrale è un elemento della topologia di Lync Server, mentre il sito di rete fa parte della rete complessiva in cui risiede la topologia di Lync Server.



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
<th>Sito centrale</th>
<th>Siti di rete</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>America del Nord</p></td>
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

Un sito di rete rappresenta una posizione in cui l'organizzazione ha una sede fisica, ad esempio uffici, un set di edifici o un campus. Un luogo fisico con una LAN e una connettività WAN ad altri siti è considerato un sito di rete. Iniziare a inventariare tutti gli uffici dell'organizzazione. Nella topologia di esempio l'area di rete Nord America è costituita dai siti di rete seguenti: New York, Chicago, Detroit, Portland, Reno e Albuquerque.

È necessario associare ogni sito di rete a un'area di rete. A seconda che il sito di rete disponga di un collegamento WAN vincolato, un criterio di larghezza di banda è associato al sito di rete. Per informazioni dettagliate sui criteri di CAC e sulla larghezza di banda allocata usandoli, vedere "definire i criteri di larghezza di banda" più avanti in questo argomento. Per configurare CAC, è possibile associare i siti di rete alle aree di rete e quindi creare criteri di assegnazione della larghezza di banda da applicare alle connessioni con vincoli di larghezza di banda tra un sito o un'area geografica specifica e le connessioni WAN tra i siti e le aree geografiche.

</div>

<div>

## <a name="identify-network-links"></a>Identificare i collegamenti di rete

I collegamenti di rete rappresentano connessioni alla WAN fisica che collega aree e siti diversi. Nella topologia di esempio ci sono due collegamenti di rete regionali, cinque collegamenti di rete tra aree geografiche e siti e un collegamento di rete tra due siti.

I due collegamenti internazionali si trovano tra Nord America e EMEA, rappresentati come NA-EMEA-LINK e tra APAC e EMEA, rappresentati come EMEA-APAC-LINK.

I collegamenti ai siti sono indicati dalle linee che collegano Portland, Reno e Albuquerque all'area Nord America, Manila alla regione APAC e Colonia nell'area EMEA. La linea tra Reno e Albuquerque Mostra un collegamento di rete diretta tra questi due siti.

</div>

<div>

## <a name="define-bandwidth-policies"></a>Definire i criteri di larghezza di banda

Collaborare con il team operazioni di rete per determinare la quantità di larghezza di banda WAN disponibile per il traffico audio e video in tempo reale nei collegamenti WAN dell'organizzazione. I criteri di larghezza di banda vengono in genere applicati ai collegamenti WAN se l'utilizzo della larghezza di banda è vincolato; Se si prevede che la larghezza di banda può essere allocata per le modalità audio e video.

I *criteri di larghezza di banda* CAC definiscono la larghezza di banda massima che può essere riservata per le modalità audio e video in tempo reale. Dato che CAC non limita la larghezza di banda di un altro traffico, non può impedire l'uso di tutta la larghezza di banda della rete, ad esempio un trasferimento di file di grandi dimensioni, lo streaming di musica.

I criteri di larghezza di banda CAC possono definire uno o tutti gli elementi seguenti:

  - Larghezza di banda totale massima allocata per l'audio.

  - Larghezza di banda totale massima allocata per il video.

  - Larghezza di banda massima allocata per una singola chiamata audio (sessione).

  - Larghezza di banda massima allocata per una singola chiamata video (sessione).

<div>


> [!NOTE]  
> Tutti i valori di larghezza di banda CAC rappresentano i limiti massimi di larghezza di banda <EM>unidirezionali</EM> .



</div>

<div>


> [!NOTE]  
> Le caratteristiche dei criteri vocali di Lync Server 2013 consentono di ignorare i controlli dei criteri di larghezza di banda per le chiamate in arrivo all'utente (non per le chiamate in uscita inserite dall'utente). Dopo la creazione della sessione, il consumo di larghezza di banda verrà contabilizzato in modo accurato. Questa impostazione deve essere usata con parsimonia. Per informazioni dettagliate, vedere <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">creare un criterio vocale e configurare i record di utilizzo PSTN in Lync server 2013</A> o <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

Per ottimizzare l'utilizzo della larghezza di banda per ogni singola sessione, prendere in considerazione il tipo di codec audio e video che verranno usati. In particolare, evitare di allocare larghezza di banda insufficiente per un codec che si prevede di usare di frequente. Se invece si vuole impedire l'uso di un codec che richiede più larghezza di banda, è consigliabile impostare la larghezza di banda massima per ogni sessione abbastanza bassa da scoraggiare tale utilizzo. Per l'audio, non tutti i codec sono disponibili per ogni scenario. Ad esempio:

  - Le chiamate audio peer-to-peer tra endpoint Lync utilizzeranno RTAudio (8kHz) o RTAudio (16kHz) quando si fattorizza la larghezza di banda e la priorità dei codec.

  - Le chiamate in conferenza tra endpoint Lync e il servizio di conferenza A/V utilizzeranno G. 722 o Siren.

  - Le chiamate alla rete PSTN (Public Switched Telephone Network) in o da endpoint di Lync utilizzeranno G. 711 o RTAudio (8kHz).

Usare la tabella seguente per ottimizzare le impostazioni di larghezza di banda massima per sessione.

### <a name="bandwidth-utilization-by-codecs"></a>Utilizzo della larghezza di banda per codec

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Codec</th>
<th>Requisito della larghezza di banda senza correzione degli errori in avanti (FEC)</th>
<th>Requisito della larghezza di banda con la correzione degli errori in avanti (FEC)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio (8kHz)</p></td>
<td><p>49,8 Kbps</p></td>
<td><p>61,6 Kbps</p></td>
</tr>
<tr class="even">
<td><p>RTAudio (16kHz)</p></td>
<td><p>67 kbps</p></td>
<td><p>96 kbps</p></td>
</tr>
<tr class="odd">
<td><p>Sirena</p></td>
<td><p>57,6 Kbps</p></td>
<td><p>73,6 Kbps</p></td>
</tr>
<tr class="even">
<td><p>G. 711</p></td>
<td><p>102 Kbps</p></td>
<td><p>166 kbps</p></td>
</tr>
<tr class="odd">
<td><p>G. 722</p></td>
<td><p>105,6 Kbps</p></td>
<td><p>169,6 Kbps</p></td>
</tr>
<tr class="even">
<td><p>RTVideo (CIF 15 fps)</p></td>
<td><p>260 Kbps</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="odd">
<td><p>RTVideo (VGA 30 fps)</p></td>
<td><p>610 Kbps</p></td>
<td><p>Non applicabile</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> I requisiti di larghezza di banda prendono in considerazione i costi seguenti: Ethernet II, IP, User Datagram Protocol (UDP), RTP (protocollo di trasporto in tempo reale) e SRTP (Secure Real-Time Transport Protocol). Includono inoltre 10 Kbps per l'overhead di RTCP.



</div>

I codec G. 722.1 e Siren sono simili, ma offrono diversi bitrate.

G. 722, il codec predefinito per i servizi di conferenza di Lync Server, è completamente diverso dai codec G. 722.1 e Siren.

Il codec Siren viene usato in Lync Server nelle situazioni seguenti:

  - Se i criteri di larghezza di banda sono impostati troppo bassi per l'uso di G. 722.

  - Se un client di Communications Server 2007 o Communications Server 2007 R2 si connette a un servizio di conferenza di Lync Server (poiché tali client non supportano il codec G. 722).

### <a name="bandwidth-utilization-by-scenario"></a>Utilizzo della larghezza di banda per scenario

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
<th>Requisito di larghezza di banda ottimizzato per quantità (Kbps)</th>
<th>Requisito della larghezza di banda per la modalità bilanciata (Kbps)</th>
<th>Requisiti di larghezza di banda ottimizzati per la qualità (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamate audio peer-to-peer</p></td>
<td><p>45 Kbps</p></td>
<td><p>62 kbps</p></td>
<td><p>91 kbps</p></td>
</tr>
<tr class="even">
<td><p>Chiamate in conferenza</p></td>
<td><p>53 Kbps</p></td>
<td><p>101 kbps</p></td>
<td><p>165 kbps</p></td>
</tr>
<tr class="odd">
<td><p>Chiamate PSTN (tra Lync 2013 e gateway PSTN, con il bypass multimediale)</p></td>
<td><p>97 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="even">
<td><p>Chiamate PSTN (tra Lync 2013 e Mediation Server, senza bypass multimediale)</p></td>
<td><p>45 Kbps</p></td>
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

Per ogni sito di rete, è necessario collaborare con l'amministratore di rete per determinare quali subnet IP vengono assegnate a ogni sito di rete. Se l'amministratore di rete ha già organizzato le subnet IP nelle aree di rete e nei siti di rete, il lavoro è semplificato in modo significativo.

In questo esempio, nel sito di New York nell'area Nord America sono assegnate le subnet IP seguenti: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Supponiamo che Roberto, che lavora in genere a Detroit, viaggi nell'ufficio di New York per la formazione. Quando accende il computer e si connette alla rete, il computer riceverà un indirizzo IP in uno dei quattro intervalli riservati a New York, ad esempio 172.29.80.103.

<div>


> [!WARNING]  
> Le subnet IP specificate durante la configurazione di rete nel server devono corrispondere al formato fornito dai computer client per poter essere usate correttamente per il bypass multimediale. Un client Lync prende l'indirizzo IP locale e maschera l'indirizzo IP con la subnet mask associata. Quando si determina l'ID di bypass associato a ogni client, il registrar confronterà l'elenco delle subnet IP associate a ogni sito di rete rispetto alla subnet fornita dal client per una corrispondenza esatta. Per questo motivo, è importante che le subnet immesse durante la configurazione di rete sul server siano subnet effettive anziché sottoreti virtuali. Se si distribuisce il controllo di ammissione alle chiamate, ma non il bypass multimediale, il controllo di ammissione delle chiamate funzionerà correttamente anche se si configurano sottoreti virtuali.<BR>Ad esempio, se un client esegue l'accesso in un computer con un indirizzo IP di 172.29.81.57 con una subnet mask IP 255.255.255.0, Lync 2013 richiederà l'ID di bypass associato alla subnet 172.29.81.0. Se la subnet è definita come 172.29.0.0/16, anche se il client appartiene alla subnet virtuale, il registrar non considererà questa corrispondenza perché il registrar Cerca specificamente la subnet 172.29.81.0. Di conseguenza, è importante che l'amministratore immetta le subnet esattamente come fornite dai client Lync (che vengono provisionate con subnet durante la configurazione di rete in modo statico o tramite DHCP).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

