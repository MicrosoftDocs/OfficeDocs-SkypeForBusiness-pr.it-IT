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
ms.openlocfilehash: 9d1172fc7da9600de036312adb05548b51dea6b0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a>Panoramica dei tipi di indirizzi IP per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-29_

Sono disponibili tre opzioni per la configurazione degli indirizzi IP in Lync Server 2013. È possibile configurare Lync Server 2013 per supportare solo IP versione 4 (IPv4), solo IP versione 6 (IPv6) o una combinazione di entrambi (noto come *stack doppio*). Esistono diversi problemi da considerare con ogni tipo di configurazione:

  - **IPv4 solo**   IPv6 è stato creato perché il mondo è in esaurimento degli indirizzi IPv4. In definitiva, IPv6 sarà completamente supportato in tutto il mondo, ma in questo momento, molte aziende e dispositivi di cui l'organizzazione potrebbe dover comunicare non supportano ancora IPv6 e potrebbero non essere da qualche tempo. Una configurazione solo IPv4 consentirà di garantire che l'implementazione di Lync Server possa comunicare con la maggior parte dei dispositivi esistenti.

  - **IPv6 solo**   al contrario, un'implementazione completa di IPv6, in questo momento, escluderà la comunicazione con molti dispositivi esistenti.

  - **Dual**   stack dual stack è una rete in cui sono abilitati sia gli indirizzi IPv4 che IPv6. Questa configurazione è supportata in Lync Server 2013 perché nella maggior parte dei casi la transizione da Full-IPv4 a full-IPv6 avrà diversi anni.

Le sezioni seguenti illustrano la compatibilità tra queste tre configurazioni per varie funzionalità di Lync Server.

<div>


> [!NOTE]  
> La configurazione client o server con IPv6 è supportata solo per scopi di laboratorio o di convalida. La configurazione solo IPv6 non è supportata nella distribuzione della produzione.



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
<th>Server di rete</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Stack doppio</p></td>
</tr>
<tr class="odd">
<td><p>Stack doppio</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Stack doppio</p></td>
<td><p>Stack doppio</p></td>
</tr>
<tr class="odd">
<td><p>Stack doppio</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Stack doppio</p></td>
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

Le comunicazioni peer-to-peer includono audio, audio/video, condivisione applicazioni e trasferimento di file. Dopo aver registrato correttamente entrambi i client, sono supportate le combinazioni seguenti.


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
<td><p>Stack doppio</p></td>
</tr>
<tr class="odd">
<td><p>Stack doppio</p></td>
<td><p>Stack doppio</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Stack doppio</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a>Servizi di conferenza

I servizi di conferenza includono audio/video, condivisione applicazioni e collaborazione ai dati (lavagna e condivisione di file).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Rete endpoint client</th>
<th>Server di rete</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Stack doppio</p></td>
</tr>
<tr class="odd">
<td><p>Stack doppio</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Stack doppio</p></td>
<td><p>Stack doppio</p></td>
</tr>
<tr class="odd">
<td><p>Stack doppio</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Stack doppio</p></td>
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

Lync Server 2013 non supporta il bypass multimediale per le chiamate PSTN (Public Switched Telephone Network), se il traffico avviene tramite un'interfaccia IPv6. Se è necessario un bypass multimediale, è consigliabile che il gateway PSTN sia configurato per IPv4.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Interfaccia primaria *</th>
<th>Interfaccia PSTN (in Mediation Server)</th>
<th>Impostazione del gateway PSTN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>Stack doppio</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Stack doppio</p></td>
<td><p>Stack doppio</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>Stack doppio</p></td>
<td><p>Stack doppio</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


\*L'interfaccia principale è l'interfaccia che comunica con i componenti di Lync Server.

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a>Comunicazioni peer-to-peer degli utenti remoti

Le comunicazioni peer-to-peer con gli utenti remoti includono messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Rete remota degli utenti</th>
<th>Edge Server (bordo esterno)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Stack doppio</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>Stack doppio</p></td>
<td><p>Stack doppio</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Stack doppio</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a>Configurazione di pool e Edge pool Front-End

La tabella seguente mostra la matrice di supporto tra il pool del server front-end e il pool di Edge Server interno.

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a>Pool di front end e pool Edge (bordo interno)

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
<td><p><strong>Bordo piscina: IPv4</strong></p></td>
<td><p><strong>Bordo piscina: doppia pila</strong></p></td>
<td><p><strong>Pool Edge: IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Pool Front-end: IPv4</strong></p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Supporto per riunioni private con ID conferenza di riunione dinamici</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool Front-end: doppia pila</strong></p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Supporto per riunioni private con ID conferenza di riunione dinamici</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool Front-end: IPv6</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>Sì</p></td>
</tr>
</tbody>
</table>


\*Usare questa combinazione solo in un ambiente lab.

La tabella seguente è una matrice delle combinazioni supportate delle interfacce Edge interne ed esterne.

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a>Matrice pool Edge (bordo interno) e bordo piscina (bordo esterno)

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
<td><p><strong>Pool Edge (bordo esterno): IPv4</strong></p></td>
<td><p><strong>Pool Edge (bordo esterno): doppia pila</strong></p></td>
<td><p><strong>Pool Edge (bordo esterno): IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Pool Edge (bordo interno): IPv4</strong></p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Supporto per riunioni private con ID conferenza di riunione dinamici</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool di bordi (bordo interno): doppia pila</strong></p></td>
<td><p>No</p></td>
<td><p>Sì</p></td>
<td><p>Supporto per riunioni private con ID conferenza di riunione dinamici</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool Edge (bordo interno): IPv6</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>Sì</p></td>
</tr>
</tbody>
</table>


\*Usare questa combinazione solo in un ambiente lab.

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a>Supporto per VoIP aziendale avanzato per IPv6

Le distribuzioni che includono il controllo di ammissione alle chiamate (CAC), il 9-1-1 avanzato (E9-1-1) o l'esclusione multimediale devono essere configurate solo come IPv4 o come implementazione a doppio stack.

<div>


> [!NOTE]  
> In una distribuzione in pila doppia, anche se un client Lync si connette a un server Lync usando IPv6, Lync sarà utile per eseguire il mapping di un indirizzo IPv4 appropriato per supportare il servizio E9-1-1.



</div>

Il servizio informazioni sulla posizione con indirizzi IPv6 non è supportato.

La messaggistica unificata di Exchange non supporta IPv6. Per la messaggistica unificata di Exchange, assicurati che la risoluzione DNS non restituisca un indirizzo IPv6. L'uso di IPv6 può causare un errore quando le chiamate vengono inviate alla segreteria telefonica.

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a>Altre funzionalità di Lync Server 2013 supportate per IPv6

Oltre alle funzionalità e ai componenti menzionati in precedenza, Lync Server 2013 supporta IPv6 per le caratteristiche seguenti:

  - **Chat persistente**
    
    Si configura IPv6 per la chat persistente usando generatore di topologie. Per informazioni dettagliate sulla configurazione della chat persistente, vedere la documentazione relativa alla distribuzione di Persistent Chat Server.

  - **Report di qualità dei dati (QoE) e registrazione dei dettagli delle chiamate (CDR)**
    
    I report di monitoraggio includono l'indirizzo IP archiviato nel database del server di monitoraggio, indipendentemente dal tipo IPv4 o IPv6.

</div>

</div>

<span> </span>

</div>

</div>

</div>

