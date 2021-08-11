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
description: Dopo la migrazione a Microsoft Skype for Business Server 2019, è necessario completare alcune attività per configurare Skype for Business Server 2019 per l'utilizzo con System Center Operations Manager.
ms.openlocfilehash: 477fbd3c405328ffac4aa70a722120d375e95b295bf5a23d19882248d1ece54e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279614"
---
# <a name="configure-scom-monitoring"></a>Configurare il monitoraggio di SCOM

Dopo la migrazione a Skype for Business Server 2019, è necessario completare alcune attività per configurare Skype for Business Server 2019 per l'utilizzo con System Center Operations Manager.
  
- Applicare gli aggiornamenti a un server scelto per gestire la logica di individuazione centrale.
    
- Aggiornare la chiave del Registro di sistema del server candidato all'individuazione centrale.
    
- Configurare il server di gestione System Center Operations Manager in modo che sostituisca il nodo di individuazione centrale candidato.
    
Di seguito sono riportate le istruzioni per l'esecuzione di ognuna di tali attività.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Applicare gli aggiornamenti a un server scelto per gestire la logica di individuazione centrale.

1. Scegliere un server in cui siano installati i file dell'agente System Center Operations Manager e che sia configurato come nodo di individuazione candidato. 
    
2. Applicare gli aggiornamenti a questo server. Vedere l'argomento [Applicare gli aggiornamenti](apply-updates.md).
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Aggiornare la chiave del Registro di sistema del server candidato all'individuazione centrale.

1. Nel server scelto per gestire la logica di individuazione centrale, aprire una finestra Windows PowerShell comandi. 
    
2. Digitare quanto segue alla riga di comando:
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Quando si modifica il Registro di sistema, è possibile che si verifichi un errore dovuto alla mancata riuscita del comando se la chiave del Registro di sistema già esiste. In tal caso, è possibile ignorare l'errore. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Configurare il server di gestione System Center Operations Manager per sostituire il nodo watcher di individuazione centrale candidato.

1. In un computer in cui è stata installata la console System Center Operations Manager espandere **Oggetti Management Pack** e selezionare **Individuazioni oggetti**.
    
2. Fare clic **su Cambia ambito**
    
3. Nella pagina **Crea ambito oggetti Management Pack** selezionare **Candidato individuazione LS**.
    
4. Sostituire il **Valore effettivo candidato individuazione LS** con il nome del server candidato scelto nella procedura precedente. 
    
Per finalizzare le modifiche, riavviare il servizio di integrità nel System Center di gestione radice di Operations Manager.
  

