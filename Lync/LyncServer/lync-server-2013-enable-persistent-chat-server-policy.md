---
title: 'Lync Server 2013: Abilitare i criteri del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58e71cd92182fc9f68d272ba23079677983b399
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a>Abilitare i criteri del server Chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-06_

Nel pannello di controllo di Lync Server 2013 è possibile usare la pagina dei **criteri di chat persistente** del gruppo di **chat persistente** per gestire i criteri a livello globale, di pool, di sito o utente, tra cui la configurazione dei criteri globali predefiniti e la creazione di uno o più criteri aggiuntivi per l'utente e il sito per la distribuzione. Se un utente è abilitato per i criteri per il server di chat persistente, l'ambiente del server di chat persistente viene visualizzato nel client Lync 2013.

<div>


> [!NOTE]  
> Nella topologia i criteri del sito del server di chat persistenti si applicano globalmente, per il pool di utenti o per il sito per utente o per utente.



</div>

Il criterio globale viene creato automaticamente quando si distribuisce il server di chat persistente e può essere configurato, ma non eliminato. Poiché il criterio globale si applica a tutti gli utenti, non è necessario configurarlo per utente.

È possibile creare e configurare più criteri per il sito e gli utenti che, insieme al criterio globale, consentono agli utenti di usare il server di chat persistente. I criteri per i server di chat persistenti per pool e siti eseguono l'override del criterio server globale di chat persistente, ma solo per gli utenti del sito. I criteri utente hanno la priorità sia sul criterio globale che sui criteri pool e sito per gli utenti a cui viene assegnato il criterio utente.

<div>


> [!NOTE]  
> Per configurare e usare il server di chat persistente, è necessario prima di tutto usare generatore di topologia per aggiungere il supporto del server di chat persistente alla topologia e quindi pubblicare la topologia. Per informazioni dettagliate, vedere <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">aggiunta di un server di chat persistente alla distribuzione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Configurare i criteri globali per Chat persistente in Lync Server 2013](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [Creare criteri sito per chat persistente in Lync Server 2013](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [Creare criteri utente per Chat persistente in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [Applicare i criteri di Chat persistente a un utente o un gruppo di utenti in Lync Server 2013](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

