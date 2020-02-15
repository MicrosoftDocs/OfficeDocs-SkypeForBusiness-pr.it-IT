---
title: 'Lync Server 2013: gestione dei gruppi di agenti di Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f791ea6a2091ab50e159b541ef19789ffcde02b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41992171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a>Gestione dei gruppi di agenti di Response Group in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

Un gruppo di agenti è un gruppo di persone che hanno il compito di rispondere alle chiamate di un Response Group. Quando si crea un gruppo di agenti, è necessario selezionare gli agenti assegnati al gruppo e specificare ulteriori impostazioni per il gruppo, ad esempio il metodo di routing e se un agente possa o meno accedere al gruppo e disconnettersi da esso.

<div>


> [!NOTE]  
> Gli utenti devono essere abilitati per VoIP aziendale prima di poterli aggiungere ai gruppi di agenti. Per informazioni dettagliate sull'abilitazione di un utente per VoIP aziendale, vedere <A href="lync-server-2013-enable-users-for-enterprise-voice.md">abilitare gli utenti per VoIP aziendale in Lync Server 2013</A>.



</div>

<div>


> [!NOTE]  
> Solo gli utenti che si trovano in locale possono essere agenti. Se un agente viene spostato da in locale a online, le chiamate del Response Group non gli verranno instradate.



</div>

Un agente che deve accedere e uscire dal gruppo, che è diverso dall'accesso o dall'esterno di Lync Server, è definito *agente formale*. Gli agenti formali devono aver effettuato l'accesso al gruppo per poter ricevere le chiamate instradate a tale gruppo. Questo requisito può rivelarsi utile per gli agenti che rispondono solo a tempo parziale alle chiamate provenienti dal gruppo. Gli agenti formali si configurano ed escono dai rispettivi gruppi facendo clic su una voce di menu in Lync 2013 per aprire il browser Internet di Windows Internet Explorer e visualizzare una console di pagina Web.

Un agente che non accede o esce dal gruppo è definito *agente informale*. Gli agenti informali vengono automaticamente sottoscritti al gruppo quando accedono a Lync Server e non possono disconnettersi dal gruppo.

<div>


> [!IMPORTANT]  
> Quando si assegnano utenti come agenti del Response Group, informarli che, se è abilitata la modalità Privacy, dovranno cercare i contatti "RGS Presence Watcher" e aggiungerli all'elenco contatti. Gli agenti con modalità privacy abilitata ma nel cui elenco contatti non sono presenti contatti "RGS Presence Watcher" non possono ricevere chiamate per il Response Group. Questa restrizione non si applica agli agenti non in modalità privacy.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Creare o modificare un gruppo di agenti in Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

  - [Eliminare un gruppo di agenti in Lync Server 2013](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

