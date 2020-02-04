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
ms.openlocfilehash: 8f89b40a7398f35efab418fac7be92536ec17270
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a>Disabilitare un utente per VoIP aziendale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Usare la procedura seguente per disabilitare VoIP aziendale per un account utente abilitato per Lync Server 2013.

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a>Per disabilitare un account utente per VoIP aziendale

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **utenti**.

4.  Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente che si vuole abilitare e quindi fare clic su **trova**.

5.  Nella tabella fare clic sull'account utente che si desidera abilitare per VoIP aziendale.

6.  Nel menu **modifica** fare clic su **Mostra dettagli**.

7.  Nella pagina **modifica utente di Lync Server** , in **telefonia**, fare clic su qualsiasi opzione eccetto **VoIP aziendale**.
    
    <div>
    

    > [!NOTE]  
    > Per impedire a un utente di effettuare chiamate audio o video tramite Lync, in <STRONG>telefonia</STRONG>fare clic su <STRONG>disabilitato audio/video</STRONG>.

    
    </div>

8.  Fare clic su **Commit**.

Ora l'utente non è in grado di usare la caratteristica VoIP aziendale.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Consentire agli utenti di VoIP aziendale in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  


[Gestione di VoIP aziendale per gli utenti in Lync Server 2013](lync-server-2013-managing-enterprise-voice-for-users.md)  
[Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

