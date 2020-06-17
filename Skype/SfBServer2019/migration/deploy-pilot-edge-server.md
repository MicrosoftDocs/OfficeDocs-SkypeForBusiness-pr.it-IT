---
title: Distribuire Edge Server pilota
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
description: In questo argomento vengono evidenziate le impostazioni di configurazione di cui tenere conto prima di distribuire il server perimetrale di Skype for Business Server 2019. I processi di distribuzione e configurazione per Skype for Business Server 2019 sono molto simili a Skype for Business Server 2015. In questa sezione vengono evidenziati solo i punti chiave di cui è consigliabile tenere conto nell'ambito della distribuzione del pool pilota. Per la procedura dettagliata, vedere Deploying External User Access in Skype for Business Server 2019 nella documentazione relativa alla distribuzione, in cui viene descritto il processo di distribuzione e vengono fornite anche informazioni di configurazione per l'accesso degli utenti esterni.
ms.openlocfilehash: 00c371b917f2649dba9011fbbce6162b153822d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752868"
---
# <a name="deploy-pilot-edge-server"></a>Distribuire Edge Server pilota

In questo argomento vengono evidenziate le impostazioni di configurazione di cui tenere conto prima di distribuire il server perimetrale di Skype for Business Server 2019. I processi di distribuzione e configurazione per Skype for Business Server 2019 sono molto simili a Skype for Business Server 2015. In questa sezione vengono evidenziati solo i punti chiave di cui è consigliabile tenere conto nell'ambito della distribuzione del pool pilota. <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown. 
  
### <a name="to-define-an-edge-pool"></a>Per definire un pool di server perimetrali

1. Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.
    
2. Accedere al nodo Skype for Business Server 2019. Fare clic con il pulsante destro del mouse su **Pool di server perimetrali** e scegliere **Nuovo pool di server perimetrali**.
    
     ![Finestra di dialogo definire il nuovo pool di server perimetrali](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Un pool di server perimetrali può essere un **Pool di più computer** o un **Pool computer singolo**.
    
     ![Finestra di dialogo definire l'FQDN del pool di server perimetrali](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. Nella pagina **Selezionare funzionalità** non abilitare la federazione o la federazione XMPP. La Federazione e la Federazione XMPP sono entrambe instradate al server perimetrale legacy. Queste funzionalità verranno configurate in una fase successiva della migrazione. 

  
5. Continuare a completare le pagine seguenti della procedura guidata: **FQDN esterni**, **definire l'indirizzo IP interno**e **definire l'indirizzo IP esterno**.
    
6. Nella pagina **definire il server dell'hop successivo** selezionare il Director per l'hop successivo del pool perimetrale legacy. 
    
     ![Finestra di dialogo definire l'hop successivo](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. Nella pagina **associa gruppi front-end o pool di Mediation** non associare un pool a questo pool di server perimetrali in questo momento. Il traffico multimediale esterno è attualmente instradato attraverso il server perimetrale legacy. Questa impostazione verrà configurata in una fase successiva della migrazione. 
    
     ![Finestra di dialogo Associa pool Front End](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. Fare clic su **fine**e quindi **pubblicare** la topologia. 
    
9. Attenersi alla procedura descritta nella documentazione relativa alla distribuzione per installare i file nel nuovo server perimetrale, configurare i certificati e avviare i servizi. 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
È molto importante seguire le linee guida negli argomenti della documentazione relativa alla distribuzione. In questa sezione vengono fornite solo indicazioni sulle impostazioni di configurazione durante la fase di installazione di questi ruoli server. 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
È ora necessario disporre di un server perimetrale legacy distribuito in parallelo con una distribuzione di server perimetrale di Skype for Business Server 2019. Prima di passare alla fase successiva, verificare che entrambe le distribuzioni funzionino correttamente, che i servizi siano stati avviati e che sia possibile amministrare ogni distribuzione. 
  

