---
title: 'Lync Server 2013: attivazione del bypass multimediale di rete'
description: 'Lync Server 2013: abilitazione del bypass multimediale di rete.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1218376903aa42e1ea55205e3a9e8d16aade9a3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546552"
---
# <a name="enabling-network-media-bypass-in-lync-server-2013"></a>Abilitazione del bypass multimediale di rete in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Le impostazioni di bypass multimediale vengono applicate a livello globale in una distribuzione di Microsoft Lync Server 2013. Il bypass multimediale consente alle chiamate di bypassare il Mediation Server. Per informazioni dettagliate sull'utilizzo di bypass multimediale, vedere [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) nella sezione Planning.

È possibile abilitare e configurare il bypass multimediale dal pannello di controllo di Lync Server.

<div>

## <a name="to-enable-and-configure-media-bypass"></a>Per abilitare e configurare il bypass multimediale

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su  **Configurazione di rete ** e quindi su  **Globale **.

4.  Nella pagina  **Globale ** fare clic sulla scheda della configurazione  **Globale **. Esiste sempre una sola configurazione ed è sempre denominata Globale.

5.  Scegliere  **Mostra dettagli ** dal menu  **Modifica **.

6.  Nella pagina **Modifica impostazioni globali** fare clic sulla casella di controllo **Abilita bypass multimediale** .

7.  Selezionare una delle opzioni seguenti:
    
      - **Ignora sempre**     Selezionare questa opzione per tentare il bypass multimediale su tutte le chiamate. Questa opzione non sarà disponibile se il controllo di ammissione di chiamata (CAC) è abilitato. Se il servizio di controllo di ammissione non è abilitato, selezionare questa opzione nei casi seguenti:
        
          - Non è necessario il controllo della larghezza di banda.
        
          - Non è necessario disporre di una configurazione fine per determinare quando dovrebbe verificarsi un bypass.
        
          - La connettività tra gateway e client è completa.
    
      - **Utilizzare la configurazione**     dei siti e delle aree geografiche Se il servizio di controllo di ammissione è abilitato, questa opzione è selezionata per impostazione predefinita e non può essere modificata. Quando questa opzione è selezionata, i siti e le aree di configurazione di rete verranno utilizzati per determinare quando è possibile il bypass multimediale. Se si seleziona questa opzione, è possibile scegliere di abilitare il bypass per i siti non mappati. Fare clic sulla casella di controllo **Abilita bypass per i siti non mappati** solo se si dispone di uno o più siti di grandi dimensioni associati alla stessa area che non dispongono di vincoli di larghezza di banda (ad esempio, un sito centrale di grandi dimensioni) e si dispone anche di alcuni siti di succursale associati alla stessa area in cui sono presenti vincoli di larghezza di banda. Quando si Abilita il bypass per i siti non mappati, la configurazione viene semplificata perché sono state specificate solo le subnet associate ai siti di succursale anziché la necessità di specificare tutte le subnet associate a tutti i siti. Si consiglia di non selezionare la casella **di controllo Abilita bypass per i siti non mappati** se è abilitato CAC.

8.  Fare clic su  **Commit ** per salvare le modifiche.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Disabilitazione del bypass multimediale di rete in Lync Server 2013](lync-server-2013-disabling-network-media-bypass.md)  


[Opzioni di bypass multimediale globale in Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Pianificazione del bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

