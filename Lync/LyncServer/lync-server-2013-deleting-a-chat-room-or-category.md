---
title: 'Lync Server 2013: Eliminazione di una chat room o una categoria'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f64b89abd0b3266d2be52e300458ceabf3f9b915
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a>Eliminazione di una chat room o una categoria in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Le chat room permanenti possono essere eliminate. Se si ha una chat room che non viene più usata, è possibile disabilitarla. Per informazioni dettagliate, vedere [disabilitazione o abilitazione di una chat room in Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).

Un amministratore della chat persistente può eseguire query per le chat room disattivate e può periodicamente eliminare e cancellare definitivamente le chat room usando il cmdlet di Windows PowerShell **Remove-CsPersistentChatRoom**.

Le categorie possono essere eliminate. Tuttavia, per eliminare una categoria, è prima necessario eliminare tutte le chat room o spostarle in una nuova categoria, lasciando una categoria vuota per l'eliminazione. Il server di chat persistente non consente di eliminare una categoria che contiene chat room. Per informazioni dettagliate, vedere [spostamento di una chat room da una categoria a un'altra in Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).

Per informazioni dettagliate sull'eliminazione di categorie vuote tramite l'interfaccia della riga di comando di Windows PowerShell, vedere "gestione sala" nella [configurazione del server di chat persistente usando i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Per informazioni dettagliate sulle chat room e le categorie, vedere [configurare le camere in Lync server 2013](lync-server-2013-configure-rooms.md) e [configurare le categorie in Lync Server 2013](lync-server-2013-configure-categories.md) nella documentazione relativa alla distribuzione.

</div>

<span> </span>

</div>

</div>

</div>

