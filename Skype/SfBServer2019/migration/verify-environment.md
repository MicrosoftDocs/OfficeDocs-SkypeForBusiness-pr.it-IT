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
ms.localizationpriority: medium
description: Prima di distribuire Skype for Business Server 2019 in uno stato di coesistenza, è necessario verificare che i servizi legacy siano stati configurati e avviati. È importante identificare i servizi e le funzionalità chiave presenti nell'ambiente legacy prima di distribuire un pool pilota Skype for Business Server 2019. Prima di distribuire Microsoft Skype for Business Server 2019 XMPP in uno stato di coesistenza con una distribuzione XMPP legacy, è necessario verificare che i servizi XMPP legacy siano stati configurati e avviati e identificare il partner federato che supporta la configurazione XMPP legacy.
ms.openlocfilehash: 208b508eb6b2b5c62da51aa6317cde6e2a95bbb7
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727745"
---
# <a name="verify-the-legacy-environment"></a>Verificare l'ambiente legacy

Prima di distribuire Skype for Business Server 2019 in uno stato di coesistenza, è necessario verificare che i servizi legacy siano stati configurati e avviati. È importante identificare i servizi e le funzionalità chiave presenti nell'ambiente legacy prima di distribuire un pool pilota Skype for Business Server 2019. Prima di distribuire Microsoft Skype for Business Server 2019 XMPP in uno stato di coesistenza con una distribuzione XMPP legacy, è necessario verificare che i servizi XMPP legacy siano stati configurati e avviati e identificare il partner federato che supporta la configurazione XMPP legacy. La verifica della distribuzione legacy comporta quanto segue:
  
- Verifica dell'avvio dei servizi legacy
    
- Revisione della topologia e degli utenti
    
- Verifica delle impostazioni di federazione e server perimetrale
    
- Verifica dei servizi XMPP e dei partner federati
    
## <a name="verify-that-legacy-services-are-started"></a>Verificare che i servizi legacy siano avviati

1. Dal Front End Server legacy passare all'applet Strumenti di amministrazione\Servizi.
    
2. Verificare che i servizi seguenti siano in esecuzione nel Front End Server:
    
     ![Elenco dei servizi in esecuzione nel Front End Server.](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Esaminare la topologia legacy nel Skype for Business Server Pannello di controllo

1. Eseguire l'accesso al Front End Server con un account membro del gruppo RTCUniversalServerAdmins oppure membro del ruolo amministrativo CsAdministrator o CsUserAdministrator.
    
2. Apri il Skype for Business Server pannello di controllo.
    
3. Selezionare **Topologia**. Verificare che i vari server della distribuzione legacy siano elencati.
    
     ![Pagina Topologia del Pannello di controllo.](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Esaminare gli utenti legacy nel Skype for Business Server Pannello di controllo

1. Apri il Skype for Business Server pannello di controllo.
    
2. Selezionare **Utenti** e quindi fare clic su **Trova.**
    
3. Verificare che la **colonna Pool di** registrazione punti al pool legacy per ogni utente elencato. 
    
     ![Pannello di controllo che elenca gli utenti.](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Verificare le impostazioni di federazione e server perimetrale legacy

1. Avviare Generatore di topologie.
    
2. Selezionare **Scarica topologia dalla distribuzione esistente**.
    
3. Scegliere un nome di file e salvare la topologia con il tipo di file tbxml predefinito.
    
4. Espandere il nodo installazioni legacy per visualizzare i vari ruoli del server nella distribuzione.
    
5. Selezionare il nodo del sito e verificare che sia impostato un valore per l'assegnazione della route di **federazione** del sito. 
    
     ![Generatore di topologie, route di federazione del sito.](../media/migration_lyncserver_w14_federation.jpg)
  
6. Selezionare il edizione Standard Server o edizione Enterprise pool front-end. Determinare se un pool di server perimetrali è stato configurato per i supporti sotto **Associazioni**. 
    
     ![Generatore di topologie che mostra server e pool.](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Selezionare il pool di server perimetrali e identificare se un pool di hop successivo è configurato sotto **Selezione hop successivo.**
    
     ![Generatore di topologie, Selezione hop successivo.](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Verificare la configurazione del partner federato XMPP legacy

1. Dal server XMPP legacy passare all'applet Strumenti di amministrazione\Servizi.
    
2. Verificare che il servizio Office Communications Server XMPP Gateway sia stato avviato. 
    
     ![Office Servizio gateway XMPP di Communications Server.](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

