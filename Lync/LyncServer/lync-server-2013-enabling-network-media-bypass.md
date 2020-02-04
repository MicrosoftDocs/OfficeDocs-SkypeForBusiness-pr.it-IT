---
title: 'Lync Server 2013: abilitazione del bypass multimediale di rete'
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
ms.openlocfilehash: 4e0b5e7b060d056a785e80fdf29ded718d120bc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a>Abilitare il bypass multimediale di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Le impostazioni di bypass multimediale si applicano globalmente in una distribuzione di Microsoft Lync Server 2013. Il bypass multimediale consente alle chiamate di aggirare il Mediation Server. Per informazioni dettagliate su quando usare il bypass multimediale, vedere [pianificazione di un bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) nella sezione pianificazione.

È possibile abilitare e configurare il bypass multimediale dal pannello di controllo di Lync Server.

<div>

## <a name="to-enable-and-configure-media-bypass"></a>Per abilitare e configurare il bypass multimediale

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **globale**.

4.  Nella pagina **globale** fare clic sulla configurazione **globale** . Esiste sempre una sola configurazione ed è sempre denominata globale.

5.  Nel menu **modifica** fare clic su **Visualizza dettagli**.

6.  Nella pagina **Modifica impostazioni globali** fare clic sulla casella di controllo **Abilita esclusione multimediale** .

7.  Selezionare una delle opzioni seguenti:
    
      - **Ignora sempre seleziona**   questa opzione per provare il bypass multimediale in tutte le chiamate. Questa opzione non sarà disponibile se il controllo di ammissione di chiamata (CAC) è abilitato. Se CAC non è abilitato, selezionare questa opzione nelle situazioni seguenti:
        
          - Non è necessario il controllo della larghezza di banda.
        
          - Non c'è bisogno di una configurazione a grana fine per determinare quando deve avvenire il bypass.
        
          - Esiste una connettività completa tra gateway e client.
    
      - **Usare i siti e la configurazione**   dell'area se è abilitato CAC, questa opzione è selezionata per impostazione predefinita e non può essere modificata. Quando questa opzione è selezionata, i siti e le aree di configurazione della rete verranno usati per determinare quando il bypass multimediale è possibile. Se si seleziona questa opzione, è possibile scegliere di abilitare il bypass per i siti non mappati. Fare clic sulla casella **di controllo Abilita esclusione per i siti non mappati** solo se si hanno uno o più siti di grandi dimensioni associati alla stessa area geografica che non hanno vincoli di larghezza di banda, ad esempio un sito centrale di grandi dimensioni, e si hanno anche alcuni siti di succursale associati alla stessa area geografica con vincoli di larghezza di banda. Quando si Abilita l'esclusione per i siti non mappati, la configurazione viene semplificata perché si specificano solo le subnet associate ai siti di succursale e non è necessario specificare tutte le subnet associate a tutti i siti. È consigliabile non selezionare la casella di controllo **Abilita esclusione per i siti non mappati** se è abilitato CAC.

8.  Fare clic su **conferma** per salvare le modifiche.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Disabilitare il bypass multimediale di rete in Lync Server 2013](lync-server-2013-disabling-network-media-bypass.md)  


[Opzioni di bypass multimediale globale in Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Pianificazione del bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

