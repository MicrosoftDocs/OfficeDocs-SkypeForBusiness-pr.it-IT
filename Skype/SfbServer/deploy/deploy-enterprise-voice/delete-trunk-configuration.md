---
title: Eliminare una raccolta esistente di impostazioni di configurazione dei trunk SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Riepilogo: informazioni su come eliminare una raccolta di impostazioni di configurazione trunk utilizzando il Pannello di controllo di Skype for Business Server.'
ms.openlocfilehash: a9065304860a257a7787c557e59da38d03abfef0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836976"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Eliminare una raccolta esistente di impostazioni di configurazione dei trunk SIP in Skype for Business Server
 
**Riepilogo:** Informazioni su come eliminare una raccolta di impostazioni di configurazione trunk utilizzando il Pannello di controllo di Skype for Business Server.
  
Le impostazioni di configurazione dei trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un IP-Public Branch eXchange (PBX) o un session border controller (SBC) presso il provider di servizi. Queste impostazioni consentono di specificare quanto segue:
  
- Se abilitare il bypass multimediale nei trunk.
    
- Condizioni in cui vengono inviati i pacchetti RTCP (Realtime Transport Control Protocol).
    
- Indica se è necessaria o meno la crittografia SRTP (Secure Realtime Transport Protocol) in ogni trunk.
    
Quando si installa Skype for Business Server, viene creata automaticamente una raccolta globale di impostazioni di configurazione dei trunk SIP. Questa raccolta globale di impostazioni non può essere eliminata. Tuttavia, è possibile utilizzare il Pannello di controllo di Skype for Business Server o il cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) per ripristinare i valori predefiniti delle proprietà della raccolta globale. Se ad esempio la proprietà Enable3pccRefer è stata impostata su True, quando si reimposta l'insieme globale, la proprietà Enable3pccRefer viene ripristinata sul valore predefinito False.
  
Gli amministratori possono inoltre creare impostazioni di configurazione personalizzate per i trunk con ambito sito o servizio (per un gateway PSTN singolo) che possono essere rimosse. Quando si rimuovono le impostazioni personalizzate, tenere presente che:
  
- Se si rimuovono le impostazioni con ambito servizio, il trunk SIP gestito da tali impostazioni verrà gestito dalle impostazioni applicate al rispettivo sito, se esistenti. In caso contrario, i trunk verranno gestiti dalla raccolta globale di impostazioni di configurazione dei trunk.
    
- Se si rimuovono le impostazioni con ambito sito, i trunk SIP gestiti da tali impostazioni verranno gestiti dalla raccolta globale di impostazioni di configurazione dei trunk.
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>Per rimuovere le impostazioni di configurazione dei trunk con il Pannello di controllo di Skype for Business Server

1. Nel Pannello di controllo di Skype for Business Server fare clic su **Routing vocale** e quindi su **Configurazione trunk.**
    
2. Nella scheda **Configurazione trunk** selezionare la raccolta di impostazioni di configurazione dei trunk SIP da eliminare, fare clic su **Modifica**, quindi su **Elimina**. Per eliminare più raccolte con una sola operazione, fare clic sulla prima raccolta da eliminare, quindi sulle altre raccolte tenendo premuto il tasto CTRL.
    
3. La proprietà **Stato** per la raccolta verrà aggiornata a **Commit non eseguito**. Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **Commit**, quindi su **Salva tutto**.
    
4. Nella finestra di dialogo **Impostazioni di configurazione vocale di cui non è stato eseguito il commit** fare clic su **OK**.
    
5. Nella finestra di dialogo Del Pannello di controllo di **Skype for Business Server** fare clic su **OK.**
    
6. Se si decide di non eliminare più la raccolta, fare clic su **Commit**, quindi su **Annulla tutte le modifiche di cui non è stato eseguito il commit**. Quando viene visualizzata la finestra di dialogo Del Pannello di controllo di **Skype for Business Server,** fare clic su **OK.**
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>Rimozione delle impostazioni di configurazione dei trunk tramite i cmdlet di Skype for Business Server Management Shell

È possibile eliminare le impostazioni di configurazione dei trunk utilizzando Skype for Business Server Management Shell e il cmdlet **Remove-CsTrunkConfiguration.** È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Skype for Business Server Management Shell.
  
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

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps)
  

