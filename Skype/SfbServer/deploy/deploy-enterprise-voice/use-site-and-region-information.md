---
title: Configurare le impostazioni globali di bypass multimediale in Skype for Business Server per l'utilizzo delle informazioni sui siti e sulle aree geografiche
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Configurare il bypass multimediale da utilizzare solo per alcuni siti e aree geografiche in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 58fd4fca90029a8a5f4cd82c6a9616ae66e69cd0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830586"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>Configurare le impostazioni globali di bypass multimediale in Skype for Business Server per l'utilizzo delle informazioni sui siti e sulle aree geografiche
 
Configurare il bypass multimediale da utilizzare solo per alcuni siti e aree geografiche in Skype for Business Server VoIP aziendale. 
  
 Se si utilizzano i passaggi descritti in questo argomento per configurare le impostazioni globali per il bypass multimediale, si presuppone che non si disponga di una buona connettività tra tutti gli endpoint di Skype for business e qualsiasi peer per il quale è stato configurato il bypass multimediale sulla connessione trunk.
  
> [!NOTE]
> Le informazioni relative alle aree di rete e ai siti di rete vengono condivise tra le caratteristiche di VoIP aziendale avanzate del controllo di ammissione di chiamata e del bypass multimediale, quando entrambi sono abilitati. Se il controllo di ammissione di chiamata è già configurato, non sarà pertanto necessario eseguire la procedura seguente per modificare le informazioni sui siti e sulle aree in modo specifico per il bypass multimediale. Eseguire questa procedura se le aree e i siti di rete non sono stati ancora configurati per il controllo di ammissione di chiamata e si desidera modificare le impostazioni per il bypass multimediale. 
  
Affinché il bypass multimediale funzioni correttamente, è necessario che esista una coerenza tra un sito come definito in Generatore di topologie e come definito quando si configurano le aree di rete e i siti di rete. Ad esempio, se si dispone di un sito di succursale definito in Generatore di topologie per la distribuzione di un solo gateway PSTN, il sito di succursale deve essere configurato con un criterio VoIP aziendale che consenta agli utenti di siti di succursale di fare in modo che le chiamate PSTN vengano instradate attraverso il gateway PSTN nel sito di succursale.
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>Per configurare le informazioni relative ai siti e alle aree per il bypass multimediale

1. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.  
    
2. Nella barra di spostamento sinistra fare clic su **Configurazione di rete**.
    
3. Fare doppio clic sulla configurazione **Globale** nella tabella.
    
4. Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita bypass multimediale**.
    
5. Fare clic su **Utilizza configurazione siti e aree**.
    
6. Se necessario, selezionare la casella di controllo **Abilita bypass per siti non mappati**.
    
    > [!NOTE]
    > Selezionare questa casella di controllo solo se alla stessa area sono associati uno o più siti di grandi dimensioni senza vincoli di larghezza di banda, ad esempio un grande sito centrale, ma anche siti di succursale con vincoli di larghezza di banda. Quando si abilita il bypass per i siti non mappati, la configurazione viene snellita perché è necessario specificare esclusivamente le subnet associate ai siti di succursale anziché tutte le subnet associate a tutti i siti. È consigliabile non selezionare questa casella di controllo se il controllo di ammissione di chiamata è abilitato. 
  
7. Fare clic su **Commit**.
    
Successivamente, aggiungere le subnet al sito di rete, come descritto in [associare una subnet a un sito di rete](deploy-network.md#BKMK_AssociateSubnets). Dopo aver associato tutte le subnet ai siti di rete, la distribuzione del bypass multimediale può considerarsi completata.
> [!IMPORTANT]
> Se non sono stati ancora creati i siti e le aree di rete, è necessario crearli prima di poter proseguire con la distribuzione del bypass multimediale. Per informazioni dettagliate, vedere [deploy Network Regions, sites and Subnets in Skype for business](deploy-network.md). 
  
## <a name="see-also"></a>Vedere anche

[Associare una subnet a un sito di rete](deploy-network.md#BKMK_AssociateSubnets)

