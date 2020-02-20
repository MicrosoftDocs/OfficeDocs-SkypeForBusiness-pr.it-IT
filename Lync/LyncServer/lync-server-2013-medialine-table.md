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
ms.openlocfilehash: edf0e216d90af0d32a0e700661a653a13028e01a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a>Tabella MediaLine in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-21_

Ogni record rappresenta una linea multimediale. (Una sessione audio di solito contiene una linea media audio. Una sessione audio e video (A/V) solitamente contiene una linea media audio e una linea multimediale video, anche se la sessione potrebbe contenere due linee multimediali video se viene utilizzato un dispositivo per conferenze o se viene utilizzata la visualizzazione raccolta.


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
<td><p>datetime</p></td>
<td><p>Principale</p></td>
<td><p>A cui viene fatto riferimento dalla <a href="lync-server-2013-session-table.md">tabella Session in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>A cui viene fatto riferimento dalla <a href="lync-server-2013-session-table.md">tabella Session in Lync Server 2013</a>.</p></td>
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
<td><p>Questa colonna è presente ma non utilizzata in Microsoft Lync Server 2013. Le informazioni sulla connettività utilizzata per una linea multimediale vengono acquisite nelle colonne CallerConnectivityICE e CalleeConnectivityICE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Informazioni sul processo di creazione di connettività interattive (ICE) descritto in flag di bit. Per informazioni dettagliate, vedere la sezione relativa alla <em>qualità delle specifiche del protocollo di monitoraggio del server</em>, disponibile per il download.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Uguale a CallerIceWarningFlags, ma da parte del destinatario della chiamata. Per informazioni dettagliate, vedere la sezione relativa alla <em>qualità delle specifiche del protocollo di monitoraggio del server</em>, disponibile per il download.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sicurezza</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Il profilo di sicurezza in uso. 0 per NESSUNA, 1 per SRTP, 2 per V1.</p></td>
</tr>
<tr class="even">
<td><p><strong>Trasporto</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>0 per UDP, 1 per TCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Indirizzo IP del chiamante. Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</p></td>
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
<td><p> Stranieri</p></td>
<td><p>La subnet del chiamante. Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>po'</p></td>
<td><p> </p></td>
<td><p>1 indica che il chiamante è all'interno della rete aziendale, 0 invece indica che è all'esterno della rete.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Indirizzo MAC del chiamante, a cui viene fatto riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Indirizzo IP del servizio A/V Edge di Lync Server utilizzato dal chiamante. Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Porta utilizzata nel servizio A/V Edge dal chiamante.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Dispositivo di acquisizione utilizzato dal chiamante. A cui viene fatto riferimento dalla <a href="lync-server-2013-device-table.md">tabella Device in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Dispositivo di rendering utilizzato dal chiamante. A cui viene fatto riferimento dalla <a href="lync-server-2013-device-table.md">tabella Device in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Driver per il dispositivo di acquisizione del chiamante, a cui viene fatto riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Driver per il dispositivo di rendering del chiamante, a cui viene fatto riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Stranieri</p></td>
<td><p>Indica il modo in cui il chiamante si è connesso alla rete. I valori vengono ottenuti dalla <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a>. I valori tipici sono 0 per una connessione cablata ' 1 per una connessione WiFi; e 3 per una connessione Ethernet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>BSSID del chiamante se viene utilizzata la tecnologia wireless. Riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Il collegamento del chiamante. 1 indica una rete privata virtuale (VPN), 0 indica una rete non VPN.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>decimale (18,0)</p></td>
<td></td>
<td><p>Velocità del collegamento di rete, in bps, per l'endpoint del chiamante.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Indirizzo IP del destinatario della chiamata. Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Porta utilizzata dal destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeSubnet</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Subnet del destinatario della chiamata. Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>po'</p></td>
<td><p> </p></td>
<td><p>1 indica che il destinatario della chiamata è all'interno della rete aziendale, 0 indica che il destinatario della chiamata è esterno alla rete.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Indirizzo MAC del destinatario della chiamata. A cui viene fatto riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Indirizzo IP del servizio A/V Edge utilizzato dal destinatario della chiamata. Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Porta utilizzata nel servizio A/V Edge dal destinatario della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>stranieri</p></td>
<td><p>Dispositivo di acquisizione utilizzato dal destinatario della chiamata. A cui viene fatto riferimento dalla <a href="lync-server-2013-device-table.md">tabella Device in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Dispositivo di rendering utilizzato dal destinatario della chiamata. A cui viene fatto riferimento dalla <a href="lync-server-2013-device-table.md">tabella Device in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Driver per il dispositivo di acquisizione del destinatario della chiamata. Riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>varchar (256)</p></td>
<td><p>Stranieri</p></td>
<td><p>Driver del dispositivo di rendering del destinatario della chiamata. Riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Stranieri</p></td>
<td><p>Indica il modo in cui il destinatario della chiamata è connesso alla rete. I valori vengono ottenuti dalla <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a>. I valori tipici sono 0 per una connessione cablata ' 1 per una connessione WiFi; e 3 per una connessione Ethernet.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>BSSID del destinatario della chiamata se viene utilizzato wireless. Riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>po'</p></td>
<td><p> </p></td>
<td><p>Il collegamento del destinatario della chiamata; 1 è la rete privata virtuale (VPN), 0 non è VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>decimale (18,0)</p></td>
<td><p> </p></td>
<td><p>Velocità del collegamento di rete, in bps, per l'endpoint del destinatario della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>decimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>Conversational MOS a banda stretta delle sessioni audio (basato su entrambi i flussi audio).</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Si tratta della larghezza di banda effettiva applicata al flusso del server di invio specificato, in cui sono disponibili diverse impostazioni di criteri (attiva, API, SDP, criteri e così via). Da non confondere con la larghezza di banda effettiva, perché può esistere una larghezza di banda effettiva inferiore basata sulla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che può essere utilizzata dal flusso di invio escludendo i limiti imposti dalla stima della larghezza di banda.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Origine del limite della larghezza di banda imposto. Descrive la posizione del limite della larghezza di banda ("server criteri", "Attiva server", "modalità" e così via). A cui viene fatto riferimento dalla <a href="lync-server-2013-appliedbandwidthsource-table.md">tabella AppliedBandwidthSource in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chiamante</strong></p></td>
<td><p>po'</p></td>
<td><p> </p></td>
<td><p>Indica se le metriche del chiamante sono state ricevute; 1 è sì, un valore null è no.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Destinatario chiamata</strong></p></td>
<td><p>po'</p></td>
<td><p> </p></td>
<td><p>Indica se le metriche provenienti dal destinatario della chiamata sono state ricevute; 1 è sì, un valore null è no.</p></td>
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
<td><p>Indica se il chiamante ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Indica se il chiamante ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Indirizzo IP riflessivo dell'utente che ha effettuato la chiamata. Nelle organizzazioni che utilizzano NAT (Network Address Translation), l'indirizzo IP riflessivo è l'indirizzo IP del server proxy.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Descrizione del dispositivo per il driver WiFi impiegato dall'utente che ha effettuato la chiamata.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Numero di versione del driver WiFi impiegato dall'utente che ha effettuato la chiamata.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Indirizzo IP riflessivo dell'utente che ha ricevuto la chiamata. Nelle organizzazioni che utilizzano NAT (Network Address Translation), l'indirizzo IP riflessivo è l'indirizzo IP del server proxy.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Descrizione del dispositivo per il driver WiFi impiegato dall'utente che ha ricevuto la chiamata.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Numero di versione del driver WiFi impiegato dall'utente che ha ricevuto la chiamata.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

