---
title: Abilitazione e disabilitazione del bypass multimediale
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Usare le procedure descritte in questo articolo per abilitare o disabilitare il bypass multimediale usando il Skype for Business Server Pannello di controllo.
ms.openlocfilehash: 38ec29c6e4b51a4c6898b13c4de0172f55947907
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675338"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>Abilitazione e disabilitazione del bypass multimediale in Skype for Business Server

Usare le procedure descritte in questo articolo per abilitare o disabilitare il bypass multimediale usando il Skype for Business Server Pannello di controllo.

## <a name="enable-network-media-bypass"></a>Abilitare il bypass multimediale di rete 

Le impostazioni di bypass multimediale si applicano a livello globale in una distribuzione Skype for Business Server. Il bypass multimediale consente alle chiamate di ignorare il Mediation Server. Per informazioni dettagliate sull'uso del bypass multimediale, vedere [Pianificare il bypass multimediale](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

È possibile abilitare e configurare il bypass multimediale dal Skype for Business Server Pannello di controllo.


### <a name="to-enable-and-configure-media-bypass"></a>Per abilitare e configurare il bypass multimediale

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL Amministrazione per aprire il Skype for Business Server Pannello di controllo. 

3.  Nella barra di spostamento a sinistra fare clic su **Configurazione di rete** e quindi su **Globale**.

4.  Nella pagina  **Globale** fare clic sulla scheda della configurazione  **Globale**. Esiste sempre una sola configurazione ed è sempre denominata Globale.

5.  Scegliere  **Mostra dettagli** dal menu  **Modifica**.

6.  Nella pagina **Modifica impostazione globale** fare clic sulla casella di controllo **Abilita bypass multimediale** .

7.  Selezionare una delle opzioni seguenti:
    
      - **Ignora sempre**   Selezionare questa opzione per tentare il bypass multimediale in tutte le chiamate. Questa opzione non sarà disponibile se il controllo di ammissione di chiamata è abilitato. Se il controllo di ammissione di ammissione di controllo di ammissione di controllo non è abilitato, selezionare questa opzione nelle situazioni seguenti:
        
          - Non è necessario il controllo della larghezza di banda.
        
          - Non è necessario configurare con granularità fine per determinare quando deve verificarsi il bypass.
        
          - È disponibile la connettività completa tra gateway e client.
    
      - **Usare la configurazione dei siti e dell'area**   Se cac è abilitato, questa opzione viene selezionata per impostazione predefinita e non può essere modificata. Quando questa opzione è selezionata, verranno usati siti e aree di configurazione di rete per determinare quando è possibile ignorare i supporti. Se si seleziona questa opzione, è possibile scegliere di abilitare il bypass per i siti non mappati. Fare clic sulla casella di controllo **Abilita bypass per i siti non mappati** solo se si dispone di uno o più siti di grandi dimensioni associati alla stessa area che non hanno vincoli di larghezza di banda (ad esempio, un sito centrale di grandi dimensioni) e si dispone anche di alcuni siti di succursali associati alla stessa area che hanno vincoli di larghezza di banda. Quando si abilita il bypass per i siti non mappati, la configurazione viene semplificata perché si specificano solo le subnet associate ai siti di succursale anziché specificare tutte le subnet associate a tutti i siti. È consigliabile non selezionare la casella di controllo **Abilita bypass per i siti non mappati** se il controllo di ammissione di controllo è abilitato.

8.  Fare clic su  **Commit** per salvare le modifiche.


## <a name="disable-network-media-bypass"></a>Disabilitare il bypass multimediale di rete

Le impostazioni di bypass multimediale si applicano a livello globale in una distribuzione Skype for Business Server. Il bypass multimediale consente alle chiamate di ignorare il Mediation Server. Per informazioni dettagliate sull'uso del bypass multimediale, vedere [Pianificare il bypass multimediale](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). È possibile disabilitare il bypass multimediale dal Skype for Business Server Pannello di controllo. 


### <a name="to-disable-media-bypass"></a>Per disabilitare il bypass multimediale

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL Amministrazione per aprire il Skype for Business Server Pannello di controllo. 

3.  Nella barra di spostamento a sinistra fare clic su **Configurazione di rete** e quindi su **Globale**.

4.  Nella pagina  **Globale** fare clic sulla scheda della configurazione  **Globale**. Esiste sempre una sola configurazione ed è sempre denominata Globale.

5.  Scegliere  **Mostra dettagli** dal menu  **Modifica**.

6.  Nella pagina  **Modifica impostazioni globali** deselezionare la casella di controllo  **Abilita bypass multimediale**.

7.  Fare clic su  **Commit** per salvare le modifiche.

  
