---
title: 'Lync Server 2013: eliminazione di un criterio percorso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34a71670bb9d4ffa9db67b594d17c330880998c3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a>Eliminazione di un criterio percorso in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-10_

In Lync Server 2013, è possibile utilizzare i criteri percorso per applicare le impostazioni relative alla funzionalità Enhanced 9-1-1 (E9-1-1) e alle impostazioni di posizione per utenti o contatti. I criteri di posizione determinano se un utente è abilitato per E9-1-1 e in questo caso il funzionamento di una chiamata di emergenza. Ad esempio, è possibile usare i criteri di posizione per definire il numero di emergenza (ad esempio il 113 in Italia), se la sicurezza aziendale deve essere automaticamente notificata e come instradare la chiamata.

È possibile configurare i criteri percorso dal gruppo **configurazione di rete** nel pannello di controllo di Lync Server 2013. Dal pannello di controllo di Lync Server è possibile visualizzare, creare, modificare o eliminare i criteri di percorso. Usare le procedure seguenti per eliminare un criteri di posizione. Per informazioni dettagliate sulla creazione o la modifica dei criteri percorso, vedere [creazione o modifica di un criterio percorso in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).

<div>

## <a name="to-delete-a-location-policy"></a>Per eliminare un criterio di posizione

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su  **Configurazione di rete ** e quindi su  **Criteri percorso **.

4.  Nella pagina  **Criteri percorso ** selezionare il criterio percorso che si desidera eliminare.
    
    <div>
    

    > [!NOTE]  
    > È possibile eliminare più criteri percorso contemporaneamente. A tale scopo, tenere premuto CTRL e selezionare i diversi criteri. In alternativa, per selezionare tutti i criteri, scegliere  <STRONG>Seleziona tutto </STRONG> dal menu  <STRONG>Modifica </STRONG>.

    
    </div>

5.  Scegliere  **Elimina ** dal menu  **Modifica **.

6.  Fare clic su **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > Non è possibile eliminare il criterio percorso Globale. Se si tenta di eliminare tale criterio, verrà visualizzato un messaggio di avviso e il criterio verrà reimpostato sui relativi valori predefiniti.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creazione o modifica di un criterio percorso in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Visualizzazione delle informazioni sui criteri percorso in Lync Server 2013](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

