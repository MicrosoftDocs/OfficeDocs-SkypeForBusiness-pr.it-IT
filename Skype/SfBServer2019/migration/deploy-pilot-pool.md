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
localization_priority: Normal
description: Uno dei primi passaggi necessari per la migrazione a Skype for Business Server 2019 è la distribuzione di un pool pilota. Il pool pilota è il luogo in cui è possibile testare la coesistenza di Skype for Business Server 2019 con la distribuzione legacy. La coesistenza è uno stato temporaneo che dura fino a quando non sono stati spostati tutti gli utenti e i pool in Skype for Business Server 2019.
ms.openlocfilehash: 46d8b6fd6cefa2894f67a1c24732ace01ca65785
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752858"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Distribuire il pool pilota di Skype for Business Server 2019

Uno dei primi passaggi necessari per la migrazione a Skype for Business Server 2019 è la distribuzione di un pool pilota. Il pool pilota è il luogo in cui è possibile testare la coesistenza di Skype for Business Server 2019 con la distribuzione legacy. La coesistenza è uno stato temporaneo che dura fino a quando non sono stati spostati tutti gli utenti e i pool in Skype for Business Server 2019. 
  
Quando si distribuisce un pool pilota, utilizzare la procedura guidata Definisci nuovo pool Front End. È consigliabile distribuire le stesse caratteristiche e i carichi di lavoro nel pool pilota di Skype for Business Server 2019 che è presente nel pool legacy. Se è stato distribuito il server di archiviazione, il Monitoring Server o System Center Operations Manager per l'archiviazione o il monitoraggio dell'ambiente legacy e si desidera continuare l'archiviazione o il monitoraggio durante la migrazione, è necessario distribuire queste funzionalità anche nell'ambiente pilota. La versione distribuita per archiviare o monitorare l'ambiente legacy non catturerà i dati nell'ambiente Skype for Business Server 2019. 
  
> [!NOTE]
> Nella procedura riportata di seguito vengono illustrate le funzionalità e le impostazioni che è necessario considerare come parte del processo complessivo di distribuzione del pool pilota. In questa sezione vengono evidenziati solo i punti chiave di cui è consigliabile tenere conto nell'ambito della distribuzione del pool pilota. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Per distribuire un pool pilota di Skype for Business Server 2019

1. Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.
    
2. Espandere l'albero fino a raggiungere i pool Front End **di Skype for Business Server 2019**  >  **Enterprise Edition**.
    
3. Fare clic con il pulsante destro del mouse su pool **Enterprise Edition front end** e scegliere **nuovo pool Front End**.
  
4. Immettere il nome di dominio completo (FQDN) del pool. Quando si definisce il pool pilota, è possibile scegliere di distribuire un pool Enterprise Edition front end o un server Standard Edition. Skype for Business Server 2019 non richiede che le funzionalità del pool pilota corrispondano a quelle distribuite nel pool legacy.
    
    > [!CAUTION]
    > Il nome di dominio completo del pool o del server definito per il pool pilota deve essere univoco. Non può corrispondere al nome del pool legacy correntemente distribuito o di qualsiasi altro server attualmente distribuito. 
  
5. Nella pagina **Selezionare funzionalità** selezionare le caselle di controllo corrispondenti alle caratteristiche desiderate per il pool Front End. Ad esempio, se si stanno distribuendo solo funzionalità di messaggistica istantanea e presenza, è necessario selezionare la casella di controllo per consentire la messaggistica istantanea a più parti, ma non selezionare le caselle di controllo per le conferenze telefoniche con accesso esterno, VoIP aziendale o di ammissione di chiamata, perché rappresentano le funzionalità di conferenza vocale, video e di collaborazione. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. Nella pagina **Selezione ruoli server collocati** , è consigliabile scegliere di collocare il Mediation Server in Skype for Business Server 2019. Quando si unisce una topologia legacy con Skype for Business Server 2019, è necessario innanzitutto collocare il Mediation Server legacy. Dopo l'Unione delle topologie e la configurazione del Mediation Server di Skype for Business Server 2019, è possibile decidere se mantenere il Mediation Server collocato o modificarlo in un server autonomo quando si sposta il ruolo Mediation Server in Skype for Business Server 2019 in un secondo momento nel processo di distribuzione. 
   
7. Durante la distribuzione del pool pilota nella pagina **associare i ruoli del server con il pool Front End** , *non* selezionare l'opzione **Abilita un pool di Edge da utilizzare per il componente multimediale di questo pool Front End** . Si tratta di una funzionalità che consente di abilitare e portare online in una fase successiva della migrazione. Mantenere questa impostazione deselezionata per il momento. 
  
8. Nella pagina **Selezionare un server Office Web Apps** fare clic su **Nuovo** e specificare l'FQDN del server applicazioni.
  
9. Nella pagina **definire l'archivio SQL Server di archiviazione** , quando si definisce l'archivio SQL Server per l'archiviazione e il monitoraggio di Skype for Business Server, selezionare l'istanza di SQL Server creata in precedenza per Skype for business server 2019. 
  
10. Per pubblicare la topologia, fare clic con il pulsante destro del mouse sul nodo di **Skype for Business Server** e quindi scegliere **Pubblica topologia**.
  
11. Al termine del processo di pubblicazione, fare clic su **Fine**.

12. Prima di passare alla sezione successiva denominata "verificare la coesistenza del pool pilota con il pool legacy" è necessario installare il nuovo pool pilota front end di Skype for Business Server appena definito nella topologia pubblicata, seguire le procedure illustrate in questo [articolo installare Skype for Business Server nei server nella topologia](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)

13. Una volta completato il passaggio precedente, passare alla sezione successiva per verificare la coesistenza del pool pilota con il pool legacy.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

