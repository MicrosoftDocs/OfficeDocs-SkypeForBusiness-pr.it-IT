---
title: 'Lync Server 2013: supporto per il software client Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync client software support
ms:assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412781(v=OCS.15)
ms:contentKeyID: 48184994
ms.date: 02/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 913a484262d9e1b3a899aeda42c5f23049d8c73c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-client-software-support-in-lync-server-2013"></a>Supporto del software client Lync in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-02-25_

In questa sezione viene riepilogato il supporto software per Lync 2013 e il componente aggiuntivo per riunioni online per Lync 2013.

<div>


> [!NOTE]  
> Il componente aggiuntivo per riunioni online per Lync 2013, che supporta la gestione delle riunioni dall'interno del client di messaggistica e collaborazione di Outlook, viene installato automaticamente con Lync 2013.



</div>

### <a name="software-requirements-for-lync-2013-and-the-online-meeting-add-in-for-lync-2013"></a>Requisiti software per Lync 2013 e il componente aggiuntivo per riunioni online per Lync 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente del sistema</th>
<th>Requisito minimo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Sistema operativo Windows</p></td>
<td><p>Windows 10</p>
<p>Windows 8.1</p>
<p>Windows 8</p>
<p>Sistema operativo Windows 7</p>
<p>Windows Server 2008 R2 con Service Pack più recente</p>
<div>

> [!NOTE]  
> Lync 2013 e il componente aggiuntivo per riunioni online per Lync 2013 non sono supportati in Windows Vista o Windows XP (qualsiasi versione).


</div></td>
</tr>
<tr class="even">
<td><p>Installazione e aggiornamenti</p></td>
<td><p>Diritti e autorizzazioni di amministratore</p></td>
</tr>
<tr class="odd">
<td><p>Browser</p></td>
<td><p>Internet Explorer 11 Internet browser</p>
<p>Internet Explorer 10 (browser Internet)</p>
<p>Internet Explorer 9 (browser Internet)</p>
<p>Internet Explorer 8 browser Internet</p>
<p>Internet Explorer 7 Internet browser</p>
<p>Mozilla Firefox</p>
<div>

> [!NOTE]  
> Se si utilizza Lync con Microsoft Exchange Online e l'organizzazione ha distribuito un proxy HTTP di autenticazione, è necessario Internet Explorer 9 o Internet Explorer 8.


</div></td>
</tr>
<tr class="even">
<td><p>Integrazione di Microsoft Office</p></td>
<td><p>Per il set completo di funzionalità di integrazione:</p>
<ul>
<li><p>Client di messaggistica e collaborazione di Outlook 2013</p></li>
<li><p>Client di messaggistica e collaborazione di Outlook 2010</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Integrazione di Microsoft Exchange</p></td>
<td><p>Per il set completo di funzionalità di integrazione:</p>
<ul>
<li><p>Microsoft Exchange Server 2013</p></li>
<li><p>Microsoft Exchange Server 2010</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>

## <a name="macintosh-operating-systems"></a>Sistemi operativi Macintosh

Lync 2013 è disponibile solo per Windows. Tuttavia, Lync Server 2013 supporta i client seguenti nei computer che eseguono Mac OS 10.5.8 o più recenti sistemi operativi di Service Pack o di rilascio (basati su Intel) (il sistema operativo Mac OS 10,9 non è attualmente supportato). Per informazioni dettagliate sulle funzionalità supportate, vedere [tabelle di confronto dei client per Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md).

  - Microsoft Lync per Mac 2011 (vedere la guida alla distribuzione di [http://go.microsoft.com/fwlink/p/?LinkId=268786](http://go.microsoft.com/fwlink/p/?linkid=268786)Lync per Mac 2011)

  - Microsoft Communicator per Mac 2011 (vedere la guida alla [http://go.microsoft.com/fwlink/p/?LinkId=268787](http://go.microsoft.com/fwlink/p/?linkid=268787)distribuzione di Communicator per Mac 2011)

</div>

<div>

## <a name="lync-web-app-browsers"></a>Browser di Lync Web App

Lync Web App supporta specifiche combinazioni di sistemi operativi e browser. Per informazioni dettagliate, vedere [Lync Web App Supported Platforms for Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md) nella documentazione relativa alla pianificazione.

</div>

<div>

## <a name="microsoft-office-supportability"></a>Supporto di Microsoft Office

I client di Lync Server 2013 supportano l'integrazione con diverse versioni di Microsoft Office, come riepilogato in questa sezione.

  - Le funzionalità di integrazione di Lync 2013 sono supportate in Outlook 2013 e Microsoft Outlook 2010.

  - Le funzionalità di integrazione di Lync 2013 sono supportate in Microsoft Exchange Server 2013 e Microsoft Exchange Server 2010.

  - Il componente aggiuntivo per riunioni online per Lync 2013 è supportato con Office 2013 e Microsoft Office 2010.

</div>

<div>

## <a name="using-mandatory-profiles"></a>Utilizzo dei profili obbligatori

Se gli utenti stanno progettando di utilizzare le funzionalità di conferenza di Lync 2013, non devono utilizzare profili obbligatori di servizi di dominio Active Directory per accedere al client Lync 2013. Poiché i profili obbligatori sono profili utente di sola lettura, le chiavi dell'infrastruttura a chiave pubblica (PKI) necessarie per Lync 2013 Conferencing non possono essere salvate nel profilo. Per informazioni dettagliate, vedere l'articolo 2552221 della Microsoft Knowledge Base "la funzionalità di conferenza di Lync 2010 ha esito negativo quando l'utente ha eseguito l' [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2552221](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2552221)accesso utilizzando un profilo utente obbligatorio" all'indirizzo.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Supporto per l'hardware client di Lync in Lync Server 2013](lync-server-2013-lync-client-hardware-support.md)  
[Requisiti video di Lync client per Lync Server 2013](lync-server-2013-lync-client-video-requirements.md)  
[Client supportati dalle distribuzioni precedenti in Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

