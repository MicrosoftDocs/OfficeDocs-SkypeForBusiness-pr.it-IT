---
title: 'Lync Server 2013: configurare i componenti aggiuntivi per le chat room'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8779e770ca96cbfc34bbbc1f1897df1f5eb9ea03
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523053"
---
# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a>Configurare i componenti aggiuntivi per le chat room in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Nel pannello di controllo di Lync Server 2013, è possibile utilizzare la sezione **componente aggiuntivo** della pagina **chat persistente** per associare gli URL alle chat room persistente. Questi URL vengono visualizzati nel client Lync 2013 nella chat room del riquadro Extensibility di conversazione. Un amministratore deve aggiungere componenti aggiuntivi all'elenco dei componenti aggiuntivi registrati e i responsabili/creatori della chat devono associare le camere a uno dei componenti aggiuntivi registrati prima che gli utenti possano visualizzare questo aggiornamento nel client Lync 2013.

I componenti aggiuntivi vengono utilizzati per estendere l'esperienza in chat. Un componente aggiuntivo tipico potrebbe includere un URL che punta a un'applicazione Silverlight che intercetta quando un ticker di stock viene inserito in una chat room e visualizza la cronologia del magazzino nel riquadro Extensibility. Tra gli altri esempi c'è l'integrazione di un URL OneNote 2013 nella chat room in forma di componente aggiuntivo, per includere un contesto condiviso, ad esempio "Di facile riconoscibilità" o "Argomento del giorno".

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a>Per configurare componenti aggiuntivi per chat room

1.  Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Dal menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL di amministratore. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > È inoltre possibile utilizzare i cmdlet di Windows PowerShell. Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> nella documentazione relativa alla distribuzione.

    
    </div>

3.  Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Componente aggiuntivo**.
    
    Per più distribuzioni di pool di server Chat persistente, selezionare il pool appropriato dall'elenco a discesa.

4.  Nella pagina **Componente aggiuntivo** fare clic su **Nuovo**.

5.  In **Seleziona un servizio**selezionare il servizio corrispondente al pool di server Chat persistente in cui è necessario creare il componente aggiuntivo. I componenti aggiuntivi non possono essere spostati da un pool all'altro o condivisi tra diversi pool.

6.  In **Nuovo componente aggiuntivo** eseguire le operazioni seguenti:
    
      - In **Nome** specificare un nome per il nuovo componente aggiuntivo.
    
      - In **URL** specificare l'URL da associare al componente aggiuntivo. Gli URL sono limitati ai protocolli http e https.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Aprire gli strumenti di amministrazione di Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)  


[Configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

