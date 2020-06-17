---
title: Configurare il monitoraggio di SCOM
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
description: Dopo aver eseguito la migrazione a Microsoft Skype for Business Server 2019, è necessario completare alcune attività per configurare Skype for Business Server 2019 in modo che funzioni con System Center Operations Manager.
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754046"
---
# <a name="configure-scom-monitoring"></a>Configurare il monitoraggio di SCOM

Dopo aver eseguito la migrazione a Skype for Business Server 2019, è necessario completare alcune attività per configurare Skype for Business Server 2019 con System Center Operations Manager.
  
- Applicare gli aggiornamenti a un server scelto per gestire la logica di individuazione centrale.
    
- Aggiornare la chiave del Registro di sistema del server candidato all'individuazione centrale.
    
- Configurare il server di gestione di System Center Operations Manager principale per eseguire l'override del nodo di individuazione centrale candidato.
    
Di seguito sono riportate le istruzioni per l'esecuzione di ognuna di tali attività.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Applicare gli aggiornamenti a un server scelto per gestire la logica di individuazione centrale.

1. Scegliere un server in cui siano installati i file dell'agente System Center Operations Manager e che sia configurato come nodo di individuazione candidato. 
    
2. Applicare gli aggiornamenti a questo server. Per ulteriori informazioni, vedere l'argomento [Apply Updates](apply-updates.md).
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Aggiornare la chiave del Registro di sistema del server candidato all'individuazione centrale.

1. Nel server scelto per gestire la logica di individuazione centrale aprire una finestra di comando di Windows PowerShell. 
    
2. Digitare quanto segue alla riga di comando:
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Configurare il server di gestione di System Center Operations Manager principale per sostituire il nodo Watcher di individuazione centrale candidato.

1. In un computer in cui è stata installata la console System Center Operations Manager espandere **Oggetti Management Pack** e selezionare **Individuazioni oggetti**.
    
2. Fare clic su **Cambia ambito**
    
3. Nella pagina **Crea ambito oggetti Management Pack** selezionare **Candidato individuazione LS**.
    
4. Sostituire il **Valore effettivo candidato individuazione LS** con il nome del server candidato scelto nella procedura precedente. 
    
Per completare le modifiche, riavviare il servizio integrità nel server di gestione radice di System Center Operations Manager.
  

