---
title: 'Lync Server 2013: applicazione di un criterio di chat persistente a un utente o a un gruppo di utenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Apply a Persistent Chat policy to a user or user group
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48184652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c32fea58eafc8728144885826c822c7485441a7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a>Applicare un criterio di chat persistente a un utente o a un gruppo di utenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-06_

Se un utente è stato abilitato per Lync Server 2013, è possibile applicare criteri adeguati a utenti specifici per abilitarli o disabilitarli per il server Chat persistente.

<div>


> [!NOTE]  
> Per configurare e utilizzare il server Chat persistente, è necessario innanzitutto utilizzare Generatore di topologie per aggiungere il supporto del server Chat persistente alla topologia e quindi pubblicare la topologia. Per ulteriori informazioni, vedere <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">aggiunta del server Chat persistente alla distribuzione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.<BR>Per configurare le impostazioni di configurazione del server Chat persistente, vedere <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurare le opzioni del server Chat persistente a livello globale o per il pool di server Chat persistente in Lync server 2013</A> nella documentazione relativa alla distribuzione.



</div>

Utilizzare la procedura descritta in questo argomento per applicare un criterio utente di chat persistente creato in precedenza a uno o più account utente o gruppi di utenti.

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Per applicare un criterio utente di chat persistente a un account utente

1.  Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Dal menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL di amministratore. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.

4.  Nella tabella in cui sono elencati i risultati di ricerca, fare clic sull'account utente, scegliere **Modifica** e quindi **Mostra dettagli**.

5.  In **modifica utente di Lync Server** in **criteri di Persistent Chat**Selezionare il criterio utente di chat persistente che si desidera applicare.
    
    <div>
    

    > [!NOTE]  
    > Le <STRONG> &lt;impostazioni&gt; automatiche</STRONG> applicano il criterio effettivo predefinito. Queste impostazioni vengono applicate automaticamente dal server.

    
    </div>

6.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

