---
title: 'Lync Server 2013: disabilitazione o abilitazione di una chat room'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96ad55bd6396cdac9b30441eb8b41bebaba834ff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a>Disabilitazione o abilitazione di una chat room in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-05_

Se l'argomento di una chat room persistente non è più pertinente, è possibile rendere la chat room non disponibile per gli utenti disabilitarla. Quando si disabilita una chat room, tutti i membri vengono disconnessi immediatamente. Dopo la disabilitazione di una chat room, gli utenti non possono più parteciparvi né trovarla eseguendo ricerche di chat room.

Una chat room disattivata può essere abilitata in un secondo momento da un amministratore di chat persistente. Se una chat è disabilitata, il relativo elenco dei membri e le altre impostazioni vengono mantenuti. In questo modo, se si decide di riabilitarla, non sarà necessario ricreare manualmente le impostazioni.

Se è configurata la persistenza della cronologia della chat room, il contenuto verrà mantenuto in caso di disabilitazione della chat room. La persistenza della cronologia della chat room è un'impostazione facoltativa di una categoria e viene applicata a tutte le chat room della categoria. Per impostazione predefinita, la persistenza è abilitata, ma è possibile disabilitarla impostando la proprietà **Abilita cronologia chat** della categoria su false. Se si disabilita una chat room, il contenuto tuttavia non verrà visualizzato nelle ricerche per tutto il tempo in cui la chat room resterà disabilitata. Se successivamente si abilita la chat room, gli utenti potranno ricercare messaggi inseriti prima che la chat room venisse disabilitata.

Per informazioni dettagliate sulla disattivazione e l'abilitazione delle chat room tramite l'interfaccia della riga di comando di Windows PowerShell, vedere la sezione "gestione sala" in [configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md). Per disabilitare una chat room, utilizzare un comando simile al seguente:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

Per abilitare una chat room, impostare la proprietà Disabled su false:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

Si noti che le chat room non possono essere abilitate o disabilitate utilizzando il pannello di controllo di Lync Server.

Per informazioni dettagliate sulla configurazione delle chat room, vedere [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) nella documentazione relativa alla distribuzione.

</div>

<span> </span>

</div>

</div>

</div>

