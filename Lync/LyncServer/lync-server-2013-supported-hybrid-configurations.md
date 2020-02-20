---
title: 'Lync Server 2013: configurazioni ibride supportate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported hybrid configurations
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945633(v=OCS.15)
ms:contentKeyID: 51541482
ms.date: 05/10/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c757fc19bd82fbf1ae3096bb4a8ac8982f9035b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-lync-server-2013-hybrid-configurations"></a>Configurazioni ibride di Lync Server 2013 supportate

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-05-10_

È possibile configurare le distribuzioni di Lync Server 2013 per l'integrazione con Microsoft Exchange Server 2010 e Microsoft Exchange Server 2013 e SharePoint Server, sia in locale che online. Le funzionalità elencate nella tabella seguente sono supportate con tutti i client, se non diversamente specificato. Per ulteriori informazioni sul supporto client, vedere tabelle di confronto [dei client per Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) e tabelle di confronto dei client di Skype for business online nei [client per Skype for business online](https://go.microsoft.com/fwlink/p/?linkid=281902).

<div>

## <a name="integration-with-exchange-server"></a>Integrazione con Exchange Server

Nella tabella seguente sono elencate le funzionalità supportate in una distribuzione ibrida se sono integrate con Microsoft Exchange Server.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Exchange in locale</th>
<th>Exchange Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 locale</strong></p></td>
<td><ul>
<li><p>Messaggistica istantanea/presenza in Outlook</p>
<p>Per ulteriori informazioni, vedere <a href="lync-server-2013-im-and-presence.md">messaggistica istantanea e presenza in Lync Server 2013</a></p></li>
<li><p>Pianificare e partecipare a riunioni online tramite Outlook</p>
<p>Per ulteriori informazioni, vedere <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">integrazione di Microsoft Lync server 2013 e Microsoft Exchange server 2013</a></p></li>
<li><p>Messaggistica istantanea/presenza in Outlook Web App</p>
<p>Per ulteriori informazioni, vedere <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">Configuring Microsoft Lync Server 2013 in a cross-premise Environment</a></p></li>
<li><p>Pianificare e partecipare a riunioni online tramite Outlook Web App</p></li>
<li><p>Messaggistica istantanea/presenza nei client mobili</p></li>
<li><p>Partecipare a riunioni online nei client mobili</p>
<p>Per ulteriori informazioni, vedere <a href="lync-server-2013-deploying-mobility.md">Deploying Mobility in Lync Server 2013</a></p></li>
<li><p>Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook</p></li>
<li><p>Elenco contatti (tramite archivio contatti unificato)</p>
<p>Per ulteriori informazioni, vedere <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">configurazione di Microsoft Lync Server 2013 per l'utilizzo dell'archivio contatti unificato</a></p>
<div>

> [!NOTE]  
> Richiede Exchange 2013.<BR>È necessario un client desktop Lync 2013.


</div></li>
<li><p>Foto contatto ad alta risoluzione in Lync 2013 client e Lync Web App.</p>
<p>Per ulteriori informazioni, vedere <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">configurazione dell'utilizzo di foto ad alta risoluzione in Microsoft Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Richiede Exchange 2013.


</div></li>
<li><p>Delega riunione</p>
<p>Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta oppure entrambi sono ospitati in locale.</p></li>
<li><p>La cronologia delle conversazioni perse e i log delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente</p></li>
<li><p>Contenuto di archiviazione (messaggistica istantanea e riunione) in Exchange</p>
<p>Per ulteriori informazioni, vedere <a href="lync-server-2013-deployment-checklist-for-archiving.md">elenco di controllo di distribuzione per l'archiviazione in Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Richiede Exchange 2013.


</div></li>
<li><p>Ricerca contenuto archiviato</p>
<div>

> [!NOTE]  
> Richiede Exchange 2013.


