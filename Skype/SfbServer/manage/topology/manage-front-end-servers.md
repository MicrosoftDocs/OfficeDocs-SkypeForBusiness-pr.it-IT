---
title: Gestire front end server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Riepilogo: informazioni su come aggiungere, rimuovere, applicare la patch o aggiornare Front End Server in Skype for Business Server.'
ms.openlocfilehash: 3d2298711e707ed897b26939fd383dbedcfb3957
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098414"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Gestire front end server in Skype for Business Server
 
In questo articolo viene illustrato come aggiungere o rimuovere front end server e come applicare gli aggiornamenti o le patch ai Front End Server.

  > [!NOTE]
> Skype for Business Server 2019 non supporta pool Enterprise Edition front end con due front end server e non consentirà la pubblicazione della topologia in tale scenario.

## <a name="add-or-remove-front-end-servers"></a>Aggiungere o rimuovere front end server
  
Quando si aggiunge un Front End Server a un pool oppure si rimuove un Front End Server da un pool, è quindi necessario riavviare il pool. 
  
> [!IMPORTANT]
> Quando si aggiunge o si rimuove un server nel pool della topologia e quindi si pubblica la topologia aggiornata, tutti i server del pool verranno riavviati contemporaneamente. Mentre i server stanno riavviando il pool non è in linea, che interromperà il servizio per gli utenti connessi a tale pool. Per evitare interruzioni del servizio agli utenti, pianificare la pubblicazione della topologia con il nuovo server del pool durante l'orario non di ufficio. 
  
Quando si aggiunge o si rimuove un front end server, è possibile utilizzare la procedura seguente.
  
> [!NOTE]
> Se si aggiungono nuovi server al pool, aggiornare i nuovi server del pool in modo che siano allo stesso livello di aggiornamento cumulativo dei server esistenti nel pool. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Per aggiungere o rimuovere front end server

1. If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. Aprire Generatore di topologie e aggiungere o rimuovere i server necessari. 
    
3. Pubblicare la topologia.
    
    > [!IMPORTANT]
    > Quando si aggiunge o si rimuove un server nel pool della topologia e quindi si pubblica la topologia aggiornata, tutti i server del pool verranno riavviati contemporaneamente. Mentre i server stanno riavviando il pool non è in linea, che interromperà il servizio per gli utenti connessi a tale pool. Per evitare interruzioni del servizio agli utenti, pianificare la pubblicazione della topologia con il nuovo server del pool durante l'orario non di ufficio. 
  
  > [!NOTE]
> Inoltre, quando si aggiunge o si rimuove un server nel pool, è necessario eseguire la distribuzione guidata di Skype for Business Server su ogni computer aggiunto o rimosso, per ulteriori informazioni, vedere [installare Skype for Business Server nei server nella topologia](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)
  
4. Se il numero di server del pool Front End è stato modificato in uno dei modi seguenti, reimpostare il pool digitando il seguente cmdlet: Reset-CsPoolRegistrarState-ResetType FullReset-PoolFqdn 
    
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

## <a name="patch-or-update-front-end-servers"></a>Patch o aggiornamento di front end server

Quando si esegue il patch dei server in un pool Front End, è possibile farlo un server alla volta. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Per applicare un aggiornamento ai Front End Server in un pool

1. Digitare il cmdlet seguente:
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     Se questo cmdlet visualizza eventuali repliche mancanti, eseguire il seguente cmdlet per recuperare il pool prima di applicare eventuali patch.
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. Sul primo server che si desidera applicare, eseguire il cmdlet seguente:
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    Questo cmdlet sposta tutti i servizi in altri front end server nel pool e utilizza questo server offline.
    
3. Applicare l'aggiornamento o la patch a questo server.
    
4. Nel server aggiornato, eseguire il cmdlet seguente:
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    Il server viene restituito al servizio.
    
5. Ripetere i passaggi 2-4 per ogni server che deve essere aggiornato.
    
