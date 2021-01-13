---
title: Abilitazione e disabilitazione del bypass multimediale
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Utilizzare le procedure descritte in questo articolo per abilitare o disabilitare il bypass multimediale tramite il pannello di controllo di Skype for Business Server.
ms.openlocfilehash: cb8bb06c0e15d39733e92f26867917bb4f8e6989
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816496"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>Abilitazione e disabilitazione del bypass multimediale in Skype for Business Server

Utilizzare le procedure descritte in questo articolo per abilitare o disabilitare il bypass multimediale tramite il pannello di controllo di Skype for Business Server.

## <a name="enable-network-media-bypass"></a>Abilitare il bypass multimediale di rete 

Le impostazioni di bypass multimediale si applicano a livello globale in una distribuzione di Skype for Business Server. Il bypass multimediale consente alle chiamate di bypassare il Mediation Server. Per informazioni dettagliate sull'utilizzo di bypass multimediale, vedere [Plan for Media Bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

È possibile abilitare e configurare il bypass multimediale dal pannello di controllo di Skype for Business Server.


### <a name="to-enable-and-configure-media-bypass"></a>Per abilitare e configurare il bypass multimediale

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **globale**.

4.  Nella pagina  **Globale** fare clic sulla scheda della configurazione  **Globale**. Esiste sempre una sola configurazione ed è sempre denominata Globale.

5.  Scegliere  **Mostra dettagli** dal menu  **Modifica**.

6.  Nella pagina **Modifica impostazioni globali** fare clic sulla casella di controllo **Abilita bypass multimediale** .

7.  Selezionare una delle opzioni seguenti:
    
      - **Ignora sempre**   Selezionare questa opzione per tentare il bypass multimediale su tutte le chiamate. Questa opzione non sarà disponibile se il controllo di ammissione di chiamata (CAC) è abilitato. Se il servizio di controllo di ammissione non è abilitato, selezionare questa opzione nei casi seguenti:
        
          - Non è necessario il controllo della larghezza di banda.
        
          - Non è necessario disporre di una configurazione fine per determinare quando dovrebbe verificarsi un bypass.
        
          - La connettività tra gateway e client è completa.
    
      - **Utilizzare la configurazione dei siti e delle aree**   geografiche   Se il servizio di controllo di ammissione è abilitato, questa opzione è selezionata per impostazione predefinita e non può essere modificata. Quando questa opzione è selezionata, i siti e le aree di configurazione di rete verranno utilizzati per determinare quando è possibile il bypass multimediale. Se si seleziona questa opzione, è possibile scegliere di abilitare il bypass per i siti non mappati. Fare clic sulla casella di controllo **Abilita bypass per i siti non mappati** solo se si dispone di uno o più siti di grandi dimensioni associati alla stessa area che non dispongono di vincoli di larghezza di banda (ad esempio, un sito centrale di grandi dimensioni) e si dispone anche di alcuni siti di succursale associati alla stessa area in cui sono presenti vincoli di larghezza di banda. Quando si Abilita il bypass per i siti non mappati, la configurazione viene semplificata perché sono state specificate solo le subnet associate ai siti di succursale anziché la necessità di specificare tutte le subnet associate a tutti i siti. Si consiglia di non selezionare la casella **di controllo Abilita bypass per i siti non mappati** se è abilitato CAC.

8.  Fare clic su  **Commit** per salvare le modifiche.


## <a name="disable-network-media-bypass"></a>Disattiva bypass multimediale di rete

Le impostazioni di bypass multimediale si applicano a livello globale in una distribuzione di Skype for Business Server. Il bypass multimediale consente alle chiamate di bypassare il Mediation Server. Per informazioni dettagliate sull'utilizzo di bypass multimediale, vedere [Plan for Media Bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). È possibile disabilitare il bypass multimediale dal pannello di controllo di Skype for Business Server. 


### <a name="to-disable-media-bypass"></a>Per disabilitare il bypass multimediale

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **globale**.

4.  Nella pagina  **Globale** fare clic sulla scheda della configurazione  **Globale**. Esiste sempre una sola configurazione ed è sempre denominata Globale.

5.  Scegliere  **Mostra dettagli** dal menu  **Modifica**.

6.  Nella pagina  **Modifica impostazioni globali** deselezionare la casella di controllo  **Abilita bypass multimediale**.

7.  Fare clic su  **Commit** per salvare le modifiche.

  
