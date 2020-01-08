---
title: 'Lync Server 2013: configurazioni ibride supportate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported hybrid configurations
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945633(v=OCS.15)
ms:contentKeyID: 51541482
ms.date: 05/10/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 142b86720e64fdfd071bc5cacb21e4891e3e7758
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-lync-server-2013-hybrid-configurations"></a>Configurazioni ibride di Lync Server 2013 supportate

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-05-10_

È possibile configurare le distribuzioni di Lync Server 2013 per l'integrazione con Microsoft Exchange Server 2010 e Microsoft Exchange Server 2013 e SharePoint Server, sia in locale che online. Le caratteristiche elencate nella tabella seguente sono supportate con tutti i client, se non diversamente specificato. Per altre informazioni sul supporto client, vedere [tabelle di confronto tra client per Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) e tabelle di confronto dei client di Skype for business online presso [i client di Skype for business online](http://go.microsoft.com/fwlink/p/?linkid=281902).

<div>

## <a name="integration-with-exchange-server"></a>Integrazione con Exchange Server

La tabella seguente elenca le caratteristiche supportate in una distribuzione ibrida quando è integrata con Microsoft Exchange Server.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Exchange locale</th>
<th>Exchange Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 locale</strong></p></td>
<td><ul>
<li><p>Messaggistica istantanea/presenza in Outlook</p>
<p>Per altre informazioni, vedere <a href="lync-server-2013-im-and-presence.md">messaggistica istantanea e presenza in Lync Server 2013</a></p></li>
<li><p>Pianificare e partecipare a riunioni online tramite Outlook</p>
<p>Per altre informazioni, vedere <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">integrazione di Microsoft Lync server 2013 e Microsoft Exchange server 2013</a></p></li>
<li><p>Messaggistica istantanea/presenza in Outlook Web App</p>
<p>Per altre informazioni, vedere <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">configurazione di Microsoft Lync Server 2013 in un ambiente tra più locali</a></p></li>
<li><p>Pianificare e partecipare a riunioni online tramite Outlook Web App</p></li>
<li><p>Messaggistica istantanea/presenza nei client mobili</p></li>
<li><p>Partecipare a riunioni online nei client mobili</p>
<p>Per altre informazioni, vedere <a href="lync-server-2013-deploying-mobility.md">distribuzione della mobilità in Lync Server 2013</a></p></li>
<li><p>Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook</p></li>
<li><p>Elenco contatti (tramite l'archivio contatti unificato)</p>
<p>Per altre informazioni, vedere <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">configurazione di Microsoft Lync Server 2013 per l'uso dell'archivio contatti unificato</a></p>
<div>

> [!NOTE]  
> Richiede Exchange 2013.<BR>È necessario un client desktop Lync 2013.


</div></li>
<li><p>Foto di contatto ad alta risoluzione in Lync 2013 client e Lync Web App.</p>
<p>Per altre informazioni, vedere <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">configurazione dell'uso di foto ad alta risoluzione in Microsoft Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Richiede Exchange 2013.


</div></li>
<li><p>Delega riunione</p>
<p>Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta oppure vengono ospitati in locale.</p></li>
<li><p>La cronologia delle conversazioni perse e i registri delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente</p></li>
<li><p>Archiviazione del contenuto (messaggistica istantanea e riunione) in Exchange</p>
<p>Per altre informazioni, vedere <a href="lync-server-2013-deployment-checklist-for-archiving.md">elenco di controllo della distribuzione per l'archiviazione in Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Richiede Exchange 2013.


</div></li>
<li><p>Cercare contenuto archiviato</p>
<div>

> [!NOTE]  
> Richiede Exchange 2013.


</div></li>
<li><p>Segreteria telefonica</p>
<p>Per altre informazioni, vedere la pagina <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">relativa alla distribuzione della messaggistica unificata di Exchange locale per consentire la segreteria telefonica di Lync Server 2013</a></p></li>
</ul></td>
<td><ul>
<li><p>Messaggistica istantanea/presenza in Outlook</p>
<p>Per altre informazioni, vedere <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">configurazione dell'integrazione di Lync Server 2013 locale con Exchange Online</a></p></li>
<li><p>Pianificare e partecipare a una riunione online tramite Outlook</p></li>
<li><p>Messaggistica istantanea/presenza in OWA</p>
<p>Per altre informazioni, vedere <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">configurazione dell'integrazione di Lync Server 2013 locale con Exchange Online</a></p></li>
<li><p>Pianificare e partecipare a una riunione online da Outlook Web App</p>
<p>Per altre informazioni, vedere <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">configurazione dell'integrazione di Lync Server 2013 locale con Exchange Online</a></p></li>
<li><p>Messaggistica istantanea/presenza nei client mobili</p></li>
<li><p>Partecipare a una riunione online nei client mobili</p></li>
<li><p>Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook</p></li>
<li><p>Elenco contatti (tramite archivio contatti unificato). Per altre informazioni, vedere <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">configurazione di Microsoft Lync Server 2013 per l'uso dell'archivio contatti unificato</a></p>
<div>

> [!NOTE]  
> Solo Lync Server 2013. È necessario un client desktop Lync 2013.


</div></li>
<li><p>Foto di contatto ad alta risoluzione in Lync 2013 client e Lync Web App.</p>
<p>Per altre informazioni, vedere <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">configurazione dell'uso di foto ad alta risoluzione in Microsoft Lync Server 2013</a>.</p></li>
<li><p>Delega riunione</p>
<p>Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta oppure vengono ospitati in locale.</p></li>
<li><p>La cronologia delle conversazioni perse e i registri delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente</p></li>
<li><p>Archiviazione del contenuto (messaggistica istantanea e riunione) in Exchange.</p>
<p>Per altre informazioni, vedere <a href="lync-server-2013-deployment-checklist-for-archiving.md">elenco di controllo della distribuzione per l'archiviazione in Lync Server 2013</a></p></li>
<li><p>Cercare contenuto archiviato. Per altre informazioni, vedere <a href="http://go.microsoft.com/fwlink/p/?linkid=285448">configurare Exchange per SharePoint eDiscovery Center</a></p></li>
<li><p>Segreteria telefonica. Per altre informazioni, vedere fornitura della segreteria <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">telefonica di Lync Server 2013 agli utenti nella messaggistica unificata di Exchange ospitata</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Messaggistica istantanea e presenza in Outlook</p></li>
<li><p>Pianificare e partecipare a riunioni online tramite Outlook</p></li>
<li><p>Messaggistica istantanea/presenza nei client mobili</p></li>
<li><p>La cronologia delle conversazioni perse e i registri delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente</p></li>
<li><p>Foto di contatto ad alta risoluzione nel client Lync 2013.</p>
<div>

> [!NOTE]  
> Richiede Microsoft Exchange Server 2013. Questa operazione non è supportata in Lync Web App quando gli utenti vengono ospitati in Skype for business online.


</div></li>
<li><p>Partecipare a una riunione online nei client mobili</p></li>
<li><p>Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook</p></li>
<li><p>Delega riunione</p>
<p>Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta oppure vengono ospitati in locale.</p></li>
</ul></td>
<td><ul>
<li><p>Messaggistica istantanea/presenza in Outlook</p></li>
<li><p>Pianificare e partecipare a riunioni online tramite Outlook</p></li>
<li><p>Messaggistica istantanea/presenza in Outlook Web App</p></li>
<li><p>Pianificare e partecipare a una riunione online da Outlook Web App</p></li>
<li><p>Messaggistica istantanea/presenza nei client mobili</p></li>
<li><p>Partecipare a una riunione online nei client mobili</p></li>
<li><p>Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook</p></li>
<li><p>La cronologia delle conversazioni perse e i registri delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente</p></li>
<li><p>Elenco contatti (tramite l'archivio contatti unificato)</p>
<div>

> [!NOTE]  
> Client di Lync Server 2013 richiesto


</div></li>
<li><p>Foto di contatto ad alta risoluzione in Lync 2013 client e Lync Web App</p></li>
<li><p>Delega riunione</p>
<p>Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta oppure vengono ospitati in locale.</p></li>
<li><p>Archiviazione del contenuto (messaggistica istantanea e riunione) in Exchange</p></li>
<li><p>Cercare contenuto archiviato</p></li>
<li><p>Segreteria telefonica</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a>Integrazione con SharePoint

La tabella seguente elenca le caratteristiche supportate in una distribuzione ibrida di Lync Server 2013 quando è integrata in SharePoint.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>SharePoint locale</th>
<th>SharePoint Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 locale</strong></p></td>
<td><ul>
<li><p>Ricerca di competenze</p></li>
<li><p>Presenza in SharePoint</p></li>
</ul></td>
<td><ul>
<li><p>Presenza in SharePoint</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Presenza in SharePoint</p></li>
</ul></td>
<td><ul>
<li><p>Presenza in SharePoint</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

