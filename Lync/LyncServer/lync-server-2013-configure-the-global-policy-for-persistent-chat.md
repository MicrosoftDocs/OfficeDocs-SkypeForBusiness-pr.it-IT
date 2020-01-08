---
title: 'Lync Server 2013: Configurare i criteri globali per Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 236023756f8d2c917812d38f5a03da8dd4c40b5b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a>Configurare i criteri globali per Chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-06_

È possibile usare i criteri globali predefiniti per abilitare le impostazioni della chat persistente per tutti gli utenti della distribuzione. È anche possibile specificare criteri aggiuntivi per i siti e gli utenti per controllare se la chat persistente è abilitata o disabilitata per utenti e siti specifici.

Non è possibile eliminare il criterio globale. Se si tenta di eliminarlo, la configurazione viene reimpostata sui valori predefiniti.

<div>


> [!NOTE]  
> Per configurare e usare il server di chat persistente, è necessario prima di tutto usare generatore di topologia per aggiungere il supporto del server di chat persistente alla topologia e quindi pubblicare la topologia. Per informazioni dettagliate, vedere <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">aggiunta di un server di chat persistente alla distribuzione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.<BR>Per configurare le impostazioni di configurazione del server di chat persistente, vedere <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurare le opzioni del server di chat permanenti globalmente o per il pool di server di chat persistente in Lync server 2013</A> nella documentazione relativa alla distribuzione



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Per configurare il criterio globale per la chat persistente

1.  Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, eseguire l'accesso a qualsiasi computer nella distribuzione interna.

2.  Nel menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md) nella documentazione Operations.
    
    <div>
    

    > [!IMPORTANT]  
    > È anche possibile usare i cmdlet di Windows PowerShell. Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configurazione del server di chat persistente con i cmdlet di Windows PowerShell</A> nella documentazione di distribuzione.

    
    </div>

3.  Nel pannello di controllo di Lync Server fare clic su **chat persistente**e quindi su **criteri di chat permanenti**.

4.  Fare clic su **Globale** nell'elenco dei criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.

5.  In **Modifica Criteri Chat persistente- Globale** eseguire le operazioni seguenti:
    
      - In **Nome** specificare un nuovo nome per i criteri globali, se non si desidera utilizzare il nome predefinito Globale.
    
      - In **Descrizione**specificare i dettagli relativi al criterio utente (ad esempio, criteri globali per centralSiteName).
    
      - Per controllare la chat persistente per tutti i siti e gli utenti non controllati in modo specifico tramite criteri del sito o criteri utente, selezionare o deselezionare la casella di controllo **Abilita Chat persistente** .

6.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

