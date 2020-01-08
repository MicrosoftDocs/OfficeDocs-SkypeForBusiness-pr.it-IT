---
title: 'Lync Server 2013: Visualizzazione MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d930f3beeeddb5c5582f41c44f1c68ff7f21f18d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a>Visualizzazione MediaLine in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-03_

La Visualizzazione MediaLine archivia le informazioni su ogni riga multimediale nel database. Una sessione audio in genere contiene una linea media audio. Una sessione audio e video (A/V) in genere contiene una linea media audio e una linea media video; Tuttavia, la sessione può contenere due linee multimediali video se viene usato un dispositivo per i servizi di conferenza o se viene usata la visualizzazione raccolta. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonna</th>
<th>Tipo di dati</th>
<th>Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ConferenceDateTime</p></td>
<td><p>DateTime</p></td>
<td><p>A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p>A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamante. Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamato. Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.</p></td>
</tr>
<tr class="even">
<td><p>Sicurezza</p></td>
<td><p>tinyint</p></td>
<td><p>Profilo di sicurezza in uso. 0 è NONE, 1 è SRTP, 2 è V1.</p></td>
</tr>
<tr class="odd">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo di trasporto. 0 è UDP, 1 è TCP.</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del chiamante. Può essere un indirizzo IPv4 o IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Porta utilizzata dal chiamante.</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>po'</p></td>
<td><p>Indica se il chiamante si trova all'interno della rete dell'organizzazione. 1 indica che il chiamante si trova all'interno della rete aziendale. 0 indica che il chiamante si trova all'esterno della rete.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMacAddress</p></td>
<td><p>varchar (256)</p></td>
<td><p>Indirizzo MAC dell'interfaccia di rete usata dal chiamante.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del servizio A/V Edge usato dal chiamante. Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Porta usata nel servizio A/V Edge usato dal chiamante.</p></td>
</tr>
<tr class="even">
<td><p>CallerReflexiveIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del chiamante segnalato dal servizio A/V Edge. Questo indirizzo può essere diverso da quello di CallerIPAddr se il client si trova dietro a un NAT, ad esempio.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del dispositivo di acquisizione del chiamante.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del dispositivo di rendering del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del driver del dispositivo di acquisizione del chiamante.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del driver del dispositivo di rendering del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CallerWifiDriverDeviceDesc</p></td>
<td><p>varchar (256</p></td>
<td><p>Descrizione del driver WiFi del chiamante.</p></td>
</tr>
<tr class="even">
<td><p>CallerWifiDriverVersion</p></td>
<td><p>varchar (256)</p></td>
<td><p>Versione del driver WiFi del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar (256)</p></td>
<td><p>Dettagli della connessione di rete del chiamante. Per altre informazioni, vedere la <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerBssid</p></td>
<td><p>varchar (256)</p></td>
<td><p>ID set di servizi di base usato dalla connessione WiFi dei chiamanti.</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>po'</p></td>
<td><p>Indica se il chiamante è connesso tramite una rete privata virtuale. 1 è una rete privata virtuale (VPN), 0 non è VPN.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del destinatario. Può essere un indirizzo IPv4 o IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Porta utilizzata dal chiamato.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>po'</p></td>
<td><p>Indica se il chiamato si trova all'interno della rete aziendale. 1 significa che il chiamato si trova all'interno della rete aziendale, 0 indica che il chiamato è all'esterno della rete.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeMacAddress</p></td>
<td><p>varchar (256)</p></td>
<td><p>Indirizzo MAC dell'interfaccia di rete usata dal chiamato.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del servizio A/V Edge usato dal destinatario. Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Porta usata nel servizio A/V Edge usato dal chiamato.</p></td>
</tr>
<tr class="even">
<td><p>CalleeReflexiveIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del destinatario segnalato dal servizio A/V Edge. Questo indirizzo può essere diverso da quello di CalleeIPAddr se il client si trova dietro a un NAT, ad esempio.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>var (50)</p></td>
<td><p>Nome del dispositivo di acquisizione del chiamato.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del dispositivo di rendering del destinatario.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del driver del dispositivo di acquisizione del destinatario.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del driver del dispositivo di rendering del destinatario.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeWifiDriverDeviceDesc</p></td>
<td><p>varchar (256)</p></td>
<td><p>Descrizione del driver WiFi del chiamato.</p></td>
</tr>
<tr class="even">
<td><p>CalleeWifiDriverVersion</p></td>
<td><p>varchar (256</p></td>
<td><p>Versione del driver WiFi del chiamato.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar (256)</p></td>
<td><p>Dettagli della connessione di rete del chiamato. Per altre informazioni, vedere la <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeBssid</p></td>
<td><p>varchar (256)</p></td>
<td><p>Identificatore del set di servizi di base usato dalla connessione Wi-Fi del chiamato.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>po'</p></td>
<td><p>Indica se il chiamato è connesso tramite una rete privata virtuale. 1 è una rete privata virtuale (VPN), 0 non è VPN.</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>decimale (3; 2)</p></td>
<td><p>Stretta MOS colloquiale delle sessioni audio (in base a entrambi i flussi audio).</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Questa è la larghezza di banda effettiva applicata al flusso del lato di invio assegnato in base a varie impostazioni dei criteri (TURN, API, SDP, Policy Server e così via). Questa operazione non deve essere confusa con la larghezza di banda effettiva, in quanto la larghezza di banda effettiva può essere inferiore in base alla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che il flusso di invio può bloccare i limiti imposti dalla stima della larghezza di banda.</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthSource</p></td>
<td><p>varchar (256)</p></td>
<td><p>Origine del limite di larghezza di banda imposto. Descrive la posizione in cui proviene il limite di larghezza di banda, ad esempio "Policy Server", "TURN server" o "modality".</p></td>
</tr>
<tr class="odd">
<td><p>Chiamante</p></td>
<td><p>po'</p></td>
<td><p>Indica se sono state ricevute metriche dal chiamante; 1 è sì, 0 è no.</p></td>
</tr>
<tr class="even">
<td><p>Chiamato</p></td>
<td><p>po'</p></td>
<td><p>Indica se le metriche del destinatario della chiamata sono state ricevute; 1 è sì, 0 è no.</p></td>
</tr>
<tr class="odd">
<td><p>MidCallReport</p></td>
<td><p>po'</p></td>
<td><p>Indica se il report è per una parte della chiamata o per la chiamata completa.</p></td>
</tr>
<tr class="even">
<td><p>ClassifiedPoorCall</p></td>
<td><p>po'</p></td>
<td><p>Indica se una chiamata è stata classificata come chiamata scadente (1) o come buona chiamata (0).</p></td>
</tr>
<tr class="odd">
<td><p>CallerConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>Indica se il chiamante è connesso alla rete usando il protocollo ICE (Internet Connectivity Establishment).</p></td>
</tr>
<tr class="even">
<td><p>CalleeConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>Indica se l'utente ha chiamato connesso alla rete usando il protocollo ICE (Internet Connectivity Establishment).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

