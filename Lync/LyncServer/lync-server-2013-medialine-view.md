---
title: 'Lync Server 2013: Visualizzazione MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c6e5fd3c1afe27bc1baa8790527ee239bdba990
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a>Visualizzazione MediaLine in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-03_

Nella visualizzazione MediaLine vengono archiviate informazioni su ogni linea multimediale nel database. Una sessione audio in genere contiene una linea multimediale audio. Una sessione audio e video (A/V) in genere contiene una linea multimediale audio e una video; la sessione, tuttavia, contiene due linee multimediali video se si utilizza un dispositivo per conferenze o la visualizzazione Raccolta. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.


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
<td><p>datetime</p></td>
<td><p>A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p>A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il chiamante. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il destinatario della chiamata. Per informazioni dettagliate, vedere la Specifica del protocollo Quality of Experience Monitoring Server.</p></td>
</tr>
<tr class="even">
<td><p>Sicurezza</p></td>
<td><p>tinyint</p></td>
<td><p>Profilo di sicurezza in uso. 0 per NESSUNA, 1 per SRTP, 2 per V1.</p></td>
</tr>
<tr class="odd">
<td><p>Trasporto</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo di trasporto. 0 per UDP, 1 per TCP.</p></td>
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
<td><p>Indica se il chiamante si trova nella rete dell'organizzazione. 1 significa che il chiamante è all'interno della rete dell'organizzazione. 0 significa che il chiamante è all'esterno della rete dell'organizzazione.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMacAddress</p></td>
<td><p>varchar (256)</p></td>
<td><p>Indirizzo MAC dell'interfaccia di rete utilizzata dal chiamante.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del servizio A/V Edge utilizzato dal chiamante. Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Porta utilizzata nel servizio A/V Edge utilizzato dal chiamante.</p></td>
</tr>
<tr class="even">
<td><p>CallerReflexiveIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del chiamante segnalato dal servizio A/V Edge. Questo indirizzo può essere diverso rispetto al CallerIPAddr se il client si trova dietro un sistema NAT, ad esempio.</p></td>
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
<td><p>Dettagli della connessione di rete del chiamante. Per ulteriori informazioni, vedere la <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerBssid</p></td>
<td><p>varchar (256)</p></td>
<td><p>BSSI (Basic Service Set Identifier) utilizzato dalla connessione WiFi del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>po'</p></td>
<td><p>Indica se il chiamante ha eseguito la connessione su una rete privata virtuale. 1 indica una VPN, 0 indica una rete non VPN.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del destinatario della chiamata. Può essere un indirizzo IPv4 o IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Porta utilizzata dal destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>po'</p></td>
<td><p>Indica se il destinatario della chiamata si trova all'interno della rete aziendale. 1 indica che il destinatario della chiamata è all'interno della rete aziendale, mentre 0 indica che è all'esterno della rete.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeMacAddress</p></td>
<td><p>varchar (256)</p></td>
<td><p>Indirizzo MAC dell'interfaccia di rete utilizzata dal destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del servizio A/V Edge utilizzato dal destinatario della chiamata. Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Porta utilizzata nel servizio A/V Edge utilizzato dal destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CalleeReflexiveIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del destinatario della chiamata segnalato dal servizio A/V Edge. Questo indirizzo può essere diverso rispetto al CalleeIPAddr se il client si trova dietro un sistema NAT, ad esempio.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>var (50)</p></td>
<td><p>Nome del dispositivo di acquisizione del destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del dispositivo di rendering del destinatario della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del driver del dispositivo di acquisizione del destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del driver del dispositivo di rendering del destinatario della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeWifiDriverDeviceDesc</p></td>
<td><p>varchar (256)</p></td>
<td><p>Descrizione del driver WiFi del destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CalleeWifiDriverVersion</p></td>
<td><p>varchar (256</p></td>
<td><p>Versione del driver WiFi del destinatario della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar (256)</p></td>
<td><p>Dettagli della connessione di rete del destinatario della chiamata. Per ulteriori informazioni, vedere la <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeBssid</p></td>
<td><p>varchar (256)</p></td>
<td><p>BSSI (Basic Service Set Identifier) utilizzato dalla connessione WiFi del destinatario della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>po'</p></td>
<td><p>Indica se il destinatario della chiamata ha eseguito la connessione su una rete privata virtuale. 1 indica una VPN, 0 indica una rete non VPN.</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>decimale (3, 2)</p></td>
<td><p>Conversational MOS a banda stretta delle sessioni audio (basato su entrambi i flussi audio).</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Questa è la larghezza di banda effettivamente applicata al flusso sul lato dell'invio secondo diverse impostazioni di criteri (TURN, API, SDP, server dei criteri e così via). Da non confondere con la larghezza di banda effettiva, perché può esistere una larghezza di banda effettiva inferiore basata sulla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che può essere utilizzata dal flusso di invio escludendo i limiti imposti dalla stima della larghezza di banda.</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthSource</p></td>
<td><p>varchar (256)</p></td>
<td><p>Origine del limite della larghezza di banda imposto. Descrive l'origine del limite della larghezza di banda, ad esempio "Policy Server", "TURN Server" o "Modality".</p></td>
</tr>
<tr class="odd">
<td><p>Chiamante</p></td>
<td><p>po'</p></td>
<td><p>Indica se è stata ricevuta la metrica del chiamante. 1 indica sì e 0 indica no.</p></td>
</tr>
<tr class="even">
<td><p>Destinatario chiamata</p></td>
<td><p>po'</p></td>
<td><p>Indica se è stata ricevuta la metrica del destinatario della chiamata. 1 indica sì e 0 indica no.</p></td>
</tr>
<tr class="odd">
<td><p>MidCallReport</p></td>
<td><p>po'</p></td>
<td><p>Indica se il report riguarda una parte della chiamata o l'intera chiamata.</p></td>
</tr>
<tr class="even">
<td><p>ClassifiedPoorCall</p></td>
<td><p>po'</p></td>
<td><p>Indica se una chiamata è stata classificata come di livello insufficiente (1) o buono (0).</p></td>
</tr>
<tr class="odd">
<td><p>CallerConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>Indica se il chiamante ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).</p></td>
</tr>
<tr class="even">
<td><p>CalleeConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>Indica se il destinatario della chiamata ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