</div></li>
<li><p>Posta vocale</p>
<p>Per ulteriori informazioni, vedere <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">Deploying on-premises Exchange Messaggistica unificata per fornire Lync Server 2013</a> segreteria telefonica</p></li>
</ul></td>
<td><ul>
<li><p>Messaggistica istantanea/presenza in Outlook</p>
<p>Per ulteriori informazioni, vedere <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 Integration with Exchange Online</a></p></li>
<li><p>Pianificare e partecipare a una riunione online tramite Outlook</p></li>
<li><p>Messaggistica istantanea/presenza in OWA</p>
<p>Per ulteriori informazioni, vedere <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 Integration with Exchange Online</a></p></li>
<li><p>Pianificazione e partecipazione alla riunione online da Outlook Web App</p>
<p>Per ulteriori informazioni, vedere <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 Integration with Exchange Online</a></p></li>
<li><p>Messaggistica istantanea/presenza nei client mobili</p></li>
<li><p>Partecipare a una riunione online nei client mobili</p></li>
<li><p>Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook</p></li>
<li><p>Elenco contatti (tramite archivio contatti unificato). Per ulteriori informazioni, vedere <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">configurazione di Microsoft Lync Server 2013 per l'utilizzo dell'archivio contatti unificato</a></p>
<div>

> [!NOTE]  
> Solo Lync Server 2013. È necessario un client desktop Lync 2013.


</div></li>
<li><p>Foto contatto ad alta risoluzione in Lync 2013 client e Lync Web App.</p>
<p>Per ulteriori informazioni, vedere <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">configurazione dell'utilizzo di foto ad alta risoluzione in Microsoft Lync Server 2013</a>.</p></li>
<li><p>Delega riunione</p>
<p>Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta oppure entrambi sono ospitati in locale.</p></li>
<li><p>La cronologia delle conversazioni perse e i log delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente</p></li>
<li><p>Contenuto di archiviazione (messaggistica istantanea e riunione) in Exchange.</p>
<p>Per ulteriori informazioni, vedere <a href="lync-server-2013-deployment-checklist-for-archiving.md">elenco di controllo di distribuzione per l'archiviazione in Lync Server 2013</a></p></li>
<li><p>Ricerca contenuto archiviato. Per ulteriori informazioni, vedere at <a href="https://go.microsoft.com/fwlink/p/?linkid=285448">Configure Exchange for SharePoint eDiscovery Center</a></p></li>
<li><p>Segreteria telefonica. Per ulteriori informazioni, vedere <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">providing Lync Server 2013 Users Voice mail sulla messaggistica unificata di Exchange ospitata</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Messaggistica istantanea e presenza in Outlook</p></li>
<li><p>Pianificare e partecipare a riunioni online tramite Outlook</p></li>
<li><p>Messaggistica istantanea/presenza nei client mobili</p></li>
<li><p>La cronologia delle conversazioni perse e i log delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente</p></li>
<li><p>Foto contatto ad alta risoluzione nel client Lync 2013.</p>
<div>

> [!NOTE]  
> Richiede Microsoft Exchange Server 2013. Questo non è supportato in Lync Web App quando gli utenti sono ospitati in Skype for business online.


</div></li>
<li><p>Partecipare a una riunione online nei client mobili</p></li>
<li><p>Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook</p></li>
<li><p>Delega riunione</p>
<p>Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta oppure entrambi sono ospitati in locale.</p></li>
</ul></td>
<td><ul>
<li><p>Messaggistica istantanea/presenza in Outlook</p></li>
<li><p>Pianificare e partecipare a riunioni online tramite Outlook</p></li>
<li><p>Messaggistica istantanea/presenza in Outlook Web App</p></li>
<li><p>Pianificazione e partecipazione alla riunione online da Outlook Web App</p></li>
<li><p>Messaggistica istantanea/presenza nei client mobili</p></li>
<li><p>Partecipare a una riunione online nei client mobili</p></li>
<li><p>Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook</p></li>
<li><p>La cronologia delle conversazioni perse e i log delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente</p></li>
<li><p>Elenco contatti (tramite archivio contatti unificato)</p>
<div>

> [!NOTE]  
> Client Lync Server 2013 necessario


</div></li>
<li><p>Foto di contatto ad alta risoluzione in Lync 2013 client e Lync Web App</p></li>
<li><p>Delega riunione</p>
<p>Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta oppure entrambi sono ospitati in locale.</p></li>
<li><p>Contenuto di archiviazione (messaggistica istantanea e riunione) in Exchange</p></li>
<li><p>Ricerca contenuto archiviato</p></li>
<li><p>Segreteria telefonica</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a>Integrazione con SharePoint

Nella tabella seguente sono elencate le funzionalità supportate in una distribuzione ibrida di Lync Server 2013 quando è integrata con SharePoint.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>SharePoint in locale</th>
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

