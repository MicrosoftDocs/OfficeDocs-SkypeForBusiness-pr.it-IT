---
title: Eseguire la migrazione dei gruppi di risposte
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dopo lo spostamento degli utenti nei pool di Skype for Business Server 2019, è possibile eseguire la migrazione dei gruppi di risposta. La migrazione dei gruppi di risposte include la copia di gruppi di agenti, code, flussi di lavoro, file audio e oggetti contatto del gruppo di risposte in spostamento dalla distribuzione legacy al pool di Skype for Business Server 2019. Dopo la migrazione dei gruppi di risposta legacy, le chiamate ai gruppi di risposta vengono gestite dall'applicazione Response Group nel pool di Skype for Business Server 2019. Le chiamate ai gruppi di risposte non vengono più gestite dal pool legacy.
ms.openlocfilehash: b8d49205f4f54ca7c00a9aed0b6ac176c11cd617
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238462"
---
# <a name="migrate-response-groups"></a>Eseguire la migrazione dei gruppi di risposte

Dopo lo spostamento degli utenti nei pool di Skype for Business Server 2019, è possibile eseguire la migrazione dei gruppi di risposta. La migrazione dei gruppi di risposte include la copia di gruppi di agenti, code, flussi di lavoro, file audio e oggetti contatto del gruppo di risposte in spostamento dalla distribuzione legacy al pool di Skype for Business Server 2019. Dopo la migrazione dei gruppi di risposta legacy, le chiamate ai gruppi di risposta vengono gestite dall'applicazione Response Group nel pool di Skype for Business Server 2019. Le chiamate ai gruppi di risposte non vengono più gestite dal pool legacy.
  
> [!NOTE]
> Anche se è possibile eseguire la migrazione di gruppi di risposte prima di spostare tutti gli utenti nel pool di Skype for Business Server 2019, è consigliabile spostare prima tutti gli utenti. In particolare, gli utenti che sono agenti del gruppo di risposta non avranno la piena funzionalità delle nuove caratteristiche finché non verranno spostati nel pool di Skype for Business Server 2019. 
  
Prima di eseguire la migrazione dei Response Groups, è necessario avere implementato un pool di Skype for Business Server 2019 che include l'applicazione Response Group. L'applicazione Response Group viene installata e attivata per impostazione predefinita quando si distribuisce VoIP aziendale. Puoi verificare che l'applicazione Response Group sia installata eseguendo il cmdlet **Get-CsService-ApplicationServer** . 
  
> [!NOTE]
> È possibile creare nuovi gruppi di risposta di Skype for Business Server 2019 nel pool di Skype for Business Server 2019 prima di eseguire la migrazione dei gruppi di risposta legacy. 
  
Per eseguire la migrazione dei gruppi di risposte da un pool legacy a Skype for Business Server 2019, Esegui il cmdlet **Move-CsRgsConfiguration** . 
  
> [!IMPORTANT]
> Il cmdlet di migrazione del gruppo di risposte sposta la configurazione del gruppo di risposte per l'intero pool. Non è possibile selezionare gruppi, code o flussi di lavoro specifici per la migrazione. 
  
Dopo la migrazione dei Response Groups, è necessario usare il pannello di controllo di Skype for Business Server o i cmdlet di Skype for Business Server Management Shell per verificare che tutti i gruppi di agenti, le code e i flussi di lavoro vengano spostati correttamente. 
  
Quando si esegue la migrazione dei gruppi di risposte, i gruppi di risposta legacy non vengono rimossi. Quando si gestiscono i gruppi di risposta dopo la migrazione usando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell, è possibile vedere sia i gruppi di risposta legacy che i gruppi di risposta di Skype for Business Server 2019. Dovresti applicare gli aggiornamenti solo ai gruppi di risposta di Skype for Business Server 2019. I gruppi di risposte legacy vengono conservati solo per scopi di rollback. 
  
> [!CAUTION]
> Dopo aver completato la migrazione e creato i nuovi gruppi di risposta, il pannello di controllo di Skype for Business Server e Skype for Business Server Management Shell visualizzeranno le versioni legacy e Skype for Business Server 2019 di ogni risposta gruppo. Non usare il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell per rimuovere i gruppi di risposta legacy. Se si rimuove uno, il gruppo di risposte corrispondente creato durante la migrazione smetterà di funzionare. I gruppi di risposte legacy verranno rimossi quando si rimuove la Commissione del pool legacy. 
  
