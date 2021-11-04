---
title: Eliminare una raccolta esistente di impostazioni di configurazione di registrazione dei dati in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Riepilogo: informazioni su come rimuovere le impostazioni di configurazione della registrazione dei dati in Skype for Business Server.'
ms.openlocfilehash: b72891493a88a733dfd18761023ba875a3b6bc07
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763685"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Eliminare una raccolta esistente di impostazioni di configurazione di registrazione dei dati in Skype for Business Server
 
**Riepilogo:** Scopri come rimuovere le impostazioni di configurazione della registrazione dei dati in Skype for Business Server.
  
La registrazione dettagli chiamata consente di tenere traccia dell'utilizzo delle sessioni di messaggistica istantanea peer-to-peer, delle chiamate telefoniche VoIP (Voice over Internet Protocol) e delle conferenze telefoniche. Questi dati sull'utilizzo includono informazioni sui chiamanti, sugli utenti chiamati, sulla data della chiamata e sulla durata della conversazione.
  
Quando si installa Skype for Business Server, viene creata automaticamente una singola raccolta globale di impostazioni di configurazione della registrazione dei dati. Gli amministratori hanno inoltre la possibilità di creare raccolte di impostazioni personalizzate da applicare ai siti individuali. Le impostazioni configurate nell'ambito del sito hanno precedenza su quelle configurate nell'ambito globale. Se si eliminano le impostazioni con ambito a livello di sito, la Registrazione dettagli chiamata viene gestita nel sito in base alle impostazioni globali.
  
Tieni presente che puoi anche "eliminare" le impostazioni globali. Tuttavia, le impostazioni globali non vengono effettivamente rimosse. Invece, tutte le proprietà nella raccolta vengono reimpostate sui valori predefiniti. Ad esempio, per impostazione predefinita la rimozione è abilitata in una raccolta delle impostazioni di configurazione di Registrazione dettagli chiamata. Supponiamo di modificare la raccolta globale in modo da disabilitare la rimozione. Se successivamente si eliminano le impostazioni globali, tutte le proprietà verranno reimpostate sui valori predefiniti. In questo caso, ciò significa che l'eliminazione verrà riabilitata.
  
È possibile rimuovere le impostazioni di configurazione della registrazione dei dati utilizzando Skype for Business Server pannello di controllo o il cmdlet [Remove-CsCdrConfiguration.](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>Per rimuovere le impostazioni di configurazione della registrazione dei dati con Skype for Business Server pannello di controllo

1. Nel Skype for Business Server di controllo fare clic su **Monitoraggio e archiviazione.** 
    
2. Nella scheda **Registrazione dettagli chiamata** selezionare la raccolta (o le raccolte) delle impostazioni di Registrazione dettagli chiamata da rimuovere. Per selezionare più raccolte, fare clic sulla prima raccolta, tenere premuto il tasto CTRL e fare clic sulle raccolte aggiuntive.
    
3. Fare clic su **Modifica** e quindi scegliere **Elimina**.
    
4. Nella finestra Skype for Business Server pannello di controllo fare clic su **OK.**
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Rimozione delle impostazioni di configurazione di registrazione dei dati tramite Windows PowerShell cmdlet

È possibile eliminare le impostazioni di configurazione della registrazione dettagli chiamata utilizzando Windows PowerShell e il cmdlet **Remove-CsCdrConfiguration.** È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell remota per connettersi a Skype for Business Server, vedere Amministrazione remota di PowerShell per [Microsoft Lync.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>Per rimuovere una raccolta specificata delle impostazioni di configurazione di Registrazione dettagli chiamata

 Questo comando rimuove le impostazioni di configurazione di Registrazione dettagli chiamata applicate al sito Redmond:
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>Per rimuovere tutte le impostazioni di configurazione di registrazione dei dati applicate all'ambito del sito

 Questo comando rimuove tutte le impostazioni di configurazione di Registrazione dettagli chiamata applicate all'ambito del sito:
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsCdrConfiguration.](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)
  
## <a name="see-also"></a>Vedere anche

[Eliminare manualmente i database di registrazione dettagli chiamata e qualità dell'esperienza in Skype for Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)