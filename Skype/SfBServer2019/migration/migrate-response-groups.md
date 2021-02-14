---
title: Eseguire la migrazione di Response Group
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
description: Dopo aver spostato gli utenti nei pool di Skype for Business Server 2019, è possibile eseguire la migrazione dei Response Group. La migrazione dei Response Group include la copia di gruppi di agenti, code, flussi di lavoro, file audio e lo spostamento di oggetti contatto di Response Group dalla distribuzione legacy al pool di Skype for Business Server 2019. Dopo aver eseguito la migrazione dei Response Group legacy, le chiamate ai Response Group vengono gestite dall'applicazione Response Group nel pool di Skype for Business Server 2019. Le chiamate ai Response Group non sono più gestite dal pool legacy.
ms.openlocfilehash: 03b0ffd900b5d7c23dd6ff680d56c0c4db53d8dc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752678"
---
# <a name="migrate-response-groups"></a>Eseguire la migrazione di Response Group

Dopo aver spostato gli utenti nei pool di Skype for Business Server 2019, è possibile eseguire la migrazione dei Response Group. La migrazione dei Response Group include la copia di gruppi di agenti, code, flussi di lavoro, file audio e lo spostamento di oggetti contatto di Response Group dalla distribuzione legacy al pool di Skype for Business Server 2019. Dopo aver eseguito la migrazione dei Response Group legacy, le chiamate ai Response Group vengono gestite dall'applicazione Response Group nel pool di Skype for Business Server 2019. Le chiamate ai Response Group non sono più gestite dal pool legacy.
  
> [!NOTE]
> Sebbene sia possibile eseguire la migrazione dei Response Group prima di spostare tutti gli utenti nel pool di Skype for Business Server 2019, è consigliabile spostare prima tutti gli utenti. In particolare, gli utenti che sono agenti di Response Group non avranno tutte le funzionalità delle nuove funzionalità finché non vengono spostati nel pool di Skype for Business Server 2019. 
  
Prima di eseguire la migrazione dei Response Group, è necessario aver distribuito un pool di Skype for Business Server 2019 che includa l'applicazione Response Group. L'applicazione Response Group viene installata e attivata per impostazione predefinita quando si distribuisce VoIP aziendale. È possibile verificare che l'applicazione Response Group sia installata eseguendo il cmdlet **Get-CsService -ApplicationServer.** 
  
> [!NOTE]
> È possibile creare nuovi Response Group di Skype for Business Server 2019 nel pool di Skype for Business Server 2019 prima di eseguire la migrazione dei Response Group legacy. 
  
Per eseguire la migrazione dei Response Group da un pool legacy a Skype for Business Server 2019, eseguire il cmdlet **Move-CsRgsConfiguration.** 
  
> [!IMPORTANT]
> Il cmdlet di migrazione di Response Group sposta la configurazione di Response Group per l'intero pool. Non è possibile selezionare gruppi, code o flussi di lavoro specifici di cui eseguire la migrazione. 
  
Dopo aver eseguito la migrazione dei Response Group, è necessario utilizzare il Pannello di controllo di Skype for Business Server o i cmdlet di Skype for Business Server Management Shell per verificare che tutti i gruppi di agenti, le code e i flussi di lavoro siano stati spostati correttamente. 
  
Quando si esegue la migrazione dei Response Group, i Response Group legacy non vengono rimossi. Quando si gestiscono Response Group dopo la migrazione utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell, è possibile visualizzare sia i Response Group legacy che i Response Group di Skype for Business Server 2019. È consigliabile applicare gli aggiornamenti solo ai Response Group di Skype for Business Server 2019. I Response Group legacy vengono conservati solo a scopo di rollback. 
  
> [!CAUTION]
> Dopo aver completato la migrazione e creato i nuovi Response Group, il Pannello di controllo di Skype for Business Server e Skype for Business Server Management Shell visualizzano le versioni legacy e Skype for Business Server 2019 di ogni Response Group. Non usare il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell per rimuovere i Response Group legacy. Se ne viene rimosso uno, il Response Group corrispondente creato durante la migrazione smetterà di funzionare. I Response Group legacy verranno rimossi quando si rimuovere le autorizzazioni del pool legacy. 
  
