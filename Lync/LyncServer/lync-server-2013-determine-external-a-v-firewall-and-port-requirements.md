---
title: 'Lync Server 2013: Determinare i requisiti di porte e firewall A/V esterni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d5519ef37ff334ddf196e94b40aa7df14d69d25
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a>Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-29_

La comunicazione audio/video (A/V) può essere complessa. A causa della natura dei protocolli usati in A/V e in che modo i client e i server usano i protocolli, è garantita una sezione speciale per spiegare le differenze tra le versioni client e server.

Usare la tabella a/V del firewall e della porta seguente per determinare i requisiti del firewall e le porte da aprire. Esaminare quindi la terminologia NAT (Network Address Translation) perché NAT può essere implementato in molti modi diversi. Per un esempio dettagliato delle impostazioni della porta del firewall, vedere le architetture di riferimento in [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a>Utilizzo di protocolli generali per UDP e TCP nel traffico audio/video e multimediale

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Trasporto audio/video</th>
<th>L'uso</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>Protocollo di livello di trasporto preferito per audio e video</p></td>
</tr>
<tr class="even">
<td><p>TCP</p></td>
<td><p>Protocollo di livello di trasporto di fallback per audio e video</p>
<p>Protocollo di livello di trasporto obbligatorio per la condivisione delle applicazioni in Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013</p>
<p>Protocollo di livello di trasporto obbligatorio per il trasferimento di file in Lync Server 2010 e Lync Server 2013</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a>Requisiti della porta firewall esterni A/V per l'accesso degli utenti esterni

I requisiti della porta del firewall per le interfacce SIP e per le conferenze esterne (e interne) sono coerenti, indipendentemente dalla versione del client o dalla versione del partner federativo.

Lo stesso non è vero per l'interfaccia esterna del bordo audio/video. Per la Federazione con Office Communications Server 2007, l'A/V Edge Service richiede che le regole del firewall esterno consentano il traffico RTP/TCP e RTP/UDP nell'intervallo di porte da 50.000 a 59.999 per il flusso in entrambe le direzioni. La tabella precedente presuppone che Lync Server 2013 sia il partner principale della Federazione e sia configurato per comunicare con uno degli altri tipi di partner federativi elencati.

La configurazione dell'intervallo di porte audio/video di 50000-59.999 deve tenere presente che l'intervallo di porte conterrà le porte di origine per le comunicazioni ai partner federativi. In dettaglio, tenere presente che una comunicazione viene avviata da un partner federativo. La comunicazione dalle porte a/V Edge service nell'intervallo 50000-59.999 si connetterà alla porta prevista TCP 443 dell'A/V Edge del partner. Viceversa, il traffico in entrata per la porta del servizio a/V Edge TCP 443 avrà una porta di origine nell'intervallo di 50000-59.999.

I diversi firewall e criteri per l'amministrazione del firewall possono richiedere la configurazione di sole regole di destinazione oppure possono richiedere sia la configurazione dell'origine che quella della destinazione. Se i requisiti sono solo per le porte di destinazione, i requisiti audio/video sono i seguenti:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>IP di origine</th>
<th>IP di destinazione</th>
<th>Porta di destinazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interfaccia A/V Edge service</p></td>
<td><p>Qualsiasi</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Interfaccia A/V Edge service</p></td>
<td><p>Qualsiasi</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia A/V Edge service</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia A/V Edge service</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


Se i criteri richiedono definizioni di regole firewall in ingresso e in uscita, i requisiti audio/video sono i seguenti:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>IP di origine</th>
<th>IP di destinazione</th>
<th>Porta di origine</th>
<th>Porta di destinazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interfaccia A/V Edge service</p></td>
<td><p>Qualsiasi</p></td>
<td><p>TCP 50000-59.999</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Interfaccia A/V Edge service</p></td>
<td><p>Qualsiasi</p></td>
<td><p>UDP 3478</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia A/V Edge service</p></td>
<td><p>Qualsiasi</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia A/V Edge service</p></td>
<td><p>Qualsiasi</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Microsoft Office Communications Server 2007 richiede una configurazione leggermente diversa. L'intervallo di porte TCP e UDP di 50000-59.999 deve essere aperto in ingresso e in uscita. Questo requisito è solo per Office Communicator 2007. Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013 richiedono solo l'intervallo TCP 50000-59.999 aperto in uscita.



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a>Requisiti NAT per il servizio Edge

I requisiti NAT seguenti si applicano se si sceglie di configurare indirizzi IP privati non instradabili per il servizio Edge:

  - NAT può essere usato solo con il bilanciamento del carico DNS. NAT non è supportato con una topologia di Edge di bilanciamento del carico hardware (HLB).

  - NAT può essere usato solo nell'interfaccia esterna di Edge. NAT non è supportato nell'interfaccia Edge interna.

  - NAT deve essere simmetrico per il traffico in entrata e in uscita.
    
  - Per il traffico da Internet, NAT deve cambiare l'indirizzo IP di destinazione dall'indirizzo IP pubblico abilitato per NAT del servizio a/V Edge all'indirizzo IP esterno. L'indirizzo IP di origine deve rimanere intatto, in modo che il servizio A/V Edge sia in grado di trovare il percorso multimediale ottimale.
  
  Ad esempio, nella direzione in entrata della figura seguente l'indirizzo IP pubblico 131.107.155.30 è stato modificato in 10.45.16.10 indirizzo IP (privato) esterno. L'indirizzo IP di origine rimane invariato.
  
  - Per il traffico dal servizio a/V Edge a Internet, NAT deve modificare l'indirizzo IP di origine dall'indirizzo IP esterno dell'a/V Edge service all'indirizzo IP pubblico abilitato per NAT.

Ad esempio, nella direzione in uscita della figura seguente, l'indirizzo IP esterno (privato) 10.45.16.10 è stato modificato nell'indirizzo IP pubblico 131.107.155.30.

**La figura seguente mostra il modo in cui NAT cambia l'indirizzo IP di destinazione per il traffico in entrata e l'indirizzo IP di origine per il traffico in uscita.**

![Modifica degli indirizzi IP di origine/destinazione](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Modifica degli indirizzi IP di origine/destinazione")

I punti chiave sono:

  - Traffico in ingresso al server che esegue il servizio A/V Edge, l'indirizzo IP di origine non cambia, ma l'indirizzo IP di destinazione cambia da 131.107.155.30 all'indirizzo IP tradotto di 10.45.16.10.

  - Traffico in uscita dal server che riporta il servizio a/V Edge alla workstation, l'indirizzo IP di origine viene modificato dall'indirizzo IP pubblico del server all'indirizzo IP pubblico del server in cui è in uso il servizio A/V Edge. L'IP di destinazione rimane l'indirizzo IP pubblico della workstation. Dopo che il pacchetto ha lasciato il primo dispositivo NAT in uscita, la regola sul dispositivo NAT cambia l'indirizzo IP di origine del server che gestisce l'indirizzo IP dell'interfaccia esterna del servizio A/V (10.45.16.10) con l'indirizzo IP pubblico (131.107.155.30).

</div>

</div>

<span> </span>

</div>

</div>

</div>

