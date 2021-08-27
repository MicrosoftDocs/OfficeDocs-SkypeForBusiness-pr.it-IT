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
ms.localizationpriority: medium
description: Dopo aver spostato gli utenti in Skype for Business Server 2019, è possibile eseguire la migrazione dei Response Group. La migrazione di Response Group include la copia di gruppi di agenti, code, flussi di lavoro, file audio e lo spostamento di oggetti contatto di Response Group dalla distribuzione legacy al pool di Skype for Business Server 2019. Dopo aver eseguito la migrazione dei Response Group legacy, le chiamate ai Response Group vengono gestite dall'applicazione Response Group nel pool Skype for Business Server 2019. Le chiamate ai Response Group non sono più gestite dal pool legacy.
ms.openlocfilehash: 96eecb0ad10a900a9d00d26383e149ceec4cbfe8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588028"
---
# <a name="migrate-response-groups"></a>Eseguire la migrazione di Response Group

Dopo aver spostato gli utenti in Skype for Business Server 2019, è possibile eseguire la migrazione dei Response Group. La migrazione di Response Group include la copia di gruppi di agenti, code, flussi di lavoro, file audio e lo spostamento di oggetti contatto di Response Group dalla distribuzione legacy al pool di Skype for Business Server 2019. Dopo aver eseguito la migrazione dei Response Group legacy, le chiamate ai Response Group vengono gestite dall'applicazione Response Group nel pool Skype for Business Server 2019. Le chiamate ai Response Group non sono più gestite dal pool legacy.
  
> [!NOTE]
> Sebbene sia possibile eseguire la migrazione di Response Group prima di spostare tutti gli utenti nel pool Skype for Business Server 2019, è consigliabile spostare prima tutti gli utenti. In particolare, gli utenti che sono agenti di Response Group non avranno tutte le funzionalità delle nuove funzionalità fino a quando non vengono spostati nel pool Skype for Business Server 2019. 
  
Prima di eseguire la migrazione dei Response Group, è necessario aver distribuito un pool Skype for Business Server 2019 che includa l'applicazione Response Group. L'applicazione Response Group viene installata e attivata per impostazione predefinita quando si distribuisce VoIP aziendale. È possibile verificare che l'applicazione Response Group sia installata eseguendo il cmdlet **Get-CsService -ApplicationServer.** 
  
> [!NOTE]
> È possibile creare nuovi Response Group Skype for Business Server 2019 nel pool Skype for Business Server 2019 prima di eseguire la migrazione dei Response Group legacy. 
  
Per eseguire la migrazione di Response Group da un pool legacy Skype for Business Server 2019, eseguire il cmdlet **Move-CsRgsConfiguration.** 
  
> [!IMPORTANT]
> Il cmdlet di migrazione di Response Group sposta la configurazione di Response Group per l'intero pool. Non è possibile selezionare gruppi, code o flussi di lavoro specifici di cui eseguire la migrazione. 
  
Dopo aver eseguito la migrazione dei Response Group, è necessario utilizzare il Pannello di controllo di Skype for Business Server o i cmdlet di Skype for Business Server Management Shell per verificare che tutti i gruppi di agenti, le code e i flussi di lavoro siano stati spostati correttamente. 
  
Quando si esegue la migrazione dei Response Group, i Response Group legacy non vengono rimossi. Quando si gestiscono Response Group dopo la migrazione utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell, è possibile visualizzare sia i Response Group legacy che i Response Group Skype for Business Server 2019. È consigliabile applicare gli aggiornamenti solo ai Response Group Skype for Business Server 2019. I Response Group legacy vengono conservati solo a scopo di rollback. 
  
> [!CAUTION]
> Dopo aver completato la migrazione e aver creato i nuovi Response Group, nel Pannello di controllo di Skype for Business Server e Skype for Business Server Management Shell verranno visualizzate le versioni legacy e Skype for Business Server 2019 di ogni Response Group. Non utilizzare Skype for Business Server pannello di controllo o Skype for Business Server Management Shell per rimuovere i Response Group legacy. Se ne viene rimosso uno, il Response Group corrispondente creato durante la migrazione smetterà di funzionare. I Response Group legacy verranno rimossi quando si decommissiona il pool legacy. 
  