> [!IMPORTANT]
> È consigliabile rimuovere i dati dalla distribuzione precedente solo dopo la rimozione del pool. È inoltre consigliabile esportare i Response Group subito dopo la migrazione. Se un Response Group legacy deve essere rimosso, è possibile ripristinare i Response Group dal backup per eseguire di nuovo i Response Group di Skype for Business Server 2019. 
  
Skype for Business Server 2019 introduce una nuova funzionalità di Response Group denominata **Tipo di flusso di lavoro.** Il **Tipo di flusso di lavoro** può essere **Gestito** o **Non gestito**. Tutti i Response Group vengono migrati con il **Tipo di flusso di lavoro** impostato su **Non gestito** e con un elenco di responsabili vuoto. 
  
Quando si esegue il cmdlet **Move-CsRgsConfiguration**, i gruppi di agenti, le code, i flussi di lavoro e i file audio rimangono nel pool legacy per consentirne il ripristino. Se occorre eseguire il rollback dello stato precedente nel pool legacy, tuttavia, è necessario eseguire il cmdlet **Move-CsApplicationEndpoint** per rispostare gli oggetti contatto nel pool legacy. 
  
La procedura seguente per la migrazione delle configurazioni di Response Group presuppone che si abbia una relazione uno-a-uno tra i pool legacy e i pool di Skype for Business Server 2019. Se si prevede di consolidare o suddividere i pool durante la migrazione e la distribuzione, è necessario pianificare quale pool legacy mappa a quale pool di Skype for Business Server 2019.
  
## <a name="to-migrate-response-group-configurations"></a>Per eseguire la migrazione delle configurazioni di Response Group

1. Accedere al computer con un account membro del gruppo RTCUniversalServerAdmins o con le autorizzazioni e i diritti di amministratore equivalenti.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Microsoft Skype for Business Server 2019** e quindi **Skype for Business Server Management Shell.**
    
3. Correre:
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Ad esempio:
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Dopo aver eseguito la migrazione di Response Group e agenti nel pool di Skype for Business Server 2019, l'URL utilizzato dagli agenti per accedere e disconnettersi è un URL di Skype for Business Server 2019 ed è disponibile dal **menu** Strumenti. Ricordare agli agenti di aggiornare eventuali riferimenti, come segnalibri, al nuovo URL. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>Per verificare la migrazione di Response Group tramite il Pannello di controllo di Skype for Business Server

1. Eseguire l'accesso al computer con un account membro del gruppo RTCUniversalReadOnlyAdmins o come minimo membro del ruolo CsViewOnlyAdministrator.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il Pannello di controllo di Skype for Business Server, vedere Aprire gli strumenti di amministrazione di [Skype for Business Server 2019.](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx) 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. Nel riquadro di spostamento sinistro fare clic su **Response Group**.
    
4. Nella scheda **Flusso di** lavoro verificare che tutti i flussi di lavoro nell'ambiente legacy siano inclusi nell'elenco. 
    
5. Fare clic **sulla scheda** Coda e verificare che tutte le code nell'ambiente legacy siano incluse nell'elenco. 
    
6. Fare clic **sulla scheda** Gruppo e verificare che nell'elenco siano inclusi tutti i gruppi di agenti nell'ambiente legacy. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>Per verificare la migrazione di Response Group tramite Skype for Business Server Management Shell

1. Eseguire l'accesso al computer con un account membro del gruppo RTCUniversalReadOnlyAdmins o come minimo membro del ruolo CsViewOnlyAdministrator.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Microsoft Skype for Business Server 2019** e quindi **Skype for Business Server Management Shell.**
    
    Per informazioni dettagliate sui cmdlet seguenti, eseguire:
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. Correre:
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. Verificare che tutti i gruppi di agenti nell'ambiente legacy siano inclusi nell'elenco.
    
5. Correre:
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. Verificare che tutte le code nell'ambiente legacy siano incluse nell'elenco.
    
7. Correre:
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. Verificare che tutti i flussi di lavoro nell'ambiente legacy siano inclusi nell'elenco.
    

