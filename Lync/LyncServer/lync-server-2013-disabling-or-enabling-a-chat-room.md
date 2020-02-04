---
title: 'Lync Server 2013: Disabilitazione o abilitazione di una chat room'
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
ms.openlocfilehash: a3ed23319631dd8ab51131fe9a8d7a9099e35d18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a>Disabilitazione o abilitazione di una chat room in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-05_

Se l'argomento di una chat room persistente non è più pertinente, è possibile rendere la chat room non disponibile per gli utenti disabilitando il problema. Quando una chat room è disabilitata, tutti i membri vengono immediatamente disconnessi dalla sala. Dopo la disattivazione di una chat room, gli utenti non possono raggiungerla o trovarla nelle ricerche in chat room.

Una chat room disabilitata può essere abilitata in seguito da un amministratore della chat persistente. Se una chat room è disabilitata, viene mantenuta l'elenco di appartenenza e altre impostazioni. Se si abilita di nuovo la chat room, non è necessario ricreare manualmente le impostazioni.

Se la cronologia della chat room persiste (la persistenza della cronologia delle chat room è un'impostazione facoltativa per una categoria che si applica a tutte le camere all'interno della categoria; l'impostazione predefinita è che viene mantenuta, ma può essere disattivata impostando la **cronologia della chat di Enable** della categoria su false), il contenuto viene mantenuto quando la chat room è disabilitata. Tuttavia, tale contenuto non verrà visualizzato nelle ricerche durante il periodo di permanenza della chat room in uno stato disabilitato. Se in seguito si Abilita la chat room, gli utenti possono cercare i messaggi inviati prima della disattivazione della chat room.

Per informazioni dettagliate sulla disabilitazione e l'abilitazione delle chat room tramite l'interfaccia della riga di comando di Windows PowerShell, vedere "gestione sala" nella [configurazione del server di chat persistente usando i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md). Per disabilitare una chat room, usare un comando simile al seguente:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

Per abilitare una chat room, imposta la proprietà Disabled su false:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

Tieni presente che le chat room non possono essere abilitate o disabilitate usando il pannello di controllo di Lync Server.

Per informazioni dettagliate sulla configurazione delle chat room, vedere [configurare le sale in Lync Server 2013](lync-server-2013-configure-rooms.md) nella documentazione relativa alla distribuzione.

</div>

<span> </span>

</div>

</div>

</div>

