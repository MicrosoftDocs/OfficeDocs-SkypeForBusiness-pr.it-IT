---
title: 'Lync Server 2013: Creare gruppi di agenti per Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0d282c4d166702c9b329271d69ef2d59b2f77aa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a>Creare gruppi di agenti per Response Group in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-12_

Quando si crea un gruppo di agenti, si selezionano gli agenti assegnati al gruppo e si specificano altre impostazioni di gruppo, ad esempio il metodo di routing, e se un agente può accedere e disconnettersi dal gruppo.

Un agente che deve accedere e disconnettersi dal gruppo, che è diverso dall'accesso o dall'esterno di Lync Server, viene chiamato *agente formale*. Gli agenti formali devono essere connessi al gruppo prima che possano ricevere le chiamate instradate al gruppo. Può essere utile per gli agenti che rispondono alle chiamate dal gruppo in base a tempo parziale. Gli agenti formali entrano e espongono i gruppi facendo clic su una voce di menu in Lync 2013 per aprire il browser Internet di Windows Internet Explorer e visualizzare una console della pagina Web.

Un agente che non esegue l'accesso o fuori dal gruppo viene chiamato *agente informale*. Gli agenti informali vengono automaticamente connessi al gruppo quando accedono a Lync Server e non possono disconnettersi dal gruppo.

<div>


> [!NOTE]  
> Solo gli utenti locali possono essere agenti. Se un agente viene spostato da locale a online, le chiamate di Response Group non verranno indirizzate a tale agente.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

[Creare o modificare un gruppo di agenti in Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

