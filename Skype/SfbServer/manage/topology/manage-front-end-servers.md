---
title: Gestire i Front End Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Riepilogo: informazioni su come aggiungere, rimuovere, applicare patch o aggiornare Front End Server in Skype for Business Server.'
ms.openlocfilehash: b091f1fd74cfd2c3d93ee14e9ea6f1b584ec4111443b99f881786e94e038d8b2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54290304"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Gestire i Front End Server in Skype for Business Server
 
In questo articolo viene illustrato come aggiungere o rimuovere Front End Server e come applicare aggiornamenti o patch ai Front End Server.

  > [!NOTE]
> Skype for Business Server 2019 non supporta edizione Enterprise pool Front End con due Front End Server e non consente la pubblicazione della topologia in tale scenario.

## <a name="add-or-remove-front-end-servers"></a>Aggiungere o rimuovere Front End Server
  
Quando si aggiunge un Front End Server a un pool oppure si rimuove un Front End Server da un pool, è quindi necessario riavviare il pool. 
  
> [!IMPORTANT]
> Quando si aggiunge o si rimuove un server al pool nella topologia e quindi si pubblica la topologia aggiornata, tutti i server del pool verranno riavviati contemporaneamente. Mentre i server stanno riavviando il pool è offline, il servizio verrà interrotto per gli utenti connessi a tale pool. Per evitare interruzioni del servizio per gli utenti, pianificare la pubblicazione della topologia con il nuovo server nel pool durante l'orario non di ufficio. 
  
È possibile utilizzare la procedura seguente quando si aggiunge o si rimuove un Front End Server.
  
> [!NOTE]
> Se si aggiungono nuovi server al pool, aggiornare i nuovi server del pool in modo che siano allo stesso livello di aggiornamento cumulativo dei server esistenti nel pool. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Per aggiungere o rimuovere Front End Server

1. Se si desidera rimuovere uno o più Front End Server, innanzitutto interrompere le nuove connessioni a questi server. A tale scopo, è possibile utilizzare il cmdlet seguente:
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. Aprire Generatore di topologie e aggiungere o rimuovere i server necessari. 
    
3. Pubblicare la topologia.
    
    > [!IMPORTANT]
    > Quando si aggiunge o si rimuove un server al pool nella topologia e quindi si pubblica la topologia aggiornata, tutti i server del pool verranno riavviati contemporaneamente. Mentre i server stanno riavviando il pool è offline, il servizio verrà interrotto per gli utenti connessi a tale pool. Per evitare interruzioni del servizio per gli utenti, pianificare la pubblicazione della topologia con il nuovo server nel pool durante l'orario non di ufficio. 
  
  > [!NOTE]
> Inoltre, quando si aggiunge o si rimuove un server al pool, è necessario eseguire la Distribuzione guidata di Skype for Business Server in ogni computer aggiunto o rimosso, per ulteriori informazioni, vedere [Install Skype for Business Server on servers in the topology](../../deploy/install/install-skype-for-business-server.md)
  
4. Se il numero di server nel pool Front End è stato modificato in uno dei modi seguenti, reimpostare il pool digitando il cmdlet seguente: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 a qualsiasi
    
     - Da uno a 2
    
     - 3 a qualsiasi
    
     - Da uno a 3
    
5. Riavviare il pool digitando il cmdlet seguente
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>Patch o aggiornamento dei Front End Server

Quando si esegue la patch dei server in un pool Front End, si esegue questa operazione un server alla volta. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Per applicare un aggiornamento ai Front End Server in un pool

1. Digitare il cmdlet seguente:
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     Se questo cmdlet mostra eventuali repliche mancanti, eseguire il cmdlet seguente per ripristinare il pool prima di applicare eventuali patch.
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. Nel primo server che si desidera applicare la patch, eseguire il cmdlet seguente:
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    Questo cmdlet sposta tutti i servizi in altri Front End Server del pool e porta il server offline.
    
3. Applicare l'aggiornamento o la patch a questo server.
    
4. Nel server aggiornato eseguire il cmdlet seguente:
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    Il server viene restituito al servizio.
    
5. Ripetere i passaggi da 2 a 4 per ogni server che deve essere aggiornato.
