---
title: Configurare Skype for Business Server per l'utilizzo dell'archivio contatti unificato
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: "Riepilogo: configurare l'archivio contatti unificato per Exchange Server e Skype for Business Server."
ms.openlocfilehash: ed28f57350e2ce1d7ed5f92d712bdf5ecc7f3de4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853670"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>Configurare Skype for Business Server per l'utilizzo dell'archivio contatti unificato
 
**Riepilogo:** Configurare l'archivio contatti unificato Exchange Server 2016 o Exchange Server 2013 e Skype for Business Server.
  
Utilizzando l'archivio contatti unificato, gli utenti mantengono un singolo elenco contatti e quindi dispongono di tali contatti disponibili in più applicazioni, tra cui Skype for Business, Microsoft Outlook 2013 e Microsoft Outlook Web App 2013. Quando si abilita l'archivio contatti unificato per un utente, i contatti dell'utente non vengono archiviati in Skype for Business Server e recuperati in base alle esigenze. I contatti vengono invece archiviati in Exchange Server 2016 o Exchange Server 2013 e vengono recuperati utilizzando Exchange Web Services.
  
> [!NOTE]
> Tecnicamente, le informazioni di contatto sono archiviate in una coppia di cartelle trovate nella cassetta postale Exchange'utente. I contatti stessi vengono archiviati in una cartella denominata Skype for Business Contatti visibile agli utenti finali. I metadati relativi ai contatti vengono archiviati in una sottocartella non visibile agli utenti finali. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>Abilitazione dell'archivio unificato per i contatti di un utente

Se l'autenticazione da server a server tra Skype for Business Server e Exchange Server è già configurata, è stato abilitato anche l'archivio contatti unificato. non è necessaria alcuna configurazione aggiuntiva del server. Tuttavia, per spostare i contatti di un utente all'interno dell'archivio unificato è necessaria la configurazione di un ulteriore account utente. Per impostazione predefinita, i contatti utente vengono mantenuti in Skype for Business Server e non nell'archivio contatti unificato.
  
L'accesso all'archivio contatti unificato viene gestito utilizzando i criteri Skype for Business Server servizi utente. I criteri sono dotati di una proprietà singola (UcsAllowed), utilizzata per determinare il percorso in cui sono archiviati i contatti di un utente. Se un utente è gestito da un criterio di servizi utente in cui UcsAllowed è stato impostato su True ($True), i contatti dell'utente verranno archiviati nell'archivio contatti unificato. Se l'utente è gestito da un criterio di servizi utente in cui UcsAllowed è stato impostato su False ($False), i suoi contatti verranno archiviati in Skype for Business Server.
  
