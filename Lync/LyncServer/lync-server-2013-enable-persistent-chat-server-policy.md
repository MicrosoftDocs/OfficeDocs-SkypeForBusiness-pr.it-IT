---
title: 'Lync Server 2013: abilitare i criteri del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1f98275ee911d1abecbc60907653ad8de0a4222
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a>Abilitare i criteri del server Chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-06_

Nel pannello di controllo di Lync Server 2013, è possibile utilizzare la pagina **criteri di chat persistente** del gruppo di **chat persistente** per gestire i criteri a livello globale, di pool, di sito o di utente, inclusa la configurazione dei criteri globali predefiniti e la creazione di uno o più criteri di sito e utente aggiuntivi per la distribuzione. Se un utente è abilitato per il server Chat persistente in base ai criteri, l'ambiente del server Chat persistente viene visualizzato nel client Lync 2013.

<div>


> [!NOTE]  
> Nella topologia, i criteri sito del server Chat persistente si applicano a livello globale, per pool di utenti o per sito utente o per utente.



</div>

Il criterio globale viene creato automaticamente quando si distribuisce il server Chat persistente ed è possibile configurarlo, ma non eliminarlo. Poiché il criterio globale si applica a tutti gli utenti, non è necessario configurarlo per utente.

È possibile creare e configurare più criteri di sito e utente che, insieme ai criteri globali, consentono agli utenti di Persistent Chat Server. I criteri del server Chat persistente per i pool e i siti eseguono l'override del criterio del server Chat persistente globale, ma solo per gli utenti del sito. I criteri utente hanno la priorità sia sul criterio globale che sui criteri pool e sito per gli utenti a cui viene assegnato il criterio utente.

<div>


> [!NOTE]  
> Per configurare e utilizzare il server Chat persistente, è necessario innanzitutto utilizzare Generatore di topologie per aggiungere il supporto del server Chat persistente alla topologia e quindi pubblicare la topologia. Per ulteriori informazioni, vedere <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">aggiunta del server Chat persistente alla distribuzione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Configurare il criterio globale per la chat persistente in Lync Server 2013](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [Creare criteri sito per chat persistente in Lync Server 2013](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [Creare un criterio utente per la chat persistente in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [Applicare un criterio di chat persistente a un utente o a un gruppo di utenti in Lync Server 2013](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

