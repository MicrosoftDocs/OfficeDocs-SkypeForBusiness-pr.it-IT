---
title: Eliminare una raccolta esistente di impostazioni di configurazione del trunk SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Riepilogo: informazioni su come eliminare una raccolta di impostazioni di configurazione trunk usando il pannello di controllo di Skype for Business Server.'
ms.openlocfilehash: 1cd46f855a92f4b1b975f565b12ff07c3af24111
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767709"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Eliminare una raccolta esistente di impostazioni di configurazione del trunk SIP in Skype for Business Server
 
**Riepilogo:** Informazioni su come eliminare una raccolta di impostazioni di configurazione trunk usando il pannello di controllo di Skype for Business Server.
  
Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch eXchange) o un SBC (Session Border Controller) presso il provider di servizi. Queste impostazioni eseguono operazioni come specifica:
  
- Se il bypass multimediale deve essere abilitato nei trunk.
    
- Condizioni in cui vengono inviati i pacchetti RTCP (Realtime Transport Control Protocol).
    
- Indipendentemente dal fatto che sia necessaria o meno la crittografia SRTP (Secure Realtime Transport Protocol) in ogni trunk.
    
Quando si installa Skype for Business Server, viene creata una raccolta globale di impostazioni di configurazione trunk SIP. Questa raccolta globale di impostazioni non può essere eliminata. Tuttavia, puoi usare il pannello di controllo di Skype for Business Server o il cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) per "reimpostare" i valori predefiniti delle proprietà della raccolta globale. Se ad esempio è stata impostata la proprietà Enable3pccRefer su true, quando si reimposta la raccolta globale la proprietà Enable3pccRefer restituirà il valore predefinito false.
  
Gli amministratori possono anche creare impostazioni di configurazione trunk personalizzate nell'ambito del sito o nell'ambito del servizio (per un singolo gateway PSTN); Queste impostazioni personalizzate possono essere rimosse. Quando si rimuovono queste impostazioni personalizzate, tieni presente quanto segue:
  
- Se si rimuovono le impostazioni dell'ambito del servizio, il trunk SIP gestito da tali impostazioni verrà gestito dalle impostazioni applicate al sito, se esistenti. Se le impostazioni del sito non esistono, i trunk verranno quindi gestiti dalla raccolta globale delle impostazioni di configurazione del trunk.
    
- Se si rimuovono le impostazioni con ambito sito, i trunk SIP gestiti da tali impostazioni verranno ora gestiti dalla raccolta globale delle impostazioni di configurazione del trunk.
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>Per rimuovere le impostazioni di configurazione del trunk con il pannello di controllo di Skype for Business Server

1. Nel pannello di controllo di Skype for Business Server fare clic su **routing vocale** e quindi su **configurazione trunk**.
    
2. Nella scheda **configurazione trunk** selezionare la raccolta di impostazioni di configurazione trunk SIP da eliminare, fare clic su **modifica** e quindi su **Elimina**. Per eliminare più raccolte nella stessa operazione, fare clic sulla prima raccolta da eliminare, quindi tenere premuto CTRL e fare clic su eventuali raccolte aggiuntive che si desidera rimuovere.
    
3. La proprietà **state** per la raccolta verrà aggiornata in **UNCOMMITTED**. Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **commit** e quindi su **commit tutti**.
    
4. Nella finestra di dialogo **impostazioni di configurazione vocale non impegnata** fare clic su **OK**.
    
5. Nella finestra di dialogo **Pannello di controllo di Skype for Business Server** fare clic su **OK**.
    
6. Se si cambia idea e si decide di non eliminare la raccolta, fare clic su **commit** e quindi su **Annulla tutte le modifiche non salvate**. Quando viene visualizzata la finestra **di dialogo Pannello di controllo di Skype for Business Server** , fare clic su **OK**.
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>Rimozione delle impostazioni di configurazione del trunk tramite i cmdlet di Skype for Business Server Management Shell

Puoi eliminare le impostazioni di configurazione del trunk usando Skype for Business Server Management Shell e il cmdlet **Remove-CsTrunkConfiguration** . Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Skype for Business Server Management Shell.
  
### <a name="to-remove-a-specified-collection-of-settings"></a>Per rimuovere una raccolta di impostazioni specificata

- Il comando seguente rimuove le impostazioni di configurazione trunk applicate al sito Redmond:
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>Per rimuovere tutte le raccolte applicate all'ambito del sito

- Questo comando rimuove tutte le impostazioni di configurazione trunk applicate all'ambito del servizio:
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>Per rimuovere tutte le raccolte in cui è abilitato il bypass multimediale

- Il comando seguente rimuove tutte le impostazioni di configurazione trunk in cui è stato abilitato il bypass multimediale:
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) .
  

