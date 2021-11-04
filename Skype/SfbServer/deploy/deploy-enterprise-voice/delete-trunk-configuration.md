---
title: 'Skype for Business Server: eliminare una raccolta esistente di impostazioni di configurazione trunk SIP'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Riepilogo: informazioni su come eliminare una raccolta di impostazioni di configurazione trunk tramite il Pannello Skype for Business Server controllo.'
ms.openlocfilehash: 19de05f2b31bc7a083aca7a04d71c32f17d0ea85
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771541"
---
# <a name="skype-for-business-server-delete-an-existing-collection-of-sip-trunk-configuration-settings"></a>Skype for Business Server: eliminare una raccolta esistente di impostazioni di configurazione trunk SIP 
 
**Riepilogo:** Informazioni su come eliminare una raccolta di impostazioni di configurazione trunk tramite il Pannello Skype for Business Server controllo.
  
Le impostazioni di configurazione dei trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (Branch eXchange) di IP-Public o un session border controller (SBC) presso il provider di servizi. Queste impostazioni consentono di specificare quanto segue:
  
- Se il bypass multimediale deve essere abilitato nei trunk
    
- Condizioni in cui vengono inviati pacchetti RTCP (Realtime Transport Control Protocol)
    
- Indica se è necessaria o meno la crittografia SRTP (Secure Realtime Transport Protocol) in ogni trunk
    
Quando si installa Skype for Business Server, viene creata automaticamente una raccolta globale di impostazioni di configurazione trunk SIP. Questa raccolta globale di impostazioni non può essere eliminata. È tuttavia possibile utilizzare il Pannello di controllo di Skype for Business Server o il cmdlet [Remove-CsTrunkConfiguration](/powershell/module/skype/remove-cstrunkconfiguration) per ripristinare i valori predefiniti delle proprietà della raccolta globale. Se ad esempio la proprietà Enable3pccRefer è stata impostata su True, quando si reimposta l'insieme globale, la proprietà Enable3pccRefer verrà ripristinata sul valore predefinito False.
  
Gli amministratori possono inoltre creare impostazioni di configurazione personalizzate per i trunk con ambito sito o servizio (per un gateway PSTN singolo) che possono essere rimosse. Quando si rimuovono queste impostazioni personalizzate, tenere presente quanto segue:
  
- Se si rimuovono le impostazioni con ambito servizio, il trunk SIP gestito da tali impostazioni verrà gestito dalle impostazioni applicate al rispettivo sito, se esistenti. In caso contrario, i trunk verranno gestiti dalla raccolta globale di impostazioni di configurazione dei trunk.
    
- Se si rimuovono impostazioni con ambito sito, tutti i trunk SIP gestiti da tali impostazioni verranno ora gestiti dalla raccolta globale di impostazioni di configurazione trunk.
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>Per rimuovere le impostazioni di configurazione trunk con Skype for Business Server Pannello di controllo

1. Nel Skype for Business Server di controllo fare clic **su Routing vocale** e quindi su Configurazione **trunk.**
    
2. Nella scheda **Configurazione trunk** selezionare la raccolta di impostazioni di configurazione trunk SIP da eliminare, fare clic su **Modifica** e quindi su **Elimina.** Per eliminare più raccolte nella stessa operazione, fare clic sulla prima raccolta da eliminare, quindi tenere premuto CTRL e fare clic su qualsiasi altra raccolta che si desidera rimuovere.
    
3. La proprietà **Stato** per la raccolta verrà aggiornata a **Commit non eseguito**. Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **Commit**, quindi su **Salva tutto**.
    
4. Nella finestra di dialogo **Impostazioni di configurazione vocale di cui non è stato eseguito il commit** fare clic su **OK**.
    
5. Nella finestra **Skype for Business Server pannello** di controllo fare clic su **OK.**
    
6. Se si decide di non eliminare più la raccolta, fare clic su **Commit**, quindi su **Annulla tutte le modifiche di cui non è stato eseguito il commit**. Quando viene visualizzata Skype for Business Server finestra **di dialogo** Pannello di controllo, fare clic su **OK.**
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>Rimozione della configurazione trunk Impostazioni tramite i cmdlet Skype for Business Server Management Shell

È possibile eliminare le impostazioni di configurazione trunk utilizzando Skype for Business Server Management Shell e il cmdlet **Remove-CsTrunkConfiguration.** È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Skype for Business Server Management Shell.
  
### <a name="to-remove-a-specified-collection-of-settings"></a>Per rimuovere una raccolta specificata di impostazioni

- Il comando seguente rimuove le impostazioni di configurazione dei trunk applicate al sito di Redmond:
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>Per rimuovere tutte le raccolte applicate all'ambito del sito

- Questo comando rimuove tutte le impostazioni di configurazione dei trunk applicate all'ambito servizio:
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>Per rimuovere tutte le raccolte in cui è abilitato il bypass multimediale

- Il comando seguente rimuove tutte le impostazioni di configurazione dei trunk in cui è stato abilitato il bypass multimediale:
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsTrunkConfiguration.](/powershell/module/skype/remove-cstrunkconfiguration)