Quando si installa Skype for Business Server, viene installato anche un singolo criterio dei servizi utente (configurato nell'ambito globale). Il valore UcsAllowed in questo criterio è impostato su True, il che significa che, per impostazione predefinita, i contatti utente verranno archiviati nell'archivio contatti unificato (presupponendo che sia stato distribuito e configurato). Se si desidera eseguire la migrazione di tutti i contatti utente nell'archivio contatti unificato, non è necessario eseguire alcun'operazione. 
  
Se si preferisce non eseguire la migrazione di tutti i contatti nell'archivio contatti unificato, è possibile disabilitare l'archivio contatti unificato per tutti gli utenti impostando la proprietà UcsAllowed nel criterio globale su False:
  
```powershell
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

Dopo aver disabilitato l'archivio contatti unificato nel criterio globale, è possibile creare un criterio per utente che consenta l'utilizzo dell'archivio contatti unificato. in questo modo è possibile fare in modo che alcuni utenti mantenino i propri contatti nell'archivio contatti unificato mentre altri continuano a mantenere i contatti in Skype for Business Server. È possibile creare criteri di servizi per utente utilizzando un comando simile al seguente:
  
```powershell
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

Dopo aver creato il nuovo criterio, bisognerà assegnarlo agli utenti ai quali si desidera concedere l'accesso all'archivio unificato per i contatti. I criteri "per utente" possono essere assegnati agli utenti attraverso un comando simile al seguente:
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

Dopo l'assegnazione del criterio, Skype for Business Server inizierà a eseguire la migrazione dei contatti dell'utente nell'archivio contatti unificato. Al termine della migrazione, i contatti dell'utente verranno archiviati in Exchange anziché Skype for Business Server. Se l'utente accede a Lync 2013 al termine della migrazione, verrà visualizzata una finestra di messaggio che gli chiederà di disconnettersi da Skype for Business e quindi di eseguire di nuovo l'accesso per completare il processo. Agli utenti a cui non è stato assegnato questo criterio per utente non verrà eseguita la migrazione dei contatti nell'archivio contatti unificato. Questo perché tali utenti vengono gestiti dal criterio globale e l'utilizzo dell'archivio contatti unificato è stato disabilitato nel criterio globale.
  
È possibile verificare che i contatti di un utente siano stati migrati correttamente nell'archivio contatti unificato eseguendo il cmdlet [Test-CsUnifiedContactStore](/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) dall'interno di Skype for Business Server Management Shell:
  
```powershell
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

Se Test-CsUnifiedContactStore ha esito positivo, significa che i contatti per l'utente sip:kenmyer@ litwareinc .com sono stati migrati nell'archivio contatti <span></span> <span></span> unificato.
  
## <a name="rolling-back-the-unified-contact-store"></a>Rollback (ripristino) dell'archivio unificato per i contatti

Se è necessario rimuovere i contatti di un utente dall'archivio contatti unificato( ad esempio, se l'utente deve essere riassato in Microsoft Lync Server 2010 e quindi non può più utilizzare l'archivio contatti unificato), è necessario eseguire due operazioni. Prima di tutto, è necessario assegnare all'utente un nuovo criterio dei servizi utente, che impedisce l'archiviazione dei contatti nell'archivio contatti unificato. Ovvero, un criterio in cui la proprietà UcsAllowed è stata impostata su $False. Se non si dispone di un criterio di questo tipo, è possibile crearne uno utilizzando un comando simile al seguente:
  
```powershell
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

È quindi possibile assegnare il nuovo criterio "per utente" (NoUnifiedContactStore) attraverso un comando simile al seguente:
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

Questo comando assegna all'utente Ken Myer il nuovo criterio, e fa in modo che i contatti di Ken non vengano migrati all'archivio unificato per i contatti.
  
> [!NOTE]
> In alcuni casi è possibile ottenere lo stesso effetto netto semplicemente annullando l'assegnazione del criterio di servizi utente corrente dell'utente. Supponiamo, ad esempio, che a Ken Myer sia assegnato un criterio dei servizi utente di tipo "per utente", che attiva l'archivio unificato per i contatti, e che il criterio globale proibisce l'utilizzo di quest'ultimo. In tal caso, è possibile annullare l'assegnazione dei criteri dei servizi per utente di Ken. In questo modo, Ken sarà gestito automaticamente dal criterio globale, e non avrà più accesso all'archivio unificato per i contatti. Per annullare l'assegnazione di un criterio assegnato in precedenza per utente, utilizzare lo stesso comando mostrato in precedenza, ma questa volta impostare il parametro PolicyName su un valore null: Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName $Null 
  
La terminologia "impedisce la migrazione dei contatti di Ken nell'archivio contatti unificato" è importante tenere presente quando si utilizza l'archivio contatti unificato. Se si assegna semplicemente a Ken un nuovo criterio servizi utente, i contatti non verranno spostati dall'archivio contatti unificato. Quando un utente accede a Skype for Business Server, il sistema controlla i criteri dei servizi utente dell'utente per verificare se i suoi contatti devono essere conservati nell'archivio contatti unificato. Se la risposta è sì, ovvero se la proprietà UcsAllowed è impostata su $True, tali contatti verranno migrati nell'archivio contatti unificato, presupponendo che tali contatti non siano già presenti nell'archivio contatti unificato. Se la risposta è no, Skype for Business Server semplicemente ignora i contatti dell'utente e passa all'attività successiva. Ciò significa che Skype for Business Server i contatti di un utente non verranno spostati automaticamente dall'archivio contatti unificato, indipendentemente dal valore della proprietà UcsAllowed.
  
Ciò significa anche che, dopo aver assegnato all'utente un nuovo criterio servizi utente, è necessario eseguire il cmdlet [Invoke-CsUcsRollback](/powershell/module/skype/invoke-csucsrollback?view=skype-ps) per spostare i contatti dell'utente fuori da Exchange Server e tornare a Skype for Business Server. Ad esempio, dopo avere assegnato a Ken Myer un nuovo criterio dei servizi utente, è possibile spostare i suoi contatti fuori dall'archivio unificato per i contatti, utilizzando il seguente comando:
  
```powershell
Invoke-CsUcsRollback -Identity "Ken Myer"
```

Se si modifica il criterio dei servizi utente ma non si esegue il cmdlet Invoke-CsUcsRollback, i contatti di Ken non saranno rimossi dall'archivio unificato per i contatti. Cosa succede se si esegue il cmdlet Invoke-CsUcsRollback ma non si modifica il criterio dei servizi utente di Ken Myer? In questo caso, i contatti di Ken vengono rimossi temporaneamente dall'archivio unificato per i contatti. È importante ricordare che questa rimozione è temporanea. Dopo che i contatti di Ken sono stati rimossi dall'archivio contatti unificato, Skype for Business Server attenderà 7 giorni e quindi verifica quali criteri di servizi utente sono stati assegnati a Ken. Se a Ken è ancora assegnato un criterio che consente l'utilizzo dell'archivio unificato per i contatti, i contatti saranno automaticamente spostati nuovamente nell'archivio unificato per i contatti. Per rimuovere temporaneamente i contatti dall'archivio unificato per i contatti, è necessario modificare il criterio dei servizi utente, oltre ad eseguire il cmdlet Invoke-CsUcsRollback.
  
A causa del numero elevato di variabili che possono influire sulla migrazione, è difficile stimare il tempo necessario prima che gli account siano migrati completamente nell'archivio contatti unificato. Come regola generale, tuttavia, la migrazione non ha effetto immediato: anche quando si esegue la migrazione di un numero limitato di contatti, potrebbero essere necessario 10 minuti o più prima del completamento dello spostamento.
