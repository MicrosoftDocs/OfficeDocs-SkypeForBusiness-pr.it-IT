---
title: 'Lync Server 2013: visualizzazione delle informazioni sui criteri di posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f68ad38ffbc8bb1b4abdfbf8119add7d9f965e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-location-policy-information-in-lync-server-2013"></a>Visualizzazione delle informazioni sui criteri di posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

In Lync Server 2013 è possibile usare i criteri di posizione per applicare le impostazioni relative alle funzionalità avanzate di 9-1-1 (E9-1-1) e alle impostazioni della posizione per gli utenti o i contatti. I criteri di posizione determinano se un utente è abilitato per E9-1-1 e, in caso affermativo, qual è il comportamento di una chiamata di emergenza. Ad esempio, è possibile usare i criteri di posizione per definire il numero che costituisce una chiamata di emergenza, ad esempio 911 negli Stati Uniti, se la sicurezza aziendale deve essere notificata automaticamente e come deve essere instradata la chiamata.

È possibile configurare i criteri di posizione dal gruppo **configurazione di rete** nel pannello di controllo di Lync Server 2013. Dal pannello di controllo di Lync Server è possibile visualizzare, creare, modificare o eliminare i criteri di posizione. Usare la procedura seguente per visualizzare informazioni sui criteri di posizione. Per informazioni dettagliate sulla creazione o la modifica dei criteri di posizione, vedere [creazione o modifica di un criterio di posizione in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).

<div>

## <a name="to-view-information-about-a-location-policy"></a>Per visualizzare informazioni su un criterio di posizione

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **criteri posizione**.

4.  Nella pagina **criteri di posizione** selezionare i criteri di posizione che si desidera modificare.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.
    
    <div>
    

    > [!NOTE]  
    > È possibile visualizzare solo le informazioni su un criterio di posizione alla volta.

    
    </div>

Un singolo criterio, denominato globale, esiste per impostazione predefinita e non può essere eliminato o rinominato. È tuttavia possibile modificare il criterio globale. Questo criterio si applica a tutti gli utenti e i contatti, a meno che non si creino criteri del sito o criteri per utente. I criteri per utente devono essere applicati a utenti specifici.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creazione o modifica di un criterio di posizione in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Creare criteri di posizione in Lync Server 2013](lync-server-2013-create-location-policies.md)  
[Creare o modificare un sito di rete in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)  


[New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

