---
title: Provisioning della topologia per l'esecuzione del caricamento in scenari di stress e prestazioni
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: La topologia di Skype for Business Server 2015 cambia o provisioning per consentire agli utenti di eseguire correttamente lo strumento stress e prestazioni.
ms.openlocfilehash: 2156616fac98d1e6fad08d2036f4bc2def3e98b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816165"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Provisioning della topologia per l'esecuzione del caricamento in scenari di stress e prestazioni
 
La topologia di Skype for Business Server 2015 cambia o provisioning per consentire agli utenti di eseguire correttamente lo strumento stress e prestazioni.
  
A seconda delle impostazioni e della configurazione esistenti per la distribuzione di Skype for Business Server 2015, potrebbe essere necessario apportare alcune modifiche all'ambiente. Di seguito è riportato un elenco di queste modifiche:
  
1. Impostare i criteri di esecuzione di Windows PowerShell su senza restrizioni. Se non si è sicuri di cosa sia impostato al momento, è possibile aprire Skype for Business Server Management Shell ed eseguire questo comando:
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   Se il valore Unrestricted non viene restituito, sarà necessario eseguire il successivo:
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. Per configurare efficacemente Skype for Business Server, è necessario:
    
    - Acquisire familiarità con la topologia di Skype for Business Server 2015, ad esempio nomi di computer, istanze del servizio, nomi dei siti e criteri.
    
    - Assegna alcuni degli utenti creati ai gruppi, ad esempio i gruppi di risposta alla ricerca di Response Group, come gli URI SIP.
    
3. Per eseguire uno script da riga di comando, è possibile usare:
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. In genere, dopo aver eseguito uno script da questo pacchetto, le tracce risultanti verranno archiviate in un file nello stesso percorso da cui è stato eseguito lo script. Esiste anche un formato di denominazione, \<scriptname\>$h $ m $ s. txt. Quindi, se è stato eseguito il ArchivingPolicy. ps1 alle 12:15 PM, viene visualizzato un file di log denominato ArchivingPolicy121500. txt.
    
5. Anche se sono stati forniti questi esempi per la configurazione del server, è necessario modificare la configurazione e ripristinare o eseguire il rollback dopo aver completato l'esecuzione del test di carico.
    

