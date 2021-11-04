---
title: Skype for Business Server- Eliminare una raccolta esistente di impostazioni di configurazione trunk SIP
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
description: 'Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi. '
ms.openlocfilehash: 09e51dd54401b761c448872545111e8bebf01599
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760614"
---
# <a name="skype-for-business-server---delete-an-existing-collection-of-sip-trunk-configuration-settings"></a>Skype for Business Server- Eliminare una raccolta esistente di impostazioni di configurazione trunk SIP

Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi. Queste impostazioni consentono di specificare quanto segue:

- Se abilitare il bypass multimediale nei trunk.
- Le condizioni in base alle quali vengono inviati pacchetti RTCP (Real-Time Control Protocol).
- Se in ogni trunk è richiesta la crittografia SRTP (Secure Real-Time Protocol).

Quando si installa Skype for Business Server, viene creata automaticamente una raccolta globale di impostazioni di configurazione trunk SIP. Questa raccolta globale di impostazioni non può essere eliminata. Tuttavia, è possibile utilizzare il Skype for Business ServerControl Panel o il cmdlet [Remove-CsTrunkConfiguration](/powershell/module/skype/Remove-CsTrunkConfiguration) per "ripristinare" i valori predefiniti delle proprietà nella raccolta globale. Se ad esempio la proprietà Enable3pccRefer è stata impostata su True, quando si reimposta l'insieme globale, la proprietà Enable3pccRefer verrà ripristinata sul valore predefinito False.

Gli amministratori possono inoltre creare impostazioni di configurazione personalizzate per i trunk con ambito sito o servizio (per un gateway PSTN singolo) che possono essere rimosse. Quando si rimuovono le impostazioni personalizzate, tenere presente che:

- Se si rimuovono le impostazioni con ambito servizio, il trunk SIP gestito da tali impostazioni verrà gestito dalle impostazioni applicate al rispettivo sito, se esistenti. In caso contrario, i trunk verranno gestiti dalla raccolta globale di impostazioni di configurazione dei trunk.
- Se si rimuovono le impostazioni con ambito sito, i trunk SIP gestiti da tali impostazioni verranno gestiti dalla raccolta globale di impostazioni di configurazione dei trunk.

**Per rimuovere le impostazioni di configurazione trunk con il Skype for Business Server pannello di controllo** 

1. Nel Pannello Skype for Business Server, fare clic su **Routing vocale** e quindi su **Configurazione trunk.**
2. Nella scheda **Configurazione trunk** selezionare la raccolta di impostazioni di configurazione trunk SIP da eliminare, fare clic su **Modifica** e quindi su **Elimina.** Per eliminare più raccolte con una sola operazione, fare clic sulla prima raccolta da eliminare, quindi sulle altre raccolte tenendo premuto il tasto CTRL.
3. La proprietà **Stato** per la raccolta verrà aggiornata a **Commit non eseguito**. Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **Commit**, quindi su **Salva tutto**.
4. Nella finestra di dialogo **Impostazioni di configurazione vocale di cui non è stato eseguito il commit** fare clic su **OK**.
5. Nella finestra **Skype for Business Server pannello** di controllo fare clic su **OK.**
6. Se si cambia idea e si decide di non eliminare la raccolta, fare clic su **Commit** e quindi su Annulla tutte le modifiche di cui non è stato eseguito il **commit.** Quando viene visualizzata Skype for Business Server finestra di **dialogo** Pannello di controllo, fare clic su **OK.**

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Rimozione delle impostazioni di configurazione trunk tramite Windows PowerShell cmdlet


È possibile eliminare le impostazioni di configurazione trunk utilizzando Windows PowerShell e il cmdlet **Remove-CsTrunkConfiguration.** È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

**Per rimuovere una raccolta specificata di impostazioni**

Il comando seguente rimuove le impostazioni di configurazione dei trunk applicate al sito di Redmond:

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**Per rimuovere tutte le raccolte applicate all'ambito del sito**

Questo comando rimuove tutte le impostazioni di configurazione dei trunk applicate all'ambito servizio:

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**Per rimuovere tutte le raccolte in cui è abilitato il bypass multimediale**

Il comando seguente rimuove tutte le impostazioni di configurazione dei trunk in cui è stato abilitato il bypass multimediale:

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsTrunkConfiguration.](/powershell/module/skype/Remove-CsTrunkConfiguration)
