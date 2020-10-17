---
title: 'Lync Server 2013: determinare i requisiti di porte e firewall A/V esterni'
description: 'Lync Server 2013: determinare i requisiti di porte e firewall A/V esterni.'
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
ms.openlocfilehash: 38c2a8c1e8e332a4a1e65adb87a1e962e82941c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550932"
---
# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a>Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-29_

La comunicazione audio/video (A/V) può essere complessa. A causa della natura dei protocolli utilizzati in A/V e in che modo i client e i server utilizzano i protocolli, viene garantita una sezione speciale che spiega le differenze tra le versioni client e server.

Utilizzare la seguente tabella di porte e firewall a/V per determinare i requisiti del firewall e le porte da aprire. Rivedere quindi la terminologia relativa alla conversione NAT (Network Address Translation) perché quest'ultima può essere implementata in diversi modi. Per un esempio dettagliato delle impostazioni delle porte del firewall, vedere le architetture di riferimento in [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a>Utilizzo di protocollo generale per UDP e TCP in audio/video e traffico multimediale

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Trasporto audio/video</th>
<th>Usage</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>Protocollo di trasporto Layer preferito per audio e video</p></td>
</tr>
<tr class="even">
<td><p>TCP</p></td>
<td><p>Protocollo di livello di trasporto di fallback per audio e video</p>
<p>Protocollo di trasporto Layer obbligatorio per la condivisione di applicazioni in Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013</p>
<p>Protocollo di trasporto Layer obbligatorio per il trasferimento di file in Lync Server 2010 e Lync Server 2013</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a>Requisiti delle porte dei firewall A/V esterni per l'accesso degli utenti esterni

I requisiti delle porte del firewall per le interfacce SIP e di conferenza esterne (e interne) sono coerenti, indipendentemente dalla versione del client o dalla versione del partner federativo.

Non si applicano gli stessi requisiti per l'interfaccia esterna Audio/Video Edge. Per la Federazione con Office Communications Server 2007, è necessario che il servizio A/V Edge richieda che le regole del firewall esterno consentano il traffico RTP/TCP e RTP/UDP nell'intervallo di porte da 50.000 a 59.999 per il flusso in entrambe le direzioni. La tabella precedente presuppone che Lync Server 2013 sia il partner federativo principale e che sia configurato per la comunicazione con uno degli altri tipi di partner di Federazione elencati.

Se si configura l'intervallo di porte audio/video di 50000-59.999, è necessario tenere presente che l'intervallo di porte conterrà le porte di origine per le comunicazioni ai partner federativi. In dettaglio, considerare che una comunicazione viene avviata da un partner federativo. La comunicazione dalle porte del servizio A/V Edge nell'intervallo 50000-59.999 si collegherà alla porta prevista TCP 443 del servizio A/V Edge del partner. Al contrario, il traffico in ingresso alla porta del servizio A/V Edge TCP 443 avrà una porta di origine nell'intervallo di 50000-59.999.

Diversi firewall e criteri per l'amministrazione del firewall possono richiedere la configurazione delle sole regole di destinazione oppure richiedono la configurazione di origine e di destinazione. Se i requisiti sono solo per le porte di destinazione, i requisiti audio/video sono i seguenti:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>IP origine</th>
<th>IP destinazione</th>
<th>Porta di destinazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interfaccia del servizio A/V Edge</p></td>
<td><p>Qualsiasi</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Interfaccia del servizio A/V Edge</p></td>
<td><p>Qualsiasi</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia del servizio A/V Edge</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia del servizio A/V Edge</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


Se i criteri richiedono le definizioni delle regole del firewall in ingresso e in uscita, i requisiti audio/video sono i seguenti:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>IP origine</th>
<th>IP destinazione</th>
<th>Porta di origine</th>
<th>Porta di destinazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interfaccia del servizio A/V Edge</p></td>
<td><p>Qualsiasi</p></td>
<td><p>TCP 50000-59.999</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Interfaccia del servizio A/V Edge</p></td>
<td><p>Qualsiasi</p></td>
<td><p>UDP 3478</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia del servizio A/V Edge</p></td>
<td><p>Qualsiasi</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia del servizio A/V Edge</p></td>
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

Se si sceglie di configurare gli indirizzi IP privati non instradabili per il servizio Edge, si applicano i requisiti NAT seguenti:

  - NAT può essere utilizzato solo con il bilanciamento del carico DNS. NAT non è supportato con una topologia Edge di bilanciamento del carico hardware.

  - NAT può essere utilizzato solo nell'interfaccia perimetrale esterna. NAT non è supportato per l'interfaccia perimetrale interna.

  - NAT deve essere simmetrico per il traffico in ingresso e in uscita.
    
  - Per il traffico proveniente da Internet, NAT deve modificare l'indirizzo IP di destinazione dall'indirizzo IP pubblico abilitato NAT del servizio a/V Edge all'indirizzo IP esterno. L'indirizzo IP di origine deve rimanere intatto, in modo che il servizio A/V Edge possa trovare il percorso multimediale ottimale.
  
  Ad esempio, nella direzione in ingresso nella figura seguente, l'indirizzo IP pubblico 131.107.155.30 è stato modificato nell'indirizzo IP esterno (privato) 10.45.16.10. L'indirizzo IP di origine è rimasto invariato.
  
  - Per il traffico proveniente dal servizio a/V Edge a Internet, NAT deve modificare l'indirizzo IP di origine dall'indirizzo IP esterno del servizio a/V Edge all'indirizzo IP pubblico abilitato per NAT.

Ad esempio, nella direzione in uscita della figura seguente, l'indirizzo IP esterno (privato) 10.45.16.10 è stato modificato nell'indirizzo IP pubblico 131.107.155.30.

**Nella figura seguente viene illustrato il modo in cui NAT cambia l'indirizzo IP di destinazione per il traffico in ingresso e l'indirizzo IP di origine per il traffico in uscita.**

![Modifica degli indirizzi IP di destinazione/origine](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Modifica degli indirizzi IP di destinazione/origine")

I punti principali sono i seguenti:

  - Traffico in ingresso al server che esegue il servizio A/V Edge, l'indirizzo IP di origine non cambia ma l'indirizzo IP di destinazione cambia da 131.107.155.30 all'indirizzo IP convertito di 10.45.16.10.

  - Il traffico in uscita dal server che esegue il servizio A/V Edge torna alla workstation, l'indirizzo IP di origine cambia dall'indirizzo IP pubblico del server all'indirizzo IP pubblico del server che esegue il servizio A/V Edge. L'IP di destinazione rimane l'indirizzo IP pubblico della workstation. Dopo che il pacchetto ha lasciato il primo dispositivo NAT in uscita, la regola sul dispositivo NAT cambia l'indirizzo IP di origine del server che esegue l'indirizzo IP dell'interfaccia esterna del servizio A/V Edge (10.45.16.10) al relativo indirizzo IP pubblico (131.107.155.30).

</div>

</div>

<span> </span>

</div>

</div>

</div>