> [!IMPORTANT]
> È consigliabile non rimuovere i dati dalla distribuzione precedente fino a quando non si esegue la disattivazione del pool. Inoltre, ti consigliamo vivamente di esportare i Response Group subito dopo la migrazione. Se un gruppo di risposte legacy deve essere rimosso, è possibile ripristinare i gruppi di risposte dal backup per ottenere di nuovo i gruppi di risposte di Skype for Business Server 2019. 
  
Skype for Business Server 2019 introduce una nuova funzionalità di Response Group denominata **tipo di flusso di lavoro**. Il **tipo di flusso di lavoro** può essere **gestito** o **non gestito**. Tutti i gruppi di risposte vengono migrati con il **tipo di flusso di lavoro** impostato su **non gestito** e con un elenco di gestione vuoto. 
  
Quando si esegue il cmdlet **Move-CsRgsConfiguration** , i gruppi di agenti, le code, i flussi di lavoro e i file audio rimangono nel pool legacy per scopi di rollback. Se si ha bisogno di eseguire il rollback al pool legacy, deve comunque essere eseguito il cmdlet **Move-CsApplicationEndpoint** per riportare gli oggetti di contatto nel pool legacy. 
  
La procedura seguente per la migrazione delle configurazioni di Response Group presuppone che si disponga di una relazione uno-a-uno tra i pool legacy e i pool di 2019 di Skype for Business Server. Se si prevede di consolidare o suddividere i pool durante la migrazione e la distribuzione, è necessario pianificare le mappe del pool legacy a cui è associato il pool di Skype for Business Server 2019.
  
## <a name="to-migrate-response-group-configurations"></a>Per eseguire la migrazione delle configurazioni di Response Group

1. Accedere al computer con un account che sia membro del gruppo RTCUniversalServerAdmins o disponga di diritti di amministratore e autorizzazioni equivalenti.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Eseguire
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Ad esempio:
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Dopo la migrazione di gruppi di risposte e agenti al pool di Skype for Business Server 2019, l'URL usato dagli agenti per accedere e disconnettersi è un URL di Skype for Business Server 2019 ed è disponibile nel menu **strumenti** . Ricorda agli agenti di aggiornare tutti i riferimenti, ad esempio i segnalibri, al nuovo URL. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>Per verificare la migrazione di Response Group tramite il pannello di controllo di Skype for Business Server

1. Accedere al computer con un account che è un membro del gruppo RTCUniversalReadOnlyAdmins o è minimamente un membro del ruolo CsViewOnlyAdministrator.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Skype for Business Server, vedere [aprire gli strumenti di amministrazione di Skype for Business server 2019](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx). 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. Nel riquadro di spostamento sinistro fare clic su **Response Groups**.
    
4. Nella scheda **flusso di lavoro** verificare che tutti i flussi di lavoro nell'ambiente legacy siano inclusi nell'elenco. 
    
5. Fare clic sulla scheda **coda** e verificare che tutte le code nell'ambiente legacy siano incluse nell'elenco. 
    
6. Fare clic sulla scheda **gruppo** e verificare che tutti i gruppi di agenti nell'ambiente legacy siano inclusi nell'elenco. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>Per verificare la migrazione dei gruppi di risposte tramite Skype for Business Server Management Shell

1. Accedere al computer con un account che è un membro del gruppo RTCUniversalReadOnlyAdmins o è minimamente un membro del ruolo CsViewOnlyAdministrator.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.
    
    Per informazioni dettagliate sui cmdlet seguenti, eseguire:
    
   ```
   Get-Help <cmdlet name> -Detailed
   ```

3. Eseguire
    
   ```
   Get-CsRgsAgentGroup
   ```

4. Verificare che tutti i gruppi di agenti nell'ambiente legacy siano inclusi nell'elenco.
    
5. Eseguire
    
   ```
   Get-CsRgsQueue
   ```

6. Verificare che tutte le code nell'ambiente legacy siano incluse nell'elenco.
    
7. Eseguire
    
   ```
   Get-CsRgsWorkflow
   ```

8. Verificare che tutti i flussi di lavoro nell'ambiente legacy siano inclusi nell'elenco.
    

