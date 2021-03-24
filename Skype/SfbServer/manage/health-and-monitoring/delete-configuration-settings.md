---
title: Eliminare una raccolta esistente di impostazioni di configurazione della registrazione chiamata in Skype for Business Server
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
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Riepilogo: informazioni su come rimuovere le impostazioni di configurazione della registrazione chiamata in Skype for Business Server.'
ms.openlocfilehash: 3ac961df352f26891ece9c69b7d62b37c4c015d6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095310"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Eliminare una raccolta esistente di impostazioni di configurazione della registrazione chiamata in Skype for Business Server
 
**Riepilogo:** Informazioni su come rimuovere le impostazioni di configurazione della registrazione chiamata in Skype for Business Server.
  
La registrazione dettagli chiamata consente di tenere traccia dell'utilizzo delle sessioni di messaggistica istantanea peer-to-peer, delle chiamate telefoniche VoIP (Voice over Internet Protocol) e delle conferenze telefoniche. Questi dati sull'utilizzo includono informazioni sui chiamanti, sugli utenti chiamati, sulla data della chiamata e sulla durata della conversazione.
  
Quando si installa Skype for Business Server, viene creata automaticamente una singola raccolta globale di impostazioni di configurazione della registrazione chiamata. Gli amministratori hanno inoltre la possibilità di creare raccolte di impostazioni personalizzate da applicare ai siti individuali. Le impostazioni configurate nell'ambito del sito hanno precedenza su quelle configurate nell'ambito globale. Se si eliminano le impostazioni con ambito a livello di sito, la Registrazione dettagli chiamata viene gestita nel sito in base alle impostazioni globali.
  
Tieni presente che puoi anche "eliminare" le impostazioni globali. Tuttavia, le impostazioni globali non vengono effettivamente rimosse. Invece, tutte le proprietà nella raccolta vengono reimpostate sui valori predefiniti. Ad esempio, per impostazione predefinita la rimozione è abilitata in una raccolta delle impostazioni di configurazione di Registrazione dettagli chiamata. Supponiamo di modificare la raccolta globale in modo da disabilitare la rimozione. Se successivamente si eliminano le impostazioni globali, tutte le proprietà verranno reimpostate sui valori predefiniti. In questo caso, ciò significa che l'eliminazione verrà riabilitata.
  
È possibile rimuovere le impostazioni di configurazione della registrazione chiamata tramite il Pannello di controllo di Skype for Business Server o il cmdlet [Remove-CsCdrConfiguration.](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>Per rimuovere le impostazioni di configurazione della registrazione chiamata con il Pannello di controllo di Skype for Business Server

1. Nel Pannello di controllo di Skype for Business Server fare clic su **Monitoraggio e archiviazione.** 
    
2. Nella scheda **Registrazione dettagli chiamata** selezionare la raccolta (o le raccolte) delle impostazioni di Registrazione dettagli chiamata da rimuovere. Per selezionare più raccolte, fare clic sulla prima raccolta, tenere premuto il tasto CTRL e fare clic sulle raccolte aggiuntive.
    
3. Fare clic su **Modifica** e quindi scegliere **Elimina**.
    
4. Nella finestra di dialogo Pannello di controllo di Skype for Business Server fare clic su **OK.**
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Rimozione delle impostazioni di configurazione di registrazione dei dati tramite Windows PowerShell cmdlet

È possibile eliminare le impostazioni di configurazione della registrazione dettagli chiamata utilizzando Windows PowerShell e il cmdlet **Remove-CsCdrConfiguration.** È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo di blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Il processo è lo stesso in Skype for Business Server.
  
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

[Eliminare manualmente i database di registrazione dettagli chiamata e Qualità dell'esperienza in Skype for Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)