---
title: Gestire i server front-end in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Riepilogo: informazioni su come aggiungere, rimuovere, patch o aggiornare i server front-end in Skype for Business Server.'
ms.openlocfilehash: 3689b869ba715f431ebcf0b537b4106a66177c62
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991531"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Gestire i server front-end in Skype for Business Server
 
Questo articolo illustra come aggiungere o rimuovere front-end server e come applicare gli aggiornamenti o le patch ai server front-end.

## <a name="add-or-remove-front-end-servers"></a>Aggiungere o rimuovere server front-end
  
Quando si aggiunge un server front-end a un pool o si rimuove un server front-end da un pool, è necessario riavviare il pool. 
  
> [!IMPORTANT]
> Quando si aggiunge o si rimuove un server nel pool della topologia e quindi si pubblica la topologia aggiornata, tutti i server del pool verranno riavviati simultaneamente. Mentre i server riavviano il pool è offline, il servizio verrà interrotto per gli utenti connessi al pool. Per impedire l'interruzione del servizio agli utenti, pianificare la pubblicazione della topologia con il nuovo server nel pool durante le ore non lavorative. 
  
Quando si aggiunge o si rimuove un server front-end, è possibile usare la procedura seguente.
  
> [!NOTE]
> Se si aggiungono nuovi server al pool, aggiornare i nuovi server del pool in modo che si trovino nello stesso livello di aggiornamento cumulativo dei server esistenti nel pool. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Per aggiungere o rimuovere i server front-end

1. Se si stanno rimuovendo i server front-end, arrestare prima le nuove connessioni a tali server. A questo scopo, puoi usare il cmdlet seguente:
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. Aprire Generatore di topologia e aggiungere o rimuovere i server necessari. 
    
3. Pubblicare la topologia.
    
    > [!IMPORTANT]
    > Quando si aggiunge o si rimuove un server nel pool della topologia e quindi si pubblica la topologia aggiornata, tutti i server del pool verranno riavviati simultaneamente. Mentre i server riavviano il pool è offline, il servizio verrà interrotto per gli utenti connessi al pool. Per impedire l'interruzione del servizio agli utenti, pianificare la pubblicazione della topologia con il nuovo server nel pool durante le ore non lavorative. 
  
  > [!NOTE]
> Inoltre, quando si aggiunge o si rimuove un server nel pool, è necessario eseguire la distribuzione guidata di Skype for Business Server su ogni computer aggiunto o rimosso, per altre informazioni, vedere [installare Skype for Business Server nei server della topologia](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)
  
4. Se il numero di server nel pool Front-End è stato modificato in uno dei modi seguenti, reimpostare il pool con il cmdlet seguente: Reset-CsPoolRegistrarState-ResetType FullReset-PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 a qualsiasi
    
     - Qualsiasi a 2
    
     - 3 a qualsiasi
    
     - Qualsiasi a 3
    
5. Riavviare il pool digitando il cmdlet seguente
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>Patch o aggiornamento dei Front End Server

Quando si esegue la patch dei server in un pool Front-End, è possibile farlo un server alla volta. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Per applicare un aggiornamento ai server front-end in un pool

1. Digitare il cmdlet seguente:
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     Se questo cmdlet Mostra le eventuali repliche mancanti, eseguire il cmdlet seguente per recuperare il pool prima di applicare eventuali patch.
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. Nel primo server che si vuole applicare, eseguire il cmdlet seguente:
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    Questo cmdlet sposta tutti i servizi in altri server front-end nel pool e non è in linea con questo server.
    
3. Applicare l'aggiornamento o la patch al server.
    
4. Nel server aggiornato eseguire il cmdlet seguente:
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    Il server viene restituito al servizio.
    
5. Ripetere i passaggi 2-4 per ogni server che deve essere aggiornato.
    
