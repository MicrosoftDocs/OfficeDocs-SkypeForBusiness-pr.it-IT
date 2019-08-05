---
title: Verificare l'ambiente legacy
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Prima di distribuire Skype for Business Server 2019 in uno stato di coesistenza, è necessario verificare che i servizi legacy siano stati configurati e avviati. È importante identificare i servizi e le caratteristiche principali presenti nell'ambiente legacy, prima di distribuire un pool pilota di Skype for Business Server 2019. Prima di distribuire Microsoft Skype for Business Server 2019 XMPP in uno stato di coesistenza con una distribuzione XMPP legacy, è necessario verificare che i servizi XMPP legacy siano stati configurati e avviati e identificare il partner federato della configurazione XMPP legacy supporto.
ms.openlocfilehash: 9495c68085f3fc3495d4c2ced05be8b20039eb4e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189062"
---
# <a name="verify-the-legacy-environment"></a>Verificare l'ambiente legacy

Prima di distribuire Skype for Business Server 2019 in uno stato di coesistenza, è necessario verificare che i servizi legacy siano stati configurati e avviati. È importante identificare i servizi e le caratteristiche principali presenti nell'ambiente legacy prima della distribuzione di un pool pilota di Skype for Business Server 2019. Prima di distribuire Microsoft Skype for Business Server 2019 XMPP in uno stato di coesistenza con una distribuzione XMPP legacy, è necessario verificare che i servizi XMPP legacy siano stati configurati e avviati e identificare il partner federativo legacy XMPP la configurazione sta supportando. La verifica della distribuzione legacy comporta le operazioni seguenti:
  
- Verificare che i servizi legacy vengano avviati
    
- Revisione della topologia e degli utenti
    
- Verifica delle impostazioni della Federazione e del server perimetrale
    
- Verificare i servizi XMPP e i partner federati
    
## <a name="verify-that-legacy-services-are-started"></a>Verificare che i servizi legacy siano avviati

1. Dal server front-end legacy passare all'applet Tools\Services amministrativa.
    
2. Verificare che i servizi seguenti siano in uso nel server front-end:
    
     ![Elenco dei servizi in esecuzione nel server Front End](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Esaminare la topologia legacy nel pannello di controllo di Skype for Business Server

1. Accedere al server front-end con un account che sia un membro del gruppo RTCUniversalServerAdmins o un membro del ruolo di amministratore di CsAdministrator o CsUserAdministrator.
    
2. Aprire il pannello di controllo di Skype for Business Server.
    
3. Selezionare **topologia**. Verificare che i vari server della distribuzione legacy siano elencati.
    
     ![Pagina topologia pannello di controllo](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Rivedere gli utenti legacy nel pannello di controllo di Skype for Business Server

1. Aprire il pannello di controllo di Skype for Business Server.
    
2. Selezionare **utenti**e quindi fare clic su **trova**.
    
3. Verificare che la colonna del **pool di registrazione** punti al pool legacy per ogni utente elencato. 
    
     ![Elenco degli utenti del pannello di controllo](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Verificare le impostazioni di Edge e federazioni legacy

1. Avviare Generatore di topologie.
    
2. Selezionare **Scarica topologia dalla distribuzione esistente**.
    
3. Scegliere un nome file e salvare la topologia con il tipo di file default. tbxml.
    
4. Espandere il nodo installazioni legacy per rivelare i vari ruoli del server nella distribuzione.
    
5. Selezionare il nodo del sito e verificare che sia impostato un valore di **assegnazione della route federativo del sito** . 
    
     ![Generatore di topologie - Route federazione sito](../media/migration_lyncserver_w14_federation.jpg)
  
6. Selezionare il pool di front end del server Standard Edition o Enterprise Edition. Determinare se un pool di bordi è stato configurato per elementi multimediali al di sotto delle **associazioni**. 
    
     ![Generatore di topologie con server e pool](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Selezionare il pool di bordi e identificare se un pool di hop successivo è configurato sotto la **selezione dell'hop successivo**.
    
     ![Generatore di topologie - Selezione hop successivo](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Verificare la configurazione legacy del partner federato XMPP

1. Dal server XMPP legacy passare all'applet Tools\Services amministrativa.
    
2. Verificare che il servizio gateway XMPP di Office Communications Server sia stato avviato. 
    
     ![Servizio gateway XMPP di Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

