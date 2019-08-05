---
title: Attivazione e disattivazione del bypass multimediale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Usare le procedure descritte in questo articolo per abilitare o disabilitare il bypass multimediale tramite il pannello di controllo di Skype for Business Server.
ms.openlocfilehash: acfa963e71f3c3b89d0e79648d00871b1ab44616
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188603"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>Attivazione e disattivazione del bypass multimediale in Skype for Business Server

Usare le procedure descritte in questo articolo per abilitare o disabilitare il bypass multimediale tramite il pannello di controllo di Skype for Business Server.

## <a name="enable-network-media-bypass"></a>Abilitare il bypass multimediale di rete 

Le impostazioni di bypass multimediale si applicano globalmente in una distribuzione di Skype for Business Server. Il bypass multimediale consente alle chiamate di aggirare il Mediation Server. Per informazioni dettagliate su quando usare il bypass multimediale, vedere [pianificare il bypass multimediale](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

È possibile abilitare e configurare il bypass multimediale dal pannello di controllo di Skype for Business Server.


### <a name="to-enable-and-configure-media-bypass"></a>Per abilitare e configurare il bypass multimediale

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **globale**.

4.  Nella pagina **globale** fare clic sulla configurazione **globale** . Esiste sempre una sola configurazione ed è sempre denominata globale.

5.  Nel menu **modifica** fare clic su **Visualizza dettagli**.

6.  Nella pagina **Modifica impostazioni globali** fare clic sulla casella di controllo **Abilita esclusione multimediale** .

7.  Selezionare una delle opzioni seguenti:
    
      - **Ignora sempre seleziona**   questa opzione per provare il bypass multimediale in tutte le chiamate. Questa opzione non sarà disponibile se il controllo di ammissione di chiamata (CAC) è abilitato. Se CAC non è abilitato, selezionare questa opzione nelle situazioni seguenti:
        
          - Non è necessario il controllo della larghezza di banda.
        
          - Non c'è bisogno di una configurazione a grana fine per determinare quando deve avvenire il bypass.
        
          - Esiste una connettività completa tra gateway e client.
    
      - **Usare i siti e la configurazione**   dell'area se è abilitato CAC, questa opzione è selezionata per impostazione predefinita e non può essere modificata. Quando questa opzione è selezionata, i siti e le aree di configurazione della rete verranno usati per determinare quando il bypass multimediale è possibile. Se si seleziona questa opzione, è possibile scegliere di abilitare il bypass per i siti non mappati. Fare clic sulla casella di controllo **Abilita bypass per i siti non mappati** solo se si hanno uno o più siti di grandi dimensioni associati alla stessa area geografica che non hanno vincoli di larghezza di banda, ad esempio un sito centrale di grandi dimensioni, e si hanno anche alcuni siti di succursale associati alla stessa area geografica con vincoli di larghezza di banda. Quando si Abilita l'esclusione per i siti non mappati, la configurazione viene semplificata perché si specificano solo le subnet associate ai siti di succursale e non è necessario specificare tutte le subnet associate a tutti i siti. È consigliabile non selezionare la casella di controllo **Abilita esclusione per i siti non mappati** se è abilitato CAC.

8.  Fare clic su **conferma** per salvare le modifiche.


## <a name="disable-network-media-bypass"></a>Disabilitare il bypass multimediale di rete

Le impostazioni di bypass multimediale si applicano globalmente in una distribuzione di Skype for Business Server. Il bypass multimediale consente alle chiamate di aggirare il Mediation Server. Per informazioni dettagliate su quando usare il bypass multimediale, vedere [pianificare il bypass multimediale](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). È possibile disabilitare il bypass multimediale dal pannello di controllo di Skype for Business Server. 


### <a name="to-disable-media-bypass"></a>Per disabilitare il bypass multimediale

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **globale**.

4.  Nella pagina **globale** fare clic sulla configurazione **globale** . Esiste sempre una sola configurazione ed è sempre denominata globale.

5.  Nel menu **modifica** fare clic su **Visualizza dettagli**.

6.  Nella pagina **Modifica impostazioni globali** deselezionare la casella di controllo **Abilita esclusione multimediale** .

7.  Fare clic su **conferma** per salvare le modifiche.

  
