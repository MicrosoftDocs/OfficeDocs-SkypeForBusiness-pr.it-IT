---
title: 'Lync Server 2013: disabilitare un utente per VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a0d2e5cf6eaa6ed594e7f5fbbc5b1e6a4c9103a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a>Disabilitare un utente per VoIP aziendale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Utilizzare la procedura seguente per disabilitare VoIP aziendale per un account utente abilitato per Lync Server 2013.

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a>Per disabilitare un account utente per VoIP aziendale

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Utenti**.

4.  Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account di Gestione account di protezione, dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) di linea dell'account utente da abilitare e quindi fare clic su **Trova**.

5.  Nella tabella fare clic sull'account utente che si desidera abilitare per VoIP aziendale.

6.  Scegliere **Mostra dettagli** dal menu **Modifica**.

7.  Nella pagina **Modifica utente Lync Server**, in **Telefonia** fare clic su qualsiasi opzione, ad eccezione di **VoIP aziendale**.
    
    <div>
    

    > [!NOTE]  
    > Per impedire a un utente di effettuare chiamate audio o video utilizzando Lync, in <STRONG>telefonia</STRONG>fare clic su <STRONG>audio/video disabilitato</STRONG>.

    
    </div>

8.  Fare clic su **Commit**.

L'utente non è ora in grado di utilizzare la funzionalità VoIP aziendale.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Abilitare gli utenti per VoIP aziendale in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  


[Gestione di VoIP aziendale per gli utenti in Lync Server 2013](lync-server-2013-managing-enterprise-voice-for-users.md)  
[Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

