---
title: Configurare le impostazioni globali di bypass multimediale in Skype for Business Server per l'uso delle informazioni sul sito e sulle aree geografiche
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Configurare il bypass multimediale da usare solo per determinati siti e aree geografiche in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 3a9dc907dd516151e8b6ddd509a43b49c87e3b9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195206"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>Configurare le impostazioni globali di bypass multimediale in Skype for Business Server per l'uso delle informazioni sul sito e sulle aree geografiche
 
Configurare il bypass multimediale da usare solo per determinati siti e aree geografiche in Skype for Business Server VoIP aziendale. 
  
 Se si usano i passaggi descritti in questo argomento per configurare le impostazioni globali per il bypass multimediale, si presume che non si disponga di una buona connettività tra tutti gli endpoint di Skype for business e qualsiasi peer per cui è stato configurato il bypass multimediale nella connessione trunk.
  
> [!NOTE]
> Le informazioni relative all'area geografica e al sito di rete sono condivise tra il controllo di ammissione delle chiamate e l'esclusione delle funzionalità vocali avanzate dell'organizzazione. Pertanto, se è già stato configurato il controllo di ammissione delle chiamate, non è necessario usare la procedura seguente per modificare le informazioni relative al sito e alla regione in modo specifico per il bypass multimediale. Seguire i passaggi descritti in questa procedura se non sono ancora state configurate le aree geografiche e i siti di rete per il controllo dell'ammissione alle chiamate e si vogliono modificare le impostazioni di bypass multimediale. 
  
Per consentire il corretto funzionamento del bypass multimediale, è necessario che la coerenza tra un sito sia definito in Generatore di topologie e che venga definita quando si configurano le aree di rete e i siti di rete. Ad esempio, se si ha un sito di succursale definito in Generatore di topologia con un solo gateway PSTN distribuito, il sito di filiale deve essere configurato con un criterio VoIP aziendale che consente agli utenti del sito succursale di avere le chiamate PSTN instradate attraverso la rete PSTN Gateway nel sito della filiale.
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>Per configurare le informazioni sul sito e sulle aree geografiche per il bypass multimediale

1. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
2. Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.
    
3. Fare doppio clic sulla configurazione **globale** nella tabella.
    
4. Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita esclusione multimediale** .
    
5. Fare clic su **Usa configurazione siti e aree**geografiche.
    
6. Se necessario, selezionare la casella **di controllo Abilita bypass per i siti non mappati** .
    
    > [!NOTE]
    > Selezionare questa casella di controllo solo se si hanno uno o più siti di grandi dimensioni associati alla stessa area geografica che non hanno vincoli di larghezza di banda, ad esempio un sito centrale di grandi dimensioni, ma si hanno anche alcuni siti di succursale associati alla stessa area geografica con larghezza di banda vincoli. Quando si Abilita l'esclusione per i siti non mappati, la configurazione viene semplificata in quanto si specificano solo le subnet associate ai siti di succursale, invece di specificare tutte le subnet associate a tutti i siti. È consigliabile non selezionare questa casella di controllo se il controllo di ammissione di chiamata è abilitato. 
  
7. Fare clic su **Commit**.
    
Aggiungere quindi le subnet al sito di rete, come descritto in [associare una subnet a un sito di rete](deploy-network.md#BKMK_AssociateSubnets). Dopo aver associato tutte le subnet con i siti di rete, la distribuzione di bypass multimediale è completa.
> [!IMPORTANT]
> Se non sono già state create aree di rete e siti di rete, è necessario prima di tutto crearle prima di procedere con la distribuzione di bypass multimediale. Per informazioni dettagliate, vedere [distribuire aree di rete, siti e subnet in Skype for business](deploy-network.md). 
  
## <a name="see-also"></a>Vedere anche

[Associare una subnet a un sito di rete](deploy-network.md#BKMK_AssociateSubnets)

