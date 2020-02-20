---
title: 'Lync Server 2013: client supportati dalle distribuzioni precedenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported clients from previous deployments
ms:assetid: 69d427f8-57a5-4244-b2ed-f2eb7600285e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398499(v=OCS.15)
ms:contentKeyID: 48184390
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cef56a80ed02afd5942c117e08bb058e178aebe
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-clients-from-previous-deployments-in-lync-server-2013"></a>Client supportati dalle distribuzioni precedenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-12-14_

In uno scenario di coesistenza, i client di Lync Server 2013 possono interagire con client provenienti da versioni precedenti di Lync Server e Office Communications Server. A differenza delle versioni precedenti, Lync Server 2010 supporta i nuovi client Lync 2013. In questo modo, le organizzazioni che eseguono l'aggiornamento da Lync Server 2010 possono implementare nuovi client indipendenti dagli aggiornamenti di Lync Server.

<div>

## <a name="supported-server-and-client-combinations"></a>Combinazioni supportate di client e server

Nella tabella seguente sono indicate le combinazioni supportate di versioni client e server. Lync Server 2013 supporta due versioni client precedenti e Lync Server 2010 supporta il nuovo client Lync 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Supportato</p></td>
<td><p>Supportato</p></td>
<td><p>Non supportata</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>Supportato</p></td>
<td><p>Non supportata</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Supportato</p></td>
<td><p>Supportato</p></td>
<td><p>Non supportata</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>Supportato</p></td>
<td><p>Supportato</p></td>
<td><p>Non supportata</p></td>
</tr>
<tr class="odd">
<td><p>Chat di gruppo Lync 2010</p></td>
<td><p>Non applicabile</p></td>
<td><p>Supported1</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2010</p></td>
<td><p>Non supportato</p></td>
<td><p>Supportato</p></td>
<td><p>Non supportata</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendee</p></td>
<td><p>Non Supported2</p></td>
<td><p>Supportato</p></td>
<td><p>Non supportata</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable3</p></td>
<td><p>Supportato</p></td>
<td><p>Supportato</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>Non supportato</p></td>
<td><p>Supportato</p></td>
<td><p>Supportato</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>Non supportato</p></td>
<td><p>Supportato</p></td>
<td><p>Supportato</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Non supportato</p></td>
<td><p>Supportato</p></td>
<td><p>Supportato</p></td>
</tr>
</tbody>
</table>


1In Microsoft Lync Server 2010, la funzionalità Group Chat era disponibile con Group Chat Server, un'applicazione attendibile di terze parti per Lync Server 2010. I client Lync 2013 non sono compatibili con Lync Server 2010, Group Chat.

2Lync Web App 2013 ora offre un'esperienza di riunione completa, tra cui audio e video del computer, ed è considerata la sostituzione di Lync 2010 Attendee.

le funzionalità di presenza e messaggistica istantanea di 3Il in Office Communicator 2007 R2 sono compatibili con Lync Server 2013, ma non le funzionalità di conferenza. Durante la migrazione da Office Communications Server 2007 R2, Office Communicator 2007 R2 è idoneo per l'interoperabilità della messaggistica istantanea e della presenza, ma gli utenti devono utilizzare Lync Web App 2013 per partecipare alle riunioni di Lync Server 2013.

<div>


> [!NOTE]  
> Per informazioni dettagliate sulla capacità dei client di Lync Server 2013 di coesistere e interagire con client provenienti da versioni precedenti di Lync Server e Office Communications Server, vedere <A href="lync-server-2013-client-interoperability-in-lync-2013.md">client Interoperability in lync 2013</A> nella documentazione relativa alla pianificazione.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

