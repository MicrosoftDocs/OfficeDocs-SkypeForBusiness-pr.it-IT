---
title: 'Lync Server 2013: gestione dei gruppi di agenti di Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6cbea3b1a0d6638206a022ce5aded610dd60f23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a>Gestione dei gruppi di agenti di Response Group in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

Un gruppo di agenti è costituito da un gruppo di persone designate per rispondere alle chiamate a un gruppo di risposte. Quando si crea un gruppo di agenti, si selezionano gli agenti assegnati al gruppo e si specificano altre impostazioni di gruppo, ad esempio il metodo di routing, e se un agente può accedere e disconnettersi dal gruppo.

<div>


> [!NOTE]  
> Gli utenti devono essere abilitati per VoIP aziendale prima di poterli aggiungere ai gruppi di agenti. Per informazioni dettagliate su come abilitare un utente per VoIP aziendale, vedere <A href="lync-server-2013-enable-users-for-enterprise-voice.md">abilitare gli utenti per VoIP aziendale in Lync Server 2013</A>.



</div>

<div>


> [!NOTE]  
> Solo gli utenti locali possono essere agenti. Se un agente viene spostato da locale a online, le chiamate di Response Group non verranno indirizzate a tale agente.



</div>

Un agente che deve accedere e disconnettersi dal gruppo, che è diverso dall'accesso o dall'esterno di Lync Server, viene chiamato *agente formale*. Gli agenti formali devono essere connessi al gruppo prima che possano ricevere le chiamate instradate al gruppo. Può essere utile per gli agenti che rispondono alle chiamate dal gruppo in base a tempo parziale. Gli agenti formali entrano e espongono i gruppi facendo clic su una voce di menu in Lync 2013 per aprire il browser Internet di Windows Internet Explorer e visualizzare una console della pagina Web.

Un agente che non esegue l'accesso o fuori dal gruppo viene chiamato *agente informale*. Gli agenti informali vengono automaticamente connessi al gruppo quando accedono a Lync Server e non possono disconnettersi dal gruppo.

<div>


> [!IMPORTANT]  
> Quando si assegnano gli utenti come agenti del gruppo di risposta, informarli che, se la modalità di privacy è abilitata, devono cercare i contatti "RGS Presence Watcher" e aggiungerli al proprio elenco contatti. Gli agenti che hanno abilitato la modalità privacy, ma che non hanno "Watcher presenza RGS" nell'elenco contatti, non possono ricevere chiamate al Response Group. Gli agenti che non hanno la modalità di privacy abilitata non sono interessati.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Creare o modificare un gruppo di agenti in Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

  - [Eliminare un gruppo di agenti in Lync Server 2013](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

