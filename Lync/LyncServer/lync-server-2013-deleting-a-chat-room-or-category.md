---
title: 'Lync Server 2013: eliminazione di una chat room o una categoria'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e94068337747feee592ec25669e9d7b5fc10bc3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a>Eliminazione di una chat room o di una categoria in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

È possibile eliminare le chat room permanenti. Se una chat room non viene più utilizzata, è possibile disabilitarla. Per informazioni dettagliate, vedere [disattivazione o abilitazione di una chat room in Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).

Un amministratore di chat persistente può eseguire query per le chat room disabilitate e può periodicamente eliminare e cancellare definitivamente le chat room utilizzando il cmdlet di Windows PowerShell **Remove-CsPersistentChatRoom**.

Le categorie possono essere eliminate. Tuttavia, per eliminare una categoria, è prima necessario eliminare tutte le chat room che appartengono a essa oppure spostare le chat room in una nuova categoria, lasciando una categoria vuota per l'eliminazione. Il server Chat persistente non consente di eliminare una categoria contenente chat room. Per informazioni dettagliate, vedere [spostamento di una chat room da una categoria all'altra in Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).

Per informazioni dettagliate sull'eliminazione di categorie vuote tramite l'interfaccia della riga di comando di Windows PowerShell, vedere la sezione relativa alla gestione delle chat room in [Configuring Persistent chatroom server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Per informazioni dettagliate sulle chat room e sulle categorie, vedere [Configure rooms in Lync server 2013](lync-server-2013-configure-rooms.md) e [Configure Categories in Lync Server 2013](lync-server-2013-configure-categories.md) nella documentazione relativa alla distribuzione.

</div>

<span> </span>

</div>

</div>

</div>