> [!IMPORTANT]
> È consigliabile rimuovere i dati dalla distribuzione precedente solo dopo la rimozione del pool. È inoltre consigliabile esportare i Response Group subito dopo la migrazione. Se un Response Group legacy deve essere rimosso, è possibile ripristinare i Response Group dal backup per Skype for Business Server 2019 response group in esecuzione di nuovo. 
  
Skype for Business Server 2019 introduce una nuova funzionalità di Response Group denominata **Tipo di flusso di lavoro.** Il **Tipo di flusso di lavoro** può essere **Gestito** o **Non gestito**. Tutti i Response Group vengono migrati con il **Tipo di flusso di lavoro** impostato su **Non gestito** e con un elenco di responsabili vuoto. 
  
Quando si esegue il cmdlet **Move-CsRgsConfiguration**, i gruppi di agenti, le code, i flussi di lavoro e i file audio rimangono nel pool legacy per consentirne il ripristino. Se occorre eseguire il rollback dello stato precedente nel pool legacy, tuttavia, è necessario eseguire il cmdlet **Move-CsApplicationEndpoint** per rispostare gli oggetti contatto nel pool legacy. 
  
La procedura seguente per la migrazione delle configurazioni di Response Group presuppone che si abbia una relazione uno-a-uno tra i pool legacy e i pool Skype for Business Server 2019. Se si prevede di consolidare o suddividere i pool durante la migrazione e la distribuzione, è necessario pianificare quale pool legacy esegue il mapping a quale pool Skype for Business Server 2019.
  
## <a name="to-migrate-response-group-configurations"></a>Per eseguire la migrazione delle configurazioni di Response Group

1. Accedere al computer con un account membro del gruppo RTCUniversalServerAdmins o con le autorizzazioni e i diritti di amministratore equivalenti.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Microsoft Skype for Business Server 2019** e quindi fare clic su **Skype for Business Server Management Shell.**
    
3. Eseguire: 
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Ad esempio:
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Dopo aver eseguito la migrazione di Response Group e agenti nel pool di Skype for Business Server 2019, l'URL utilizzato dagli agenti per accedere e disconnettersi è un URL di Skype for Business Server 2019 ed è disponibile dal **menu** Strumenti. Ricordare agli agenti di aggiornare eventuali riferimenti, come segnalibri, al nuovo URL. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>Per verificare la migrazione di Response Group tramite Skype for Business Server pannello di controllo

1. Eseguire l'accesso al computer con un account membro del gruppo RTCUniversalReadOnlyAdmins o come minimo membro del ruolo CsViewOnlyAdministrator.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il Skype for Business Server di controllo, vedere [Open Skype for Business Server 2019 administrative tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools). 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. Nel riquadro di spostamento sinistro fare clic su **Response Group**.
    
4. Nella scheda **Flusso di** lavoro verificare che tutti i flussi di lavoro nell'ambiente legacy siano inclusi nell'elenco. 
    
5. Fare clic **sulla scheda** Coda e verificare che tutte le code nell'ambiente legacy siano incluse nell'elenco. 
    
6. Fare clic **sulla scheda** Gruppo e verificare che tutti i gruppi di agenti nell'ambiente legacy siano inclusi nell'elenco. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>Per verificare la migrazione di Response Group tramite Skype for Business Server Management Shell

1. Eseguire l'accesso al computer con un account membro del gruppo RTCUniversalReadOnlyAdmins o come minimo membro del ruolo CsViewOnlyAdministrator.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Microsoft Skype for Business Server 2019** e quindi fare clic su **Skype for Business Server Management Shell.**
    
    Per informazioni dettagliate sui cmdlet seguenti, eseguire:
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. Eseguire: 
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. Verificare che tutti i gruppi di agenti nell'ambiente legacy siano inclusi nell'elenco.
    
5. Eseguire: 
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. Verificare che tutte le code nell'ambiente legacy siano incluse nell'elenco.
    
7. Eseguire: 
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. Verificare che tutti i flussi di lavoro nell'ambiente legacy siano inclusi nell'elenco.
