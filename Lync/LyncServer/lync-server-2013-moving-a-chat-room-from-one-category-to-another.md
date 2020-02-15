---
title: "Lync Server 2013: spostamento di una chat room da una categoria all'altra"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40077d8092f8b0b78b6e9ce78cd16c6f1e0812f0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a>Spostamento di una chat room da una categoria all'altra in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Si consiglia di non modificare la categoria di una chat room persistente dopo la creazione della chat room. Tuttavia, se il responsabile della chat room ha privilegi di **creatore** in un'altra categoria, può spostare la sala da una categoria all'altra. La sala non viene eliminata e ricreata. Si tratta di un cambiamento di associazione all'interno del database.

La modifica della categoria di una chat room deve essere un'operazione eseguita raramente. Una categoria determina i membri a cui è consentito accedere alla chat room; se questa viene spostata in un'altra categoria, tutti gli elenchi di controllo di accesso del sistema (SACL) non supportati dalla nuova categoria vengono eliminati. Ad esempio, se un utente membro di una chat room non è più un **AllowedMember** nella nuova categoria, l'appartenenza alla chat risulterà modificata, e l'utente non avrà più accesso alla chat room.

Per informazioni dettagliate sullo spostamento di una chat room tramite l'interfaccia della riga di comando di Windows PowerShell, vedere la sezione relativa alla gestione delle chat room in [Configuring Persistent chatroom server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Per informazioni dettagliate sulla configurazione delle chat room, vedere [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) nella documentazione relativa alla distribuzione.

</div>

<span> </span>

</div>

</div>

</div>

