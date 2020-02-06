---
title: Distribuire Edge Server pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Questo argomento evidenzia le impostazioni di configurazione da tenere presenti prima di distribuire il server Edge di Skype for Business Server 2019. I processi di distribuzione e configurazione per Skype for Business Server 2019 sono molto simili a Skype for Business Server 2015. Questa sezione evidenzia solo i punti chiave da tenere in considerazione nell'ambito della distribuzione del pool pilota. Per la procedura dettagliata, vedere distribuzione dell'accesso degli utenti esterni in Skype for Business Server 2019 nella documentazione relativa alla distribuzione, che descrive il processo di distribuzione e fornisce anche informazioni sulla configurazione per l'accesso degli utenti esterni.
ms.openlocfilehash: c2beb22e2cce608b692884ad9b49fef40cb87058
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813654"
---
# <a name="deploy-pilot-edge-server"></a>Distribuire Edge Server pilota

Questo argomento evidenzia le impostazioni di configurazione da tenere presenti prima di distribuire il server Edge di Skype for Business Server 2019. I processi di distribuzione e configurazione per Skype for Business Server 2019 sono molto simili a Skype for Business Server 2015. Questa sezione evidenzia solo i punti chiave da tenere in considerazione nell'ambito della distribuzione del pool pilota. <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
Mentre ci si sposta nella procedura guidata **Definisci nuovo pool Edge** , rivedere le impostazioni di configurazione chiave illustrate nella procedura seguente. Tieni presente che vengono visualizzate solo alcune pagine della procedura guidata **Definisci nuovo pool di Edge** . 
  
### <a name="to-define-an-edge-pool"></a>Per definire un pool di bordi

1. Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.
    
2. Passare al nodo di Skype for Business Server 2019. Fare clic con il pulsante destro del mouse su pool **Edge**e scegliere **nuovo pool di bordi**.
    
     ![Finestra di dialogo Definire il nuovo pool di server perimetrali](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Un pool di Edge può essere un pool di **computer multipli** o un pool di **computer singolo**.
    
     ![Finestra di dialogo Definire l'FQDN del pool di server perimetrali](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. Nella pagina **Seleziona funzionalità** non abilitare la Federazione o la Federazione XMPP. Federazione e Federazione XMPP sono entrambi attualmente instradati attraverso il server perimetrale legacy. Queste caratteristiche verranno configurate in una fase successiva della migrazione. 

  
5. Continuare a completare le pagine della procedura guidata seguenti: **FQDN esterni**, **definire l'indirizzo IP interno**e **definire l'indirizzo IP esterno**.
    
6. Nella pagina **Definisci il server hop successivo** selezionare il Director per l'hop successivo del pool di Edge legacy. 
    
     ![Finestra di dialogo Definire l'hop successivo](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. Nella pagina **Associa pool di mediazione o front-end** non associare un pool a questo pool di Edge in questo momento. Il traffico multimediale esterno è attualmente instradato attraverso il server perimetrale legacy. Questa impostazione verrà configurata in una fase successiva della migrazione. 
    
     ![Finestra di dialogo Associare pool Front End](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. Fare clic su **fine**e quindi **pubblicare** la topologia. 
    
9. Seguire i passaggi della documentazione relativa alla distribuzione per installare i file nel nuovo Edge Server, configurare i certificati e avviare i servizi. 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
È molto importante seguire le linee guida degli argomenti della documentazione relativa alla distribuzione. Questa sezione ha semplicemente fornito alcune indicazioni sulle impostazioni di configurazione durante l'installazione di questi ruoli del server. 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
Ora dovresti avere un server perimetrale legacy distribuito in parallelo con una distribuzione di Skype for Business Server 2019 Edge Server. Verificare che entrambe le distribuzioni vengano eseguite correttamente, i servizi vengano avviati ed è possibile amministrare ogni distribuzione prima di passare alla fase successiva. 
  

