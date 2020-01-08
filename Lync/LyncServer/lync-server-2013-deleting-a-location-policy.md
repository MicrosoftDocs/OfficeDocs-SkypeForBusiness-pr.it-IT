---
title: 'Lync Server 2013: eliminazione di un criterio di posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4766d2b05cef89ab29b9c303c5ba1ec456843669
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a>Eliminazione di un criterio di posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-10_

In Lync Server 2013 è possibile usare i criteri di posizione per applicare le impostazioni relative alle funzionalità avanzate di 9-1-1 (E9-1-1) e alle impostazioni della posizione per gli utenti o i contatti. I criteri di posizione determinano se un utente è abilitato per E9-1-1 e, in caso affermativo, qual è il comportamento di una chiamata di emergenza. Ad esempio, è possibile usare i criteri di posizione per definire il numero che costituisce una chiamata di emergenza, ad esempio 911 negli Stati Uniti, se la sicurezza aziendale deve essere notificata automaticamente e come deve essere instradata la chiamata.

È possibile configurare i criteri di posizione dal gruppo **configurazione di rete** nel pannello di controllo di Lync Server 2013. Dal pannello di controllo di Lync Server è possibile visualizzare, creare, modificare o eliminare i criteri di posizione. Usare le procedure seguenti per eliminare un criterio di posizione. Per informazioni dettagliate sulla creazione o la modifica dei criteri di posizione, vedere [creazione o modifica di un criterio di posizione in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).

<div>

## <a name="to-delete-a-location-policy"></a>Per eliminare un criterio di posizione

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **criteri posizione**.

4.  Nella pagina **criteri di posizione** selezionare i criteri di posizione che si desidera eliminare.
    
    <div>
    

    > [!NOTE]  
    > È possibile eliminare più criteri di posizione alla volta. Per eseguire questa operazione, premere CTRL e selezionare più criteri tenendo premuto il tasto CTRL. In alternativa, per selezionare tutti i criteri, fare clic su <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>modifica</STRONG> .

    
    </div>

5.  Scegliere **Elimina**dal menu **modifica** .

6.  Fare clic su **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > Non è possibile eliminare i criteri di posizione globale. Se si tenta di eliminare il criterio globale si riceverà un messaggio di avviso e il criterio verrà reimpostato sui valori predefiniti.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creazione o modifica di un criterio di posizione in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Visualizzazione delle informazioni sui criteri di posizione in Lync Server 2013](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

