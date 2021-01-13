---
title: Provisioning della topologia per l'esecuzione del carico negli scenari di stress e prestazioni
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: La topologia di Skype for Business Server 2015 cambia o provisioning per consentire agli utenti di eseguire correttamente lo strumento stress and performance.
ms.openlocfilehash: 8d422497d11c9e56e4d5b205269a09f96dffc136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814936"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Provisioning della topologia per l'esecuzione del carico negli scenari di stress e prestazioni
 
La topologia di Skype for Business Server 2015 cambia o provisioning per consentire agli utenti di eseguire correttamente lo strumento stress and performance.
  
A seconda delle impostazioni e della configurazione esistenti per la distribuzione di Skype for Business Server 2015, potrebbe essere necessario apportare alcune modifiche nell'ambiente in uso. Di seguito è riportato un elenco delle modifiche seguenti:
  
1. Impostare il criterio di esecuzione di Windows PowerShell su Unrestricted. Se non si è sicuri di cosa è impostato al momento, è possibile aprire Skype for Business Server Management Shell ed eseguire questo comando:
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   Se il valore Unrestricted non viene restituito, è necessario eseguire la seguente operazione:
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. Per configurare in modo efficace Skype for Business Server, è necessario eseguire le operazioni seguenti:
    
    - Familiarizzare con la topologia di Skype for Business Server 2015, ad esempio i nomi di computer, le istanze di servizio, i nomi dei siti e i criteri.
    
    - Assegnare alcuni degli utenti creati ai gruppi, ad esempio i gruppi di risposta di Response Group, come gli URI SIP.
    
3. Per eseguire uno script dalla riga di comando, è possibile utilizzare:
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. In genere, dopo aver eseguito uno script da questo pacchetto, le tracce risultanti verranno archiviate in un file nello stesso percorso da cui è stato eseguito lo script. Esiste anche un formato di denominazione, \<scriptname\> $h $ m $s.txt. Pertanto, se si esegue il ArchivingPolicy.ps1 alle 12:15 PM, si otterrà un file di registro denominato ArchivingPolicy121500.txt.
    
5. Anche se sono stati forniti questi esempi per la configurazione del server, è necessario modificare la configurazione e ripristinarla o eseguirne il rollback dopo aver completato l'esecuzione del test di carico.
    

