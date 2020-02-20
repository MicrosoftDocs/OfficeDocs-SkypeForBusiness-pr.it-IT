---
title: 'Lync Server 2013: creare gruppi di agenti di Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be70adae85256178defca0269e6663bad76dabfc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a>Creare gruppi di agenti di Response Group Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-12_

Quando si crea un gruppo di agenti, è necessario selezionare gli agenti assegnati al gruppo e specificare impostazioni aggiuntive per il gruppo, ad esempio il metodo di routing e se un agente possa o meno accedere al gruppo e disconnettervisi.

Un agente che deve accedere e uscire dal gruppo, che è diverso dall'accesso o dall'esterno di Lync Server, è definito *agente formale*. Gli agenti formali devono aver effettuato l'accesso al gruppo per poter ricevere le chiamate instradate a tale gruppo. Questo requisito può rivelarsi utile per gli agenti che rispondono alle chiamate provenienti dal gruppo a tempo parziale. Gli agenti formali si configurano ed escono dai rispettivi gruppi facendo clic su una voce di menu in Lync 2013 per aprire il browser Internet di Windows Internet Explorer e visualizzare una console di pagina Web.

Un agente che non accede o esce dal gruppo è definito *agente informale*. Gli agenti informali vengono automaticamente sottoscritti al gruppo quando accedono a Lync Server e non possono disconnettersi dal gruppo.

<div>


> [!NOTE]  
> Solo gli utenti che si trovano in locale possono essere agenti. Se un agente viene spostato da in locale a online, le chiamate del Response Group non gli verranno instradate.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

[Creare o modificare un gruppo di agenti in Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

