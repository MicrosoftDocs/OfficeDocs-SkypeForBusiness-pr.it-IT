---
title: Verificare l'ambiente legacy
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Prima di distribuire Skype for Business Server 2019 in uno stato di coesistenza, è necessario verificare che i servizi legacy siano stati configurati e avviati. È importante identificare i servizi e le funzionalità principali presenti nell'ambiente legacy, prima di distribuire un pool pilota di Skype for Business Server 2019. Prima di distribuire Microsoft Skype for Business Server 2019 XMPP in uno stato di coesistenza con una distribuzione XMPP legacy, è necessario verificare che i servizi XMPP legacy siano stati configurati e avviati e identificare il partner federato che la configurazione di XMPP legacy supporta.
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751678"
---
# <a name="verify-the-legacy-environment"></a>Verificare l'ambiente legacy

Prima di distribuire Skype for Business Server 2019 in uno stato di coesistenza, è necessario verificare che i servizi legacy siano stati configurati e avviati. È importante identificare i servizi e le funzionalità principali presenti nell'ambiente legacy prima di distribuire un pool pilota di Skype for Business Server 2019. Prima di distribuire Microsoft Skype for Business Server 2019 XMPP in uno stato di coesistenza con una distribuzione XMPP legacy, è necessario verificare che i servizi XMPP legacy siano stati configurati e avviati e identificare il partner federato che la configurazione di XMPP legacy supporta. La verifica della distribuzione legacy comporta quanto segue:
  
- Verifica dell'avvio dei servizi legacy
    
- Revisione della topologia e degli utenti
    
- Verifica delle impostazioni di Federazione e server perimetrali
    
- Verifica di servizi XMPP e partner federati
    
## <a name="verify-that-legacy-services-are-started"></a>Verificare che i servizi legacy siano stati avviati

1. Dal front end server legacy passare all'applet Amministrazione\servizi. amministrativa.
    
2. Verificare che i servizi seguenti siano in esecuzione nel Front End Server:
    
     ![Elenco dei servizi in esecuzione nel front end server](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Esaminare la topologia legacy nel pannello di controllo di Skype for Business Server

1. Eseguire l'accesso al Front End Server con un account membro del gruppo RTCUniversalServerAdmins oppure membro del ruolo amministrativo CsAdministrator o CsUserAdministrator.
    
2. Aprire il pannello di controllo di Skype for Business Server.
    
3. Selezionare **Topologia**. Verificare che siano elencati i vari server della distribuzione legacy.
    
     ![Pagina della topologia del pannello di controllo](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Esaminare gli utenti legacy nel pannello di controllo di Skype for Business Server

1. Aprire il pannello di controllo di Skype for Business Server.
    
2. Selezionare **utenti**e quindi fare clic su **trova**.
    
3. Verificare che la colonna **pool di registrazione** punti al pool legacy per ogni utente elencato. 
    
     ![Elenco degli utenti del pannello di controllo](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Verificare le impostazioni del server perimetrale e federativo legacy

1. Avviare Generatore di topologie.
    
2. Selezionare **Scarica topologia dalla distribuzione esistente**.
    
3. Scegliere un nome di file e salvare la topologia con il tipo di file default. tbxml.
    
4. Espandere il nodo installazioni legacy per rivelare i diversi ruoli del server nella distribuzione.
    
5. Selezionare il nodo del sito e verificare che sia impostato un valore **Assegnazione route federazione sito** . 
    
     ![Generatore di topologie, route di Federazione del sito](../media/migration_lyncserver_w14_federation.jpg)
  
6. Selezionare il server Standard Edition o il pool Enterprise Edition front end. Determinare se un pool di server perimetrali è stato configurato per il supporto sottostante alle **associazioni**. 
    
     ![Generatore di topologie che Mostra server e pool](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Selezionare il pool di server perimetrali e identificare se un pool di hop successivo è configurato al di sotto della **selezione dell'hop successivo**.
    
     ![Generatore di topologie, selezione dell'hop successivo](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Verificare la configurazione del partner federato XMPP legacy

1. Dal server XMPP legacy passare all'applet Strumenti di amministrazione\Servizi.
    
2. Verificare che il servizio Office Communications Server XMPP Gateway sia stato avviato. 
    
     ![Servizio gateway XMPP di Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

