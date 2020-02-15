---
title: 'Lync Server 2013: Panoramica dei tipi di indirizzi IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: feb900c6f3d2ac426c184048986a7a751a205874
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a>Panoramica dei tipi di indirizzi IP per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-29_

Sono disponibili tre opzioni per la configurazione degli indirizzi IP in Lync Server 2013. È possibile configurare Lync Server 2013 per supportare solo IP versione 4 (IPv4), solo IP versione 6 (IPv6) o una combinazione di entrambi (noto come *stack doppio*). Per ogni tipo di configurazione è necessario considerare diversi problemi:

  - **IPv4**   è stato creato solo IPv6 perché il mondo è in esecuzione fuori degli indirizzi IPv4. In futuro IPv6 sarà completamente supportato in tutto il mondo, ma al momento molte aziende e molti dispositivi con cui potrebbe essere necessario comunicare non lo supportano ancora. Una configurazione solo IPv4 consentirà di garantire che l'implementazione di Lync Server sia in grado di comunicare con la maggior parte dei dispositivi esistenti.

  - **IPv6 solo**   al contrario, un'implementazione IPv6 completa, in questo momento, escluderà la comunicazione con molti dispositivi esistenti.

  - **Dual**   stack dual stack è una rete in cui sono abilitati sia gli indirizzi IPv4 che IPv6. Questa configurazione è supportata in Lync Server 2013 perché, nella maggior parte dei casi, la transizione da Full-IPv4 a full-IPv6 richiederà diversi anni.

Nelle sezioni seguenti viene illustrata la compatibilità tra queste tre configurazioni per diverse funzionalità di Lync Server.

<div>


> [!NOTE]  
> La configurazione client o server con il solo protocollo IPv6 è supportata solo per fini di ricerca e di convalida. La configurazione Solo IPv6 non è supportata nella distribuzione di produzione.



</div>

<div>

## <a name="client-registration"></a>Registrazione client


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Rete endpoint client</th>
<th>Rete server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Dual stack</p></td>
</tr>
<tr class="odd">
<td><p>Dual stack</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Dual stack</p></td>
<td><p>Dual stack</p></td>
</tr>
<tr class="odd">
<td><p>Dual stack</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Dual stack</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a>Client peer-to-peer

La comunicazione peer-to-peer include audio, audio/video, condivisione di applicazioni e trasferimento di file. Dopo la corretta registrazione di entrambi i client, sono supportate le combinazioni seguenti.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Endpoint client 1</th>
<th>Endpoint client 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Dual stack</p></td>
</tr>
<tr class="odd">
<td><p>Dual stack</p></td>
<td><p>Dual stack</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Dual stack</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a>Conferenza

Servizi di conferenza include audio/video, condivisione di applicazioni e collaborazione dati (condivisione file e lavagna).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Rete endpoint client</th>
<th>Rete server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Dual stack</p></td>
</tr>
<tr class="odd">
<td><p>Dual stack</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Dual stack</p></td>
<td><p>Dual stack</p></td>
</tr>
<tr class="odd">
<td><p>Dual stack</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Dual stack</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a>Mediation Server/PSTN

Lync Server 2013 non supporta il bypass multimediale per le chiamate PSTN (Public Switched Telephone Network) se il traffico avviene tramite un'interfaccia IPv6. Se il bypass multimediale è necessario, è consigliabile configurare il gateway PSTN su IPv4.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Interfaccia principale*</th>
<th>Interfaccia PSTN (in Mediation Server)</th>
<th>Impostazioni del gateway PSTN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>Dual stack</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Dual stack</p></td>
<td><p>Dual stack</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>Dual stack</p></td>
<td><p>Dual stack</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


\*L'interfaccia principale è l'interfaccia che comunica con i componenti di Lync Server.

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a>Comunicazioni peer-to-peer con utenti remoti

La comunicazione peer-to-peer con utenti remoti include messaggistica istantanea, audio/video, condivisione di applicazioni e trasferimento di file.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Rete utenti remoti</th>
<th>Server perimetrale (perimetro esterno)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Dual stack</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>Dual stack</p></td>
<td><p>Dual stack</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Dual stack</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a>Configurazione di pool Front End e di pool di server perimetrali

Nella tabella seguente viene illustrata la matrice di supporto tra il pool Front End Server e il pool di server perimetrali interni.

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a>Matrice di pool Front End e di pool di server perimetrali (perimetro interno)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>Pool di server perimetrali: IPv4</strong></p></td>
<td><p><strong>Pool di server perimetrali: Dual Stack</strong></p></td>
<td><p><strong>Pool di server perimetrali: IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Pool Front End: IPv4</strong></p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool Front End: Dual Stack</strong></p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool Front End: IPv6</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>Sì*</p></td>
</tr>
</tbody>
</table>


\*Utilizzare questa combinazione solo in un ambiente lab.

La tabella seguente è una matrice delle combinazioni supportate di interfacce di server perimetrali interni ed esterni.

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a>Matrice di pool di server perimetrali (perimetro interno) e di pool di server perimetrali (perimetro esterno)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>Pool di server perimetrali (perimetro esterno): IPv4</strong></p></td>
<td><p><strong>Pool di server perimetrali (perimetro esterno): Dual Stack</strong></p></td>
<td><p><strong>Pool di server perimetrali (perimetro esterno): IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Pool di server perimetrali (perimetro interno): IPv4</strong></p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool di server perimetrali (perimetro interno): Dual Stack</strong></p></td>
<td><p>No</p></td>
<td><p>Sì</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool di server perimetrali (perimetro interno): IPv6</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>Sì*</p></td>
</tr>
</tbody>
</table>


\*Utilizzare questa combinazione solo in un ambiente lab.

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a>Supporto vocale aziendale avanzato per IPv6

Le distribuzioni che includono il servizio Controllo di ammissione di chiamata, Enhanced 9-1-1 (E9-1-1) o il bypass multimediale devono essere configurate come implementazioni Solo IPv4 o Dual Stack.

<div>


> [!NOTE]  
> In una distribuzione con stack doppio, anche se un client Lync si connette a un server Lync utilizzando IPv6, Lync farà il possibile per mappare un indirizzo IPv4 appropriato per il supporto di E9-1-1.



</div>

Il servizio informazioni percorso con indirizzi IPv6 non è supportato.

La messaggistica unificata di Exchange non supporta IPv6. Per la messaggistica unificata di Exchange, assicurasi che la risoluzione DNS non restituisca un indirizzo IPv6. L'utilizzo di IPv6 può causare errori quando le chiamate vengono inviate alla segreteria telefonica.

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a>Altre funzionalità di Lync Server 2013 supportate per IPv6

Oltre alle caratteristiche e ai componenti menzionati in precedenza, Lync Server 2013 supporta IPv6 per le caratteristiche seguenti:

  - **Chat persistente**
    
    È possibile configurare IPv6 per la chat persistente mediante il generatore di topologie. Per informazioni dettagliate sulla configurazione di chat persistente, vedere la documentazione relativa alla distribuzione di Persistent Chat Server.

  - **Rapporti qualità percepita dagli utenti (QoE) e registrazione dettagli chiamata (CDR)**
    
    Le relazioni di monitoraggio includono l'indirizzo IP così com'è archiviato nel database di Monitoring Server, che sia di tipo IPv4 o IPv6.

</div>

</div>

<span> </span>

</div>

</div>

</div>

