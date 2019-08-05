---
title: Eliminare una raccolta esistente di impostazioni di configurazione del trunk SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch Exchange) o un SBC (Session Border Controller) presso il provider di servizi. '
ms.openlocfilehash: 55636cc34df4b05ccdd4b9035ef3aa4bb169e9a0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187025"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Eliminare una raccolta esistente di impostazioni di configurazione del trunk SIP in Skype for Business Server

Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch Exchange) o un SBC (Session Border Controller) presso il provider di servizi. Queste impostazioni eseguono operazioni come specifica:

- Se il bypass multimediale deve essere abilitato nei trunk.
- Condizioni in cui vengono inviati i pacchetti RTCP (Real-Time Transport Control Protocol).
- Indipendentemente dal fatto che sia necessaria o meno la crittografia SRTP (Real-Time Protocol) in ogni trunk.

Quando si installa Skype for Business Server, viene creata una raccolta globale di impostazioni di configurazione trunk SIP. Questa raccolta globale di impostazioni non può essere eliminata. Tuttavia, puoi usare il pannello di ServerControl di Skype for business o il cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) per "reimpostare" i valori predefiniti delle proprietà della raccolta globale. Se ad esempio è stata impostata la proprietà Enable3pccRefer su true, quando si reimposta la raccolta globale la proprietà Enable3pccRefer restituirà il valore predefinito false.

Gli amministratori possono anche creare impostazioni di configurazione trunk personalizzate nell'ambito del sito o nell'ambito del servizio (per un singolo gateway PSTN); Queste impostazioni personalizzate possono essere rimosse. Quando si rimuovono queste impostazioni personalizzate, tieni presente quanto segue:

- Se si rimuovono le impostazioni dell'ambito del servizio, il trunk SIP gestito da tali impostazioni verrà gestito dalle impostazioni applicate al sito, se esistenti. Se le impostazioni del sito non esistono, i trunk verranno quindi gestiti dalla raccolta globale delle impostazioni di configurazione del trunk.
- Se si rimuovono le impostazioni con ambito sito, i trunk SIP gestiti da tali impostazioni verranno ora gestiti dalla raccolta globale delle impostazioni di configurazione del trunk.

**Per rimuovere le impostazioni di configurazione del trunk con il pannello di controllo di Skype for Business Server** 

1. Nel pannello di controllo di Skype for Business Server fare clic su **routing vocale**e quindi su **configurazione trunk**.
2. Nella scheda **configurazione trunk** selezionare la raccolta di impostazioni di configurazione trunk SIP da eliminare, fare clic su **modifica**e quindi fare clic su **Elimina**. Per eliminare più raccolte nella stessa operazione, fare clic sulla prima raccolta da eliminare, quindi tenere premuto CTRL e fare clic su eventuali raccolte aggiuntive che si desidera rimuovere.
3. La proprietà **state** per la raccolta verrà aggiornata in UNCOMMITTED. **** Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **commit** e quindi su **commit tutti**.
4. Nella finestra di dialogo **impostazioni di configurazione vocale** non impegnata fare clic su **OK**.
5. Nella finestra di dialogo **Pannello di controllo di Skype for Business Server** fare clic su **OK**.
6. Se si cambia idea e si decide di non eliminare la raccolta, fare clic su **commit**e quindi su **Annulla tutte le modifiche non salvate**. Quando viene visualizzata la finestra **di dialogo Pannello di controllo di Skype for Business Server** , fare clic su **OK**.

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Rimozione delle impostazioni di configurazione del trunk tramite i cmdlet di Windows PowerShell


Puoi eliminare le impostazioni di configurazione del trunk usando Windows PowerShell e il cmdlet **Remove-CsTrunkConfiguration** . Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

**Per rimuovere una raccolta di impostazioni specificata**

Il comando seguente rimuove le impostazioni di configurazione trunk applicate al sito Redmond:

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**Per rimuovere tutte le raccolte applicate all'ambito del sito**

Questo comando rimuove tutte le impostazioni di configurazione trunk applicate all'ambito del servizio:

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**Per rimuovere tutte le raccolte in cui è abilitato il bypass multimediale**

Il comando seguente rimuove tutte le impostazioni di configurazione trunk in cui è stato abilitato il bypass multimediale:

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) .
