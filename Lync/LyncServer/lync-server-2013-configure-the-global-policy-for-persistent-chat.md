---
title: 'Lync Server 2013: configurare i criteri globali per la chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c77093e640d51204a7e16b2b32df02afcefe0bd7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a>Configurare il criterio globale per la chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-06_

È possibile utilizzare il criterio globale predefinito per abilitare le impostazioni di chat persistente per tutti gli utenti della distribuzione. È inoltre possibile specificare criteri aggiuntivi per i siti e gli utenti per controllare se la chat persistente è abilitata o disabilitata per utenti e siti specifici.

Non è possibile eliminare i criteri globali. Se si tenta l'eliminazione, la configurazione viene reimpostata sui valori predefiniti.

<div>


> [!NOTE]  
> Per configurare e utilizzare il server Chat persistente, è necessario innanzitutto utilizzare Generatore di topologie per aggiungere il supporto del server Chat persistente alla topologia e quindi pubblicare la topologia. Per ulteriori informazioni, vedere <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">aggiunta del server Chat persistente alla distribuzione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.<BR>Per configurare le impostazioni di configurazione del server Chat persistente, vedere <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurare le opzioni del server Chat persistente a livello globale o per il pool di server Chat persistente in Lync server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Per configurare i criteri globali per la chat persistente

1.  Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Dal menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL di amministratore. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md) nella documentazione relativa alle operazioni.
    
    <div>
    

    > [!IMPORTANT]  
    > È inoltre possibile utilizzare i cmdlet di Windows PowerShell. Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in Deployment documentation.

    
    </div>

3.  Nel pannello di controllo di Lync Server, fare clic su **Persistent Chat**e quindi su **criteri di chat persistente**.

4.  Fare clic su **Globale** nell'elenco di criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.

5.  In **Modifica Criteri Persistent Chat - Globale** eseguire le operazioni seguenti:
    
      - In **Nome** specificare un nuovo nome per i criteri globali, se non si desidera usare il nome predefinito Globale.
    
      - In **Descrizione**fornire informazioni dettagliate sugli elementi del criterio utente, ad esempio criteri globali per NomeSitoCentrale ".
    
      - Per controllare la chat persistente per tutti i siti e gli utenti non controllati in modo specifico tramite criteri utente o di sito, selezionare o deselezionare la casella di controllo **Abilita Chat persistente** .

6.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

