---
title: 'Lync Server 2013: Client supportati dalle distribuzioni precedenti'
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
ms.openlocfilehash: 38d4fe00b834778f1ad87f021656ed08488c1ba2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-clients-from-previous-deployments-in-lync-server-2013"></a>Client supportati dalle distribuzioni precedenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-12-14_

In uno scenario di coesistenza i client Lync Server 2013 possono interagire con i client di versioni precedenti di Lync Server e Office Communications Server. A differenza delle versioni precedenti, Lync Server 2010 supporta i nuovi client Lync 2013. Ciò consente alle organizzazioni che eseguono l'aggiornamento da Lync Server 2010 di implementare nuovi client indipendentemente dagli aggiornamenti di Lync Server.

<div>

## <a name="supported-server-and-client-combinations"></a>Combinazioni di server e client supportate

La tabella seguente mostra le combinazioni supportate delle versioni client e delle versioni del server. Lync Server 2013 supporta due versioni precedenti del client e Lync Server 2010 supporta il nuovo client Lync 2013.


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
<td><p>Supportati</p></td>
<td><p>Supportati</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>Supportati</p></td>
<td><p>Non supportato</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Supportati</p></td>
<td><p>Supportati</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="even">
<td><p>Assistente di Lync 2010</p></td>
<td><p>Supportati</p></td>
<td><p>Supportati</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="odd">
<td><p>Chat di gruppo di Lync 2010</p></td>
<td><p>Non applicabile</p></td>
<td><p>Supported1</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2010</p></td>
<td><p>Non supportato</p></td>
<td><p>Supportati</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="odd">
<td><p>Partecipante Lync 2010</p></td>
<td><p>Non Supported2</p></td>
<td><p>Supportati</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable3</p></td>
<td><p>Supportati</p></td>
<td><p>Supportati</p></td>
</tr>
<tr class="odd">
<td><p>Assistente di Microsoft Office Communications Server 2007 R2</p></td>
<td><p>Non supportato</p></td>
<td><p>Supportati</p></td>
<td><p>Supportati</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>Non supportato</p></td>
<td><p>Supportati</p></td>
<td><p>Supportati</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Non supportato</p></td>
<td><p>Supportati</p></td>
<td><p>Supportati</p></td>
</tr>
</tbody>
</table>


1In Microsoft Lync Server 2010, la funzionalità Group Chat era disponibile con Group Chat Server, un'applicazione attendibile di terze parti per Lync Server 2010. I client Lync 2013 non sono compatibili con Lync Server 2010, chat di gruppo.

2Lync Web App 2013 ora offre un'esperienza di riunione completa, inclusi l'audio e il video del computer, ed è considerata la sostituzione per il partecipante di Lync 2010.

le funzionalità di presenza e messaggistica istantanea di 3Il in Office Communicator 2007 R2 sono compatibili con Lync Server 2013, ma le funzionalità di conferenza non lo sono. Durante la migrazione da Office Communications Server 2007 R2, Office Communicator 2007 R2 è adatto per l'interoperabilità in presenza e messaggistica istantanea, ma gli utenti devono usare Lync Web App 2013 per partecipare alle riunioni di Lync Server 2013.

<div>


> [!NOTE]  
> Per informazioni dettagliate sulla possibilità che i client di Lync Server 2013 coesistano e interagisca con i client di versioni precedenti di Lync Server e Office Communications Server, vedere <A href="lync-server-2013-client-interoperability-in-lync-2013.md">interoperabilità dei client in lync 2013</A> nella documentazione relativa alla pianificazione.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

