---
title: Eseguire la migrazione di Response Group
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
description: Dopo lo spostamento degli utenti nei pool di Skype for Business Server 2019, è possibile eseguire la migrazione dei Response Group. La migrazione dei Response Group include i gruppi di agenti di copia, le code, i flussi di lavoro, i file audio e gli oggetti contatto del gruppo di risposta in movimento dalla distribuzione legacy al pool di Skype for Business Server 2019. Dopo aver eseguito la migrazione dei gruppi di risposta legacy, le chiamate ai Response Group vengono gestite dall'applicazione Response gruppo nel pool Skype for Business Server 2019. Le chiamate ai Response Group non sono più gestite dal pool legacy.
ms.openlocfilehash: 2d439462fa103cc16fd7ae70b79364be7d79803a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42016107"
---
# <a name="migrate-response-groups"></a>Eseguire la migrazione di Response Group

Dopo lo spostamento degli utenti nei pool di Skype for Business Server 2019, è possibile eseguire la migrazione dei Response Group. La migrazione dei Response Group include i gruppi di agenti di copia, le code, i flussi di lavoro, i file audio e gli oggetti contatto del gruppo di risposta in movimento dalla distribuzione legacy al pool di Skype for Business Server 2019. Dopo aver eseguito la migrazione dei gruppi di risposta legacy, le chiamate ai Response Group vengono gestite dall'applicazione Response gruppo nel pool Skype for Business Server 2019. Le chiamate ai Response Group non sono più gestite dal pool legacy.
  
> [!NOTE]
> Anche se è possibile eseguire la migrazione dei Response Group prima di spostare tutti gli utenti nel pool di Skype for Business Server 2019, è consigliabile spostare innanzitutto tutti gli utenti. In particolare, gli utenti che sono agenti di Response Group non disporranno di funzionalità complete di nuove funzionalità finché non verranno spostati nel pool di Skype for Business Server 2019. 
  
Prima di eseguire la migrazione dei Response Group, è necessario che sia stato distribuito un pool Skype for Business Server 2019 che includa l'applicazione Response gruppo. L'applicazione Response Group viene installata e attivata per impostazione predefinita quando si distribuisce VoIP aziendale. È possibile verificare che l'applicazione Response Group sia installata eseguendo il cmdlet **Get-CsService-ApplicationServer** . 
  
> [!NOTE]
> È possibile creare nuovi Response Group di Skype for Business Server 2019 nel pool Skype for Business Server 2019 prima di eseguire la migrazione dei Response Group Legacy. 
  
Per eseguire la migrazione dei Response Group da un pool legacy a Skype for Business Server 2019, si esegue il cmdlet **Move-CsRgsConfiguration** . 
  
> [!IMPORTANT]
> Il cmdlet Response Group Migration sposta la configurazione del Response Group per l'intero pool. Non è possibile selezionare gruppi, code o flussi di lavoro specifici di cui eseguire la migrazione. 
  
Dopo aver eseguito la migrazione dei Response Group, è necessario utilizzare il pannello di controllo di Skype for Business Server o i cmdlet di Skype for Business Server Management Shell per verificare che tutti i gruppi di agenti, le code e i flussi di lavoro siano stati spostati correttamente. 
  
Quando si esegue la migrazione dei Response Group, i Response Group Legacy non vengono rimossi. Quando si gestiscono i Response Group dopo la migrazione usando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell, è possibile visualizzare sia i Response Group Legacy che i Response Group di Skype for Business Server 2019. È consigliabile applicare gli aggiornamenti solo ai Response Group di Skype for Business Server 2019. I Response Group Legacy vengono mantenuti solo per scopi di rollback. 
  
> [!CAUTION]
> Dopo che la migrazione è stata completata e i nuovi Response Group sono stati creati, il pannello di controllo di Skype for Business Server e Skype for Business Server Management Shell visualizzeranno le versioni legacy e Skype for Business Server 2019 di ogni risposta gruppo. Non utilizzare il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell per rimuovere i Response Group Legacy. Se si rimuove uno, il Response Group corrispondente che è stato creato durante la migrazione smetterà di funzionare. I Response Group Legacy verranno rimossi quando si rimuove la Commissione del pool legacy. 
  
