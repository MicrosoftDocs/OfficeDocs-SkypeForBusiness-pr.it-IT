---
title: 'Lync Server 2013: creare un criterio utente per la chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a user policy for Persistent Chat
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48185103
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dba93ca943c16caa6ee4982533e59c958e60ffc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501843"
---
# <a name="create-a-user-policy-for-persistent-chat-in-lync-server-2013"></a>Creare un criterio utente per la chat persistente in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-06_

Nel pannello di controllo di Lync Server, è possibile definire i criteri utente che possono essere assegnati agli utenti in **utenti**.

I criteri utente hanno la precedenza sui criteri globali e di sito, ma solo per gli utenti specifici a cui tali criteri utente sono assegnati.

<div>


> [!NOTE]  
> Per configurare e utilizzare il server Chat persistente, è necessario innanzitutto utilizzare Generatore di topologie per aggiungere il supporto del server Chat persistente alla topologia e quindi pubblicare la topologia. Per ulteriori informazioni, vedere <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">aggiunta del server Chat persistente alla distribuzione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.<BR>Per configurare le impostazioni di configurazione del server Chat persistente, vedere <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurare le opzioni del server Chat persistente a livello globale o per il pool di server Chat persistente in Lync server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="to-create-a-user-policy-for-persistent-chat"></a>Per creare un criterio utente per la chat persistente

1.  Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Dal menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL di amministratore. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > È inoltre possibile utilizzare i cmdlet di Windows PowerShell. Vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server using Windows PowerShell cmdlets</A> nella documentazione relativa alla distribuzione.

    
    </div>

3.  Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Criteri Persistent Chat**.

4.  Fare clic su **Nuovo** e quindi su **Criteri utente**.

5.  In **Nuovi criteri Persistent Chat** eseguire le operazioni seguenti:
    
      - In **Nome** specificare un nome per il nuovo criterio utente.
    
      - In **Descrizione**fornire informazioni dettagliate sugli elementi del criterio utente, ad esempio criteri di chat persistente per utenti specifici.
    
      - Per controllare la chat persistente per tutti gli utenti non controllati in modo specifico tramite criteri utente, selezionare o deselezionare la casella di controllo **Abilita Chat persistente** .

6.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

