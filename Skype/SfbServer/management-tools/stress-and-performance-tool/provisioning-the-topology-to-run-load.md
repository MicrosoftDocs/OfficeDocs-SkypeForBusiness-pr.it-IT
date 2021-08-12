---
title: Provisioning della topologia per l'esecuzione del carico in scenari di stress e prestazioni
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
description: Skype for Business Server 2015 le modifiche o il provisioning della topologia per consentire agli utenti di eseguire correttamente lo strumento Stress and Performance.
ms.openlocfilehash: 750a53882344d4a1df357b049fbd1dcbf01c3368fb903552bc5f398761cce66a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54328111"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Provisioning della topologia per l'esecuzione del carico in scenari di stress e prestazioni
 
Skype for Business Server 2015 le modifiche o il provisioning della topologia per consentire agli utenti di eseguire correttamente lo strumento Stress and Performance.
  
A seconda delle impostazioni e della configurazione esistenti per la distribuzione di Skype for Business Server 2015, potrebbe essere necessario apportare alcune modifiche nell'ambiente. Di seguito è riportato un elenco di tali modifiche:
  
1. Impostare il Windows PowerShell di esecuzione su Senza restrizioni. Se non si è certi dell'impostazione corrente, è possibile aprire Skype for Business Server Management Shell ed eseguire questo comando:
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   Se non viene restituito il valore Unrestricted, sarà necessario eseguire la procedura seguente:
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. Per configurare in modo Skype for Business Server, è necessario:
    
    - Acquisire familiarità con la topologia Skype for Business Server 2015, ad esempio nomi di computer, istanze di servizio, nomi di sito e criteri.
    
    - Assegnare alcuni degli utenti creati ai gruppi, ad esempio i gruppi di risposta di Response Group (ad esempio, URI SIP).
    
3. Per eseguire uno script dalla riga di comando, è possibile utilizzare:
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. In genere, dopo aver eseguito uno script da questo pacchetto, le tracce risultanti verranno archiviate in un file nello stesso percorso da cui è stato eseguito lo script. Esiste anche un formato di denominazione, \<scriptname\> $h$m$s.txt. Quindi, se è stato eseguito il ArchivingPolicy.ps1 alle 12.15, si otterrà un file di registro denominato ArchivingPolicy121500.txt.
    
5. Anche se questi esempi sono stati forniti per la configurazione del server, è necessario modificare la configurazione e ripristinarla o ripristinarla al termine dell'esecuzione del test di carico.
    

