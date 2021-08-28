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
ms.localizationpriority: medium
description: Utilizzare le procedure descritte in questo articolo per abilitare o disabilitare il bypass multimediale tramite il Pannello Skype for Business Server controllo.
ms.openlocfilehash: 6881b1627cf648cc948b5e8b3564fa3b12caa183
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604817"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>Abilitazione e disabilitazione del bypass multimediale in Skype for Business Server

Utilizzare le procedure descritte in questo articolo per abilitare o disabilitare il bypass multimediale tramite il Pannello Skype for Business Server controllo.

## <a name="enable-network-media-bypass"></a>Abilitare il bypass multimediale di rete 

Le impostazioni di bypass multimediale si applicano a livello globale in una Skype for Business Server distribuzione. Il bypass multimediale consente alle chiamate di ignorare il Mediation Server. Per informazioni dettagliate su quando usare il bypass multimediale, vedi [Pianificare il bypass multimediale.](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)

Puoi abilitare e configurare il bypass multimediale dal Skype for Business Server pannello di controllo.


### <a name="to-enable-and-configure-media-bypass"></a>Per abilitare e configurare il bypass multimediale

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Globale.**

4.  Nella pagina  **Globale** fare clic sulla scheda della configurazione  **Globale**. Esiste sempre una sola configurazione ed è sempre denominata Globale.

5.  Scegliere  **Mostra dettagli** dal menu  **Modifica**.

6.  Nella pagina **Modifica impostazione globale** fare clic sulla casella di controllo Abilita **bypass** multimediale.

7.  Selezionare una delle opzioni seguenti:
    
      - **Ignora sempre**   Selezionare questa opzione per tentare il bypass multimediale su tutte le chiamate. Questa opzione non sarà disponibile se il servizio Controllo di ammissione di chiamata è abilitato. Se il controllo di ammissione di chiamata non è abilitato, selezionare questa opzione nelle situazioni seguenti:
        
          - Non è necessario controllare la larghezza di banda.
        
          - Non è necessaria una configurazione specifica per determinare quando deve verificarsi il bypass.
        
          - Esiste una connettività completa tra gateway e client.
    
      - **Usare la configurazione di siti e aree**   Se il controllo di ammissione di chiamata è abilitato, questa opzione è selezionata per impostazione predefinita e non può essere modificata. Quando questa opzione è selezionata, verranno utilizzati siti e aree di configurazione di rete per determinare quando è possibile il bypass multimediale. Se si seleziona questa opzione, è possibile scegliere di abilitare il bypass per i siti non mappati. Selezionare la casella di controllo Abilita bypass per i siti **non** mappati solo se alla stessa area sono associati uno o più siti di grandi dimensioni, ad esempio un sito centrale di grandi dimensioni, e alcuni siti di succursale sono associati alla stessa area con vincoli di larghezza di banda. Quando si abilita il bypass per i siti non mappati, la configurazione viene semplificata perché si specificano solo le subnet associate ai siti di succursale anziché specificare tutte le subnet associate a tutti i siti. È consigliabile non selezionare la casella di controllo Abilita bypass per i siti **non** mappati se il controllo di ammissione di chiamata è abilitato.

8.  Fare clic su  **Commit** per salvare le modifiche.


## <a name="disable-network-media-bypass"></a>Disabilitare il bypass multimediale di rete

Le impostazioni di bypass multimediale si applicano a livello globale in una Skype for Business Server distribuzione. Il bypass multimediale consente alle chiamate di ignorare il Mediation Server. Per informazioni dettagliate su quando usare il bypass multimediale, vedi [Pianificare il bypass multimediale.](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md) Puoi disabilitare il bypass multimediale dal Skype for Business Server pannello di controllo. 


### <a name="to-disable-media-bypass"></a>Per disabilitare il bypass multimediale

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Globale.**

4.  Nella pagina  **Globale** fare clic sulla scheda della configurazione  **Globale**. Esiste sempre una sola configurazione ed è sempre denominata Globale.

5.  Scegliere  **Mostra dettagli** dal menu  **Modifica**.

6.  Nella pagina  **Modifica impostazioni globali** deselezionare la casella di controllo  **Abilita bypass multimediale**.

7.  Fare clic su  **Commit** per salvare le modifiche.

  
