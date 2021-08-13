---
title: Configurare le impostazioni globali di bypass multimediale in Skype for Business Server utilizzare le informazioni sul sito e sull'area geografica
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
description: Configurare il bypass multimediale da utilizzare solo per determinati siti e aree geografiche Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 38fa42374b4b5dd8c8f304de04c9beeb59f2635d955b2e9ee5afb1fb16de7789
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322338"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>Configurare le impostazioni globali di bypass multimediale in Skype for Business Server utilizzare le informazioni sul sito e sull'area geografica
 
Configurare il bypass multimediale da utilizzare solo per determinati siti e aree geografiche Skype for Business Server VoIP aziendale. 
  
 Se si utilizza la procedura descritta in questo argomento per configurare le impostazioni globali per il bypass multimediale, si presuppone che non sia disponibile una buona connettività tra tutti gli endpoint Skype for Business e qualsiasi peer per cui è stato configurato il bypass multimediale nella connessione trunk.
  
> [!NOTE]
> Le informazioni relative alle aree di rete e ai siti di rete vengono condivise tra le caratteristiche di VoIP aziendale avanzate del controllo di ammissione di chiamata e del bypass multimediale, quando entrambi sono abilitati. Se il controllo di ammissione di chiamata è già configurato, non sarà pertanto necessario eseguire la procedura seguente per modificare le informazioni sui siti e sulle aree in modo specifico per il bypass multimediale. Eseguire questa procedura se le aree e i siti di rete non sono stati ancora configurati per il controllo di ammissione di chiamata e si desidera modificare le impostazioni per il bypass multimediale. 
  
Per il corretto funzionamento del bypass multimediale, è necessario che sia presente una coerenza tra un sito come definito in Generatore di topologie e quello definito quando si configurano aree di rete e siti di rete. Se ad esempio si dispone di un sito di succursale definito in Generatore di topologie come se fosse distribuito solo un gateway PSTN, tale sito di succursale deve essere configurato con un criterio di VoIP aziendale che consenta agli utenti dei siti di succursale di instradare le proprie chiamate PSTN attraverso il gateway PSTN nel sito di succursale.
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>Per configurare le informazioni relative ai siti e alle aree per il bypass multimediale

1. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.  
    
2. Nella barra di spostamento sinistra fare clic su **Configurazione di rete**.
    
3. Fare doppio clic sulla configurazione **Globale** nella tabella.
    
4. Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita bypass multimediale**.
    
5. Fare clic su **Utilizza configurazione siti e aree**.
    
6. Se necessario, selezionare la casella di controllo **Abilita bypass per siti non mappati**.
    
    > [!NOTE]
    > Selezionare questa casella di controllo solo se alla stessa area sono associati uno o più siti di grandi dimensioni senza vincoli di larghezza di banda, ad esempio un grande sito centrale, ma anche siti di succursale con vincoli di larghezza di banda. Quando si abilita il bypass per i siti non mappati, la configurazione viene snellita perché è necessario specificare esclusivamente le subnet associate ai siti di succursale anziché tutte le subnet associate a tutti i siti. È consigliabile non selezionare questa casella di controllo se il controllo di ammissione di chiamata è abilitato. 
  
7. Fare clic su **Commit**.
    
Successivamente, aggiungere subnet al sito di rete, come descritto in [Associare una subnet a un sito di rete.](deploy-network.md#BKMK_AssociateSubnets) Dopo aver associato tutte le subnet ai siti di rete, la distribuzione del bypass multimediale può considerarsi completata.
> [!IMPORTANT]
> Se non sono stati ancora creati i siti e le aree di rete, è necessario crearli prima di poter proseguire con la distribuzione del bypass multimediale. Per informazioni dettagliate, vedere [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md). 
  
## <a name="see-also"></a>Vedere anche

[Associare una subnet a un sito di rete](deploy-network.md#BKMK_AssociateSubnets)