> [!IMPORTANT]
> È consigliabile rimuovere i dati dalla distribuzione precedente solo dopo la rimozione del pool. È inoltre consigliabile esportare i Response Group subito dopo la migrazione. Se un Response Group Legacy deve essere rimosso, è possibile ripristinare i Response Group dal backup per ottenere i Response Group di Skype for Business Server 2019 in esecuzione di nuovo. 
  
Skype for Business Server 2019 introduce una nuova funzionalità Response Group denominata **tipo di flusso di lavoro**. Il **Tipo di flusso di lavoro** può essere **Gestito** o **Non gestito**. Tutti i Response Group vengono migrati con il **Tipo di flusso di lavoro** impostato su **Non gestito** e con un elenco di responsabili vuoto. 
  
Quando si esegue il cmdlet **Move-CsRgsConfiguration**, i gruppi di agenti, le code, i flussi di lavoro e i file audio rimangono nel pool legacy per consentirne il ripristino. Se occorre eseguire il rollback dello stato precedente nel pool legacy, tuttavia, è necessario eseguire il cmdlet **Move-CsApplicationEndpoint** per rispostare gli oggetti contatto nel pool legacy. 
  
La procedura seguente per eseguire la migrazione delle configurazioni di Response Group presuppone che si disponga di una relazione uno-a-uno tra i pool legacy e i pool di Skype for Business Server 2019. Se si prevede di consolidare o dividere i pool durante la migrazione e la distribuzione, è necessario pianificare il pool legacy in cui si esegue il pool di Skype for Business Server 2019.
  
## <a name="to-migrate-response-group-configurations"></a>Per eseguire la migrazione delle configurazioni di Response Group

1. Accedere al computer con un account membro del gruppo RTCUniversalServerAdmins o con le autorizzazioni e i diritti di amministratore equivalenti.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Eseguire: 
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Ad esempio:
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Dopo aver eseguito la migrazione di Response Group e agenti al pool di Skype for Business Server 2019, l'URL utilizzato dagli agenti per accedere e disconnettersi è un URL di Skype for Business Server 2019 ed è disponibile dal menu **strumenti** . Ricordare agli agenti di aggiornare eventuali riferimenti, come segnalibri, al nuovo URL. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>Per verificare la migrazione di Response Group tramite il pannello di controllo di Skype for Business Server

1. Eseguire l'accesso al computer con un account membro del gruppo RTCUniversalReadOnlyAdmins o come minimo membro del ruolo CsViewOnlyAdministrator.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Skype for Business Server, vedere [aprire gli strumenti di amministrazione di Skype for Business server 2019](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx). 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. Nel riquadro di spostamento sinistro fare clic su **Response Group**.
    
4. Nella scheda **flusso di lavoro** verificare che nell'elenco siano inclusi tutti i flussi di lavoro dell'ambiente legacy. 
    
5. Fare clic sulla scheda **coda** e verificare che nell'elenco siano incluse tutte le code dell'ambiente legacy. 
    
6. Fare clic sulla scheda **gruppo** e verificare che nell'elenco siano inclusi tutti i gruppi di agenti dell'ambiente legacy. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>Per verificare la migrazione di Response Group tramite Skype for Business Server Management Shell

1. Eseguire l'accesso al computer con un account membro del gruppo RTCUniversalReadOnlyAdmins o come minimo membro del ruolo CsViewOnlyAdministrator.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.
    
    Per informazioni dettagliate sui cmdlet seguenti, eseguire:
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. Eseguire: 
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. Verificare che nell'elenco siano inclusi tutti i gruppi di agenti nell'ambiente legacy.
    
5. Eseguire: 
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. Verificare che nell'elenco siano incluse tutte le code dell'ambiente legacy.
    
7. Eseguire: 
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. Verificare che nell'elenco siano inclusi tutti i flussi di lavoro dell'ambiente legacy.
    

