---
title: Distribuire il pool pilota
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
description: Uno dei primi passaggi necessari per la migrazione a Skype for Business Server 2019 è la distribuzione di un pool pilota. Il pool pilota consente di testare la coesistenza di Skype for Business Server 2019 con la distribuzione legacy. La coesistenza è uno stato temporaneo che dura fino a quando non sono stati spostati tutti gli utenti e i pool Skype for Business Server 2019.
ms.openlocfilehash: e69e42e95ce7d13d8da88e91d6f1c266d7449f7b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614990"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Distribuire Skype for Business Server pool pilota 2019

Uno dei primi passaggi necessari per la migrazione a Skype for Business Server 2019 è la distribuzione di un pool pilota. Il pool pilota consente di testare la coesistenza di Skype for Business Server 2019 con la distribuzione legacy. La coesistenza è uno stato temporaneo che dura fino a quando non sono stati spostati tutti gli utenti e i pool Skype for Business Server 2019. 
  
Quando si distribuisce un pool pilota, utilizzare la procedura guidata Definisci nuovo pool Front End. È consigliabile distribuire nel pool pilota Skype for Business Server 2019 le stesse funzionalità e carichi di lavoro presenti nel pool legacy. Se è stato distribuito server di archiviazione, Monitoring Server o System Center Operations Manager per l'archiviazione o il monitoraggio dell'ambiente legacy e si desidera continuare l'archiviazione o il monitoraggio durante la migrazione, è necessario distribuire anche queste funzionalità nell'ambiente pilota. La versione distribuita per archiviare o monitorare l'ambiente legacy non acquisisce i dati nell'Skype for Business Server 2019. 
  
> [!NOTE]
> Nella procedura riportata di seguito vengono illustrate le funzionalità e le impostazioni che è necessario considerare come parte del processo complessivo di distribuzione del pool pilota. In questa sezione vengono evidenziati solo i punti chiave di cui è consigliabile tenere conto nell'ambito della distribuzione del pool pilota. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Per distribuire un pool pilota Skype for Business Server 2019

1. Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.
    
2. Espandere l'albero fino a raggiungere **Skype for Business Server 2019**  >  **edizione Enterprise pool Front End.**
    
3. Fare clic con il **edizione Enterprise pool Front End** e scegliere Nuovo pool Front **End.**
  
4. Immettere il nome di dominio completo (FQDN) del pool. Quando si definisce il pool pilota, è possibile scegliere di distribuire un pool Front End edizione Enterprise o un server edizione Standard server. Skype for Business Server 2019 non richiede che le funzionalità del pool pilota corrispondano a quanto distribuito nel pool legacy.
    
    > [!CAUTION]
    > L'FQDN del pool o del server definito per il pool pilota deve essere univoco. Non può corrispondere al nome del pool legacy attualmente distribuito o di altri server attualmente distribuiti. 
  
5. Nella pagina **Selezionare funzionalità** selezionare le caselle di controllo corrispondenti alle caratteristiche desiderate per il pool Front End. Ad esempio, se si distribuiscono solo funzionalità di messaggistica istantanea e presenza, è necessario selezionare la casella di controllo Conferenza per consentire la messaggistica istantanea a più parti, ma non selezionare le caselle di controllo Servizi di conferenza telefonica con accesso esterno (PSTN), VoIP aziendale o Controllo di ammissione di chiamata, perché rappresentano le funzionalità di conferenza vocale, video e di collaborazione. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. Nella pagina **Selezione ruoli server collocati** è consigliabile scegliere di collocare il Mediation Server Skype for Business Server 2019. Quando si unisce una topologia legacy con Skype for Business Server 2019, è necessario collocare prima il Mediation Server legacy. Dopo aver unito le topologie e aver configurato il Mediation Server Skype for Business Server 2019, è possibile decidere se mantenere il Mediation Server collocato o modificarlo in un server autonomo quando si sposta il ruolo Mediation Server Skype for Business Server 2019 più avanti nel processo di distribuzione. 
   
7. Nella pagina Associa ruoli server a questo **pool Front End,** durante la distribuzione del pool *pilota,* non selezionare l'opzione Abilita un pool di server perimetrali che deve essere utilizzato dal componente multimediale di questo pool **Front End.** Si tratta di una funzionalità che verrà abilitata e portare online in una fase successiva della migrazione. Mantenere questa impostazione deselezionata per il momento. 
  
8. Nella pagina **Selezionare un server Office Web Apps** fare clic su **Nuovo** e specificare l'FQDN del server applicazioni.
  
9. Nella pagina Definire **l'archivio SQL Server** archiviazione, quando si definisce l'archivio SQL Server sia per l'archiviazione Skype for Business Server che per il monitoraggio, selezionare l'istanza di SQL Server creata in precedenza per Skype for Business Server 2019. 
  
10. Per pubblicare la topologia, fare clic con il pulsante destro **del mouse** sul nodo Skype for Business Server e quindi scegliere **Pubblica topologia**.
  
11. Al termine del processo di pubblicazione, fare clic su **Fine**.

12. Prima di passare alla sezione successiva denominata "Verificare la coesistenza del pool pilota con il pool legacy", è necessario installare il nuovo pool pilota Front End Skype for Business Server appena definito nella topologia pubblicata, seguire le procedure descritte qui Installare Skype for Business Server nei server della [topologia](../../SfbServer/deploy/install/install-skype-for-business-server.md)

13. Al termine del passaggio precedente, passare alla sezione successiva in Verificare la coesistenza del pool pilota con il pool legacy.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
