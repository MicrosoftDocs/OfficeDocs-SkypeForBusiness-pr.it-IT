---
title: 'Lync Server 2013: Tabella MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7488aa258fd30c2f9b519806dc84f9d897a08656
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a>Tabella MediaLine in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-21_

Ogni record rappresenta una linea media. (Una sessione audio in genere contiene una linea media audio. Una sessione audio e video (A/V) in genere contiene una linea media audio e una linea media video, anche se la sessione può contenere due linee multimediali video se viene usato un dispositivo per conferenze o se viene usata la visualizzazione raccolta.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Colonna</strong></th>
<th><strong>Tipo di dati</strong></th>
<th><strong>Chiave/indice</strong></th>
<th><strong>Dettagli</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>DateTime</p></td>
<td><p>Principale</p></td>
<td><p>A cui si fa riferimento dalla <a href="lync-server-2013-session-table.md">tabella di sessione in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>A cui si fa riferimento dalla <a href="lync-server-2013-session-table.md">tabella di sessione in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principale</p></td>
<td><p>0 è l'audio principale, 1 è il video principale e 2 è un video panoramico, 3 è la condivisione di applicazioni/desktop. Questa etichetta deve essere univoca all'interno di una singola sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectivityIce</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Questa colonna è presente ma non viene usata in Microsoft Lync Server 2013. Le informazioni sulla connettività usata per una linea media vengono acquisite nelle colonne CallerConnectivityICE e CalleeConnectivityICE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in flag di bit. Per informazioni dettagliate, vedere la sezione relativa alla <em>qualità della specifica di protocollo di monitoraggio delle esperienze</em>disponibile per il download.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Uguale a CallerIceWarningFlags, ma sul lato chiamato. Per informazioni dettagliate, vedere la sezione relativa alla <em>qualità della specifica di protocollo di monitoraggio delle esperienze</em>disponibile per il download.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sicurezza</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Profilo di sicurezza in uso. 0 è NONE, 1 è SRTP, 2 è V1.</p></td>
</tr>
<tr class="even">
<td><p><strong>Transport</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>0 è UDP, 1 è TCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Indirizzo IP del chiamante. Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Porta utilizzata dal chiamante.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerSubnet</strong></p></td>
<td><p>int</p></td>
<td><p> Esterna</p></td>
<td><p>Subnet del chiamante. Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>po'</p></td>
<td><p> </p></td>
<td><p>1 indica che il chiamante si trova all'interno della rete aziendale, 0 indica che il chiamante si trova all'esterno della rete.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Indirizzo MAC del chiamante, a cui si fa riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Indirizzo IP del servizio A/V Edge di Lync Server usato dal chiamante. Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Porta usata nel servizio A/V Edge dal chiamante.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Dispositivo di acquisizione usato dal chiamante. A cui si fa riferimento dalla <a href="lync-server-2013-device-table.md">tabella dei dispositivi in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Dispositivo di rendering usato dal chiamante. A cui si fa riferimento dalla <a href="lync-server-2013-device-table.md">tabella dei dispositivi in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Driver per il dispositivo di acquisizione del chiamante, a cui viene fatto riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Driver per il dispositivo di rendering del chiamante, a cui viene fatto riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Esterna</p></td>
<td><p>Indica il modo in cui il chiamante si connette alla rete. I valori vengono ottenuti dalla <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a>. I valori tipici sono 0 per una connessione cablata ' 1 per una connessione WiFi; e 3 per una connessione Ethernet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>BSSID del chiamante se viene usato wireless. A cui si fa riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Collegamento del chiamante. 1 è una rete privata virtuale (VPN), 0 non è VPN.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>decimale (18; 0)</p></td>
<td></td>
<td><p>Velocità di collegamento di rete, in bps, per l'endpoint del chiamante.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Indirizzo IP del destinatario della chiamata. Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Porta usata dal destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeSubnet</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Subnet del chiamato. Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>po'</p></td>
<td><p> </p></td>
<td><p>1 indica che il destinatario della chiamata si trova all'interno della rete aziendale, 0 indica che il destinatario della chiamata si trova all'esterno della rete.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Indirizzo MAC del destinatario. A cui si fa riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Indirizzo IP del servizio A/V Edge usato dal destinatario della chiamata. Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Porta usata nel servizio A/V Edge dal destinatario della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>esterna</p></td>
<td><p>Dispositivo di acquisizione usato dal destinatario della chiamata. A cui si fa riferimento dalla <a href="lync-server-2013-device-table.md">tabella dei dispositivi in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Dispositivo di rendering usato dal destinatario della chiamata. A cui si fa riferimento dalla <a href="lync-server-2013-device-table.md">tabella dei dispositivi in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Driver per il dispositivo di acquisizione del destinatario della chiamata. A cui si fa riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>varchar (256)</p></td>
<td><p>Esterna</p></td>
<td><p>Driver per il dispositivo di rendering del destinatario della chiamata. A cui si fa riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Esterna</p></td>
<td><p>Indica il modo in cui il chiamato si connette alla rete. I valori vengono ottenuti dalla <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a>. I valori tipici sono 0 per una connessione cablata ' 1 per una connessione WiFi; e 3 per una connessione Ethernet.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>BSSID di chiamata se viene usato wireless. A cui si fa riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>po'</p></td>
<td><p> </p></td>
<td><p>Collegamento del destinatario della chiamata; 1 è una rete privata virtuale (VPN), 0 non è VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>decimale (18; 0)</p></td>
<td><p> </p></td>
<td><p>Velocità di collegamento di rete, in bps, per l'endpoint del destinatario della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>decimale (3; 2)</p></td>
<td><p> </p></td>
<td><p>Stretta MOS colloquiale delle sessioni audio (in base a entrambi i flussi audio).</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Si tratta della larghezza di banda effettiva applicata al flusso del lato di invio assegnato in base a varie impostazioni dei criteri (TURN, API, SDP, Policy Server e così via). Questa operazione non deve essere confusa con la larghezza di banda effettiva, perché la larghezza di banda effettiva può essere inferiore in base alla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che il flusso di invio può bloccare i limiti imposti dalla stima della larghezza di banda.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Questa è l'origine del limite di larghezza di banda imposto. Descrive la posizione del limite di larghezza di banda ("Policy Server", "TURN server", "modality" e così via). A cui si fa riferimento dalla <a href="lync-server-2013-appliedbandwidthsource-table.md">tabella AppliedBandwidthSource in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chiamante</strong></p></td>
<td><p>po'</p></td>
<td><p> </p></td>
<td><p>Indica se sono state ricevute metriche dal chiamante; 1 è sì, un valore null è no.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Chiamato</strong></p></td>
<td><p>po'</p></td>
<td><p> </p></td>
<td><p>Indica se le metriche del destinatario della chiamata sono state ricevute; 1 è sì, un valore null è no.</p></td>
</tr>
<tr class="even">
<td><p><strong>MidCallReport</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Indica se il report è per una parte della sessione o per la sessione completa.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Indica se una chiamata è stata classificata come chiamata scadente (valore 1) o come buona chiamata (0).</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerConnectivityICE</strong></p></td>
<td><p>tinyInt</p></td>
<td></td>
<td><p>Indica se il chiamante è connesso alla rete usando il protocollo ICE (Internet Connectivity Establishment).</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Indica se il chiamante è connesso alla rete usando il protocollo ICE (Internet Connectivity Establishment).</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Indirizzo IP riflessivo dell'utente che ha effettuato la chiamata. Nelle organizzazioni che usano NAT (Network Address Translation), l'indirizzo IP riflessivo è l'indirizzo IP del server proxy.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Descrizione del dispositivo per il driver WiFi impiegato dall'utente che ha effettuato la chiamata.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Numero di versione per il driver WiFi impiegato dall'utente che ha effettuato la chiamata.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Indirizzo IP riflessivo dell'utente che ha ricevuto la chiamata. Nelle organizzazioni che usano NAT (Network Address Translation), l'indirizzo IP riflessivo è l'indirizzo IP del server proxy.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Descrizione del dispositivo per il driver WiFi impiegato dall'utente che ha ricevuto la chiamata.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Numero di versione per il driver WiFi impiegato dall'utente che ha ricevuto la chiamata.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

