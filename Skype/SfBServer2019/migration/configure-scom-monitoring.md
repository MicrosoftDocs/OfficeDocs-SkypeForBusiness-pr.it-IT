---
title: Configurare il monitoraggio di SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dopo aver eseguito la migrazione a Microsoft Skype for Business Server 2019, è necessario completare alcune attività per configurare Skype for Business Server 2019 per l'utilizzo con System Center Operations Manager.
ms.openlocfilehash: 141154a8bd678f15fcc919b2dd70a50ca9d4dcca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190025"
---
# <a name="configure-scom-monitoring"></a>Configurare il monitoraggio di SCOM

Dopo aver eseguito la migrazione a Skype for Business Server 2019, è necessario completare alcune attività per configurare Skype for Business Server 2019 per l'utilizzo con System Center Operations Manager.
  
- Applicare gli aggiornamenti a un server scelto per gestire la logica di individuazione centrale.
    
- Aggiornare la chiave del registro di sistema del server di individuazione centrale.
    
- Configurare il server di gestione di System Center Operations Manager principale per eseguire l'override del nodo di individuazione centrale candidata.
    
Di seguito sono riportate le istruzioni per l'esecuzione di ciascuna di queste attività.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Applicare gli aggiornamenti a un server scelto per gestire la logica di individuazione centrale.

1. Eleggere un server in cui sono installati i file dell'agente di System Center Operations Manager ed è configurato come nodo di individuazione candidata. 
    
2. Applicare gli aggiornamenti al server. Vedere l'argomento [applicare gli aggiornamenti](apply-updates.md).
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Aggiornare la chiave del registro di sistema del server di individuazione centrale.

1. Nel server scelto per gestire la logica di individuazione centrale aprire una finestra di comando di Windows PowerShell. 
    
2. Nella riga di comando digitare quanto segue:
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Ogni volta che si modifica il registro di sistema, potrebbe verificarsi un errore che indica che il comando non è riuscito se la chiave del registro di sistema esiste già. Se si verifica questo problema, è possibile ignorare in modo sicuro l'errore. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Configurare il server di gestione di System Center Operations Manager principale per eseguire l'override del nodo di Watcher individuazione centrale candidato.

1. In un computer in cui è installata la console di System Center Operations Manager, espandere **oggetti Management Pack** e quindi selezionare individuazioni **oggetti**.
    
2. Fare clic su **Cambia ambito**
    
3. Nella pagina **oggetti Management Pack di ambito** selezionare **ls Discovery candidate**.
    
4. Eseguire l'override del **valore effettivo del candidato di individuazione LS** per il nome del server candidato eletto nella procedura precedente. 
    
Per completare le modifiche, riavviare il servizio integrità nel server di gestione radice di System Center Operations Manager.
  

