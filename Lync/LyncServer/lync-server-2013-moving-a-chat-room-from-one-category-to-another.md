---
title: "Lync Server 2013: Spostamento di una chat room da una categoria all'altra"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c61d20ff1de7437054df36af224293dcdcb61d54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a>Spostamento di una chat room da una categoria all'altra in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

È consigliabile non modificare la categoria di una chat room persistente dopo la creazione della chat room. Tuttavia, se il responsabile della chat room ha privilegi di **autore** in un'altra categoria, può trasferire la sala da una categoria a un'altra. La sala non viene eliminata e ricreata. Si tratta di un cambiamento di associazione all'interno del database.

La modifica di una categoria di chat room deve essere eseguita raramente. Una categoria determina l'appartenenza consentita per la chat room, quindi quando una chat room viene spostata in un'altra categoria, tutti gli elenchi di controllo di accesso di sistema (SACL) che non sono più supportati dalla nuova categoria vengono eliminati. Ad esempio, se un utente è stato un membro della chat room e non è più un **AllowedMember** nella nuova categoria, l'appartenenza alla sala verrà modificata e l'utente verrà rimosso dalla sala.

Per informazioni dettagliate sullo spostamento di una chat room tramite l'interfaccia della riga di comando di Windows PowerShell, vedere "gestione sala" in [configurazione del server di chat persistente usando i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Per informazioni dettagliate sulla configurazione delle chat room, vedere [configurare le sale in Lync Server 2013](lync-server-2013-configure-rooms.md) nella documentazione relativa alla distribuzione.

</div>

<span> </span>

</div>

</div>

</div>

