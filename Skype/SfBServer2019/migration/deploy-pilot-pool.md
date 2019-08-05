---
title: Distribuire il pool di piloti
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Uno dei primi passaggi necessari per la migrazione a Skype for Business Server 2019 consiste nel distribuire un pool pilota. Il pool pilota è il punto in cui è possibile testare la coesistenza di Skype for Business Server 2019 con la distribuzione legacy. La coesistenza è uno stato temporaneo che dura fino a quando non si sono spostati tutti gli utenti e i pool in Skype for Business Server 2019.
ms.openlocfilehash: 3642d603b5923a554b8eca41a948125ef25526ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189092"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Distribuire Skype for Business Server 2019 Pilot pool

Uno dei primi passaggi necessari per la migrazione a Skype for Business Server 2019 consiste nel distribuire un pool pilota. Il pool pilota è il punto in cui è possibile testare la coesistenza di Skype for Business Server 2019 con la distribuzione legacy. La coesistenza è uno stato temporaneo che dura fino a quando non si sono spostati tutti gli utenti e i pool in Skype for Business Server 2019. 
  
Quando si distribuisce un pool pilota, si usa la procedura guidata Definisci nuovo pool di front-end. È consigliabile distribuire le stesse funzionalità e i carichi di lavoro nel pool di piloti Skype for Business Server 2019 nel pool legacy. Se si è distribuito server di archiviazione, server di monitoraggio o System Center Operations Manager per l'archiviazione o il monitoraggio dell'ambiente legacy e si vuole continuare l'archiviazione o il monitoraggio durante la migrazione, è necessario distribuire queste funzionalità anche in ambiente pilota. La versione distribuita per archiviare o monitorare l'ambiente legacy non acquisisce i dati nell'ambiente Skype for Business Server 2019. 
  
> [!NOTE]
> La procedura seguente illustra le caratteristiche e le impostazioni da tenere in considerazione nell'ambito del processo di distribuzione del pool pilota globale. Questa sezione evidenzia solo i punti chiave da tenere in considerazione nell'ambito della distribuzione del pool pilota. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Per distribuire un pool pilota di Skype for Business Server 2019

1. Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.
    
2. Espandi l'albero fino a raggiungere i**pool Front End** **di Skype for Business Server 2019** > Enterprise Edition.
    
3. Fare clic con il pulsante destro del mouse su **Enterprise Edition front end** pools e scegliere **nuovo front end pool**.
  
4. Immettere il nome di dominio completo (FQDN) del pool. Quando si definisce il pool pilota, è possibile scegliere di distribuire un pool di front-end Enterprise Edition o un server Standard Edition. Skype for Business Server 2019 non richiede che le caratteristiche del pool pilota corrispondano a quelle distribuite nel pool legacy.
    
    > [!CAUTION]
    > Il nome di dominio completo del pool o del server definito per il pool pilota deve essere univoco. Non può corrispondere al nome del pool legacy attualmente distribuito o di qualsiasi altro server attualmente distribuito. 
  
5. Nella pagina **selezionare le caratteristiche** selezionare le caselle di controllo relative alle caratteristiche desiderate in questo pool di front-end. Ad esempio, se si stanno distribuendo solo le funzionalità di messaggistica istantanea e presenza, è necessario selezionare la casella di controllo conferenza per consentire la messaggistica istantanea a più parti, ma non selezionare il controllo di conferenza telefonica con accesso esterno, VoIP aziendale o ammissione alle chiamate le caselle, perché rappresentano funzionalità di conferenza vocale, video e collaborative. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. Nella pagina **Selezione ruoli server collocati** è consigliabile scegliere di collocare il Mediation Server in Skype for Business Server 2019. Quando si unisce una topologia legacy con Skype for Business Server 2019, è necessario prima di tutto collocare il server Mediation legacy. Dopo l'Unione delle topologie e la configurazione di Skype for Business Server 2019 Mediation Server, è possibile decidere se conservare il Mediation Server collocato o modificarlo in un server autonomo quando si sposta il ruolo di Mediation Server in Skype for Business Server 2019 più avanti nel processo di distribuzione. 
   
7. Nella pagina **associa i ruoli del server con questa pagina del pool Front-End** , durante la distribuzione del pool pilota, *non* scegliere l'opzione **Abilita un pool di bordi da usare per il componente multimediale di questo pool di front-end** . Si tratta di una caratteristica che verrà abilitata e riportata online in una fase successiva della migrazione. Mantieni questa impostazione deselezionata per il momento. 
  
8. Nella pagina **selezionare un server di Office Web Apps** fare clic su **nuovo**e specificare il nome di dominio completo del server applicazioni.
  
9. Nella pagina **Definisci archiviazione di SQL Server Store** , quando si definisce SQL Server Store sia per l'archiviazione che per il monitoraggio di Skype for Business Server, selezionare l'istanza di SQL Server creata in precedenza per Skype for business server 2019. 
  
10. Per pubblicare la topologia, fare clic con il pulsante destro del mouse sul nodo di **Skype for Business Server** e quindi scegliere **Pubblica topologia**.
  
11. Al termine del processo di pubblicazione, fare clic su **fine**.

12. Prima di passare alla sezione successiva denominata "verificare la coesistenza del pool pilota con il pool legacy" è necessario installare il nuovo pool di Pilot di Skype for Business Server appena definito nella topologia pubblicata, seguire le procedure descritte in questo [articolo installare Skype for Server aziendale nei server](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server) della topologia

13. Una volta completato il passaggio precedente, passare alla sezione successiva per verificare la coesistenza del pool pilota con il pool legacy.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

