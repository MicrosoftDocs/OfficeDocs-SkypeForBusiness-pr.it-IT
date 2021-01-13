---
title: Configurare Skype for Business Server per l'utilizzo dell'archivio contatti unificato
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: "Riepilogo: configurare l'archivio contatti unificato per Exchange Server e Skype for Business Server."
ms.openlocfilehash: 4b96a0c4f3294146c987794ffce083c46d94bb48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833866"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>Configurare Skype for Business Server per l'utilizzo dell'archivio contatti unificato
 
**Riepilogo:** Configurare l'archivio contatti unificato per Exchange Server 2016 o Exchange Server 2013 e Skype for Business Server.
  
L'utilizzo dell'archivio contatti unificato consente agli utenti di gestire un singolo elenco di contatti e di disporre di tali contatti in più applicazioni, tra cui Skype for business, Microsoft Outlook 2013 e Microsoft Outlook Web App 2013. Quando si Abilita l'archivio contatti unificato per un utente, i contatti dell'utente non vengono archiviati in Skype for Business Server e vengono recuperati in base alle esigenze. I contatti sono invece archiviati in Exchange Server 2016 o Exchange Server 2013 e vengono recuperati tramite i servizi Web di Exchange.
  
> [!NOTE]
> Tecnicamente, le informazioni di contatto vengono memorizzate in una coppia di cartelle trovate nella cassetta postale di Exchange dell'utente. I contatti stessi sono archiviati in una cartella denominata contatti Skype for business, visibile agli utenti finali. i metadati relativi ai contatti sono archiviati in una sottocartella che non è visibile agli utenti finali. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>Abilitazione dell'archivio unificato per i contatti di un utente

Se l'autenticazione da server a server tra Skype for Business Server e Exchange Server è già configurata, è stato abilitato anche l'archivio contatti unificato; non è necessaria alcuna configurazione aggiuntiva del server. Tuttavia, per spostare i contatti di un utente all'interno dell'archivio unificato è necessaria la configurazione di un ulteriore account utente. Per impostazione predefinita, i contatti dell'utente vengono conservati in Skype for Business Server e non nell'archivio contatti unificato.
  
L'accesso all'archivio contatti unificato viene gestito utilizzando i criteri dei servizi utente di Skype for Business Server. I criteri sono dotati di una proprietà singola (UcsAllowed), utilizzata per determinare il percorso in cui sono archiviati i contatti di un utente. Se un utente è gestito da un criterio dei servizi utente in cui UcsAllowed impostato è stato impostato su true ($True), i contatti dell'utente verranno archiviati nell'archivio contatti unificato. Se l'utente è gestito da un criterio dei servizi utente in cui UcsAllowed impostato è stato impostato su false ($False), i suoi contatti verranno archiviati in Skype for Business Server.
  
Quando si installa Skype for Business Server, viene installato anche un criterio per i servizi utente singoli (configurato nell'ambito globale). Il valore di UcsAllowed impostato in questo criterio è impostato su true, in modo che, per impostazione predefinita, i contatti utente vengano archiviati nell'archivio contatti unificato, presupponendo che sia stato distribuito e configurato. Se si desidera eseguire la migrazione di tutti i contatti utente nell'archivio contatti unificato, non è necessario eseguire alcuna operazione. 
  
Se si preferisce non eseguire la migrazione di tutti i contatti nell'archivio contatti unificato, è possibile disabilitare l'archivio contatti unificato per tutti gli utenti impostando la proprietà UcsAllowed impostato nel criterio globale su false:
  
```powershell
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

Dopo aver disabilitato l'archivio contatti unificato nel criterio globale, è possibile creare un criterio per utente che consenta l'utilizzo dell'archivio contatti unificato. in questo modo è possibile che alcuni utenti mantengano i propri contatti nell'archivio contatti unificato, mentre altri utenti continuano a mantenere i propri contatti in Skype for Business Server. È possibile creare un criterio dei servizi utente per utente utilizzando un comando simile al seguente:
  
```powershell
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

Dopo aver creato il nuovo criterio, bisognerà assegnarlo agli utenti ai quali si desidera concedere l'accesso all'archivio unificato per i contatti. I criteri "per utente" possono essere assegnati agli utenti attraverso un comando simile al seguente:
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

Dopo aver assegnato il criterio, Skype for Business Server inizierà a eseguire la migrazione dei contatti dell'utente nell'archivio contatti unificato. Al termine della migrazione, l'utente riceverà i propri contatti archiviati in Exchange anziché in Skype for Business Server. Se l'utente è connesso a Lync 2013 al termine della migrazione, viene visualizzata una finestra di messaggio e gli viene chiesto di disconnettersi da Skype for business e quindi di eseguire l'accesso per completare il processo. Gli utenti a cui non è stato assegnato il criterio per utente non avranno la migrazione dei contatti nell'archivio contatti unificato. Ciò è dovuto al fatto che gli utenti vengono gestiti dal criterio globale e l'utilizzo dell'archivio contatti unificato è stato disabilitato nei criteri globali.
  
È possibile verificare che i contatti di un utente siano stati correttamente migrati nell'archivio contatti unificato eseguendo il cmdlet [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) da in Skype for Business Server Management Shell:
  
```powershell
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

Se Test-CsUnifiedContactStore ha esito positivo, significa che i contatti per l'utente SIP: kenmyer@ <span></span> litwareinc <span></span> . com sono stati migrati nell'archivio contatti unificato.
  
## <a name="rolling-back-the-unified-contact-store"></a>Rollback (ripristino) dell'archivio unificato per i contatti

Se è necessario rimuovere i contatti di un utente dall'archivio contatti unificato, ad esempio se l'utente deve essere reinstallato in Microsoft Lync Server 2010 e pertanto non è più in grado di utilizzare l'archivio contatti unificato, è necessario eseguire due operazioni. Per prima cosa, è necessario assegnare all'utente un nuovo criterio dei servizi utente, che vieti l'archiviazione dei contatti nell'archivio contatti unificato. (Ovvero, un criterio in cui la proprietà UcsAllowed impostato è stata impostata su $False). Se non si dispone di un criterio di questo tipo, è possibile crearne uno utilizzando un comando simile al seguente:
  
```powershell
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

È quindi possibile assegnare il nuovo criterio "per utente" (NoUnifiedContactStore) attraverso un comando simile al seguente:
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

Questo comando assegna all'utente Ken Myer il nuovo criterio, e fa in modo che i contatti di Ken non vengano migrati all'archivio unificato per i contatti.
  
> [!NOTE]
> In alcuni casi, è possibile ottenere lo stesso effetto netto semplicemente deselezionando il criterio dei servizi utente correnti dell'utente. Supponiamo, ad esempio, che a Ken Myer sia assegnato un criterio dei servizi utente di tipo "per utente", che attiva l'archivio unificato per i contatti, e che il criterio globale proibisce l'utilizzo di quest'ultimo. In tal caso, è possibile annullare l'assegnazione dei criteri di servizio per utente di Ken. In questo modo, Ken sarà gestito automaticamente dal criterio globale, e non avrà più accesso all'archivio unificato per i contatti. Per annullare l'assegnazione di un criterio per utente precedentemente assegnato, utilizzare lo stesso comando illustrato in precedenza, ma questa volta impostare il parametro PolicyName su un valore null: Grant-CsUserServicesPolicy-Identity "Ken di base"-PolicyName $Null 
  
La terminologia "impedisce la migrazione dei contatti di Ken nell'archivio contatti unificato" è importante da tenere presente quando si lavora con l'archivio contatti unificato. Semplicemente assegnando a Ken un nuovo criterio dei servizi utente non sposterà i suoi contatti dall'archivio contatti unificato. Quando un utente accede a Skype for Business Server, il sistema verifica il criterio dei servizi utente dell'utente per verificare se i propri contatti devono essere conservati nell'archivio contatti unificato. Se la risposta è sì, ovvero se la proprietà UcsAllowed impostato è impostata su $True, i contatti verranno migrati nell'archivio contatti unificato, presupponendo che i contatti non siano già presenti nell'archivio contatti unificato. Se la risposta è No, Skype for Business Server ignora semplicemente i contatti dell'utente e passa alla relativa attività successiva. Ciò significa che in Skype for Business Server non verranno spostati automaticamente i contatti di un utente dall'archivio contatti unificato, indipendentemente dal valore della proprietà UcsAllowed impostato.
  
Questo significa anche che, dopo aver assegnato un nuovo criterio ai servizi utente, è necessario eseguire il cmdlet [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps) per spostare i contatti dell'utente fuori da Exchange Server e viceversa in Skype for Business Server. Ad esempio, dopo avere assegnato a Ken Myer un nuovo criterio dei servizi utente, è possibile spostare i suoi contatti fuori dall'archivio unificato per i contatti, utilizzando il seguente comando:
  
```powershell
Invoke-CsUcsRollback -Identity "Ken Myer"
```

Se si modifica il criterio dei servizi utente ma non si esegue il cmdlet Invoke-CsUcsRollback, i contatti di Ken non saranno rimossi dall'archivio unificato per i contatti. Cosa succede se si esegue il cmdlet Invoke-CsUcsRollback ma non si modifica il criterio dei servizi utente di Ken Myer? In questo caso, i contatti di Ken vengono rimossi temporaneamente dall'archivio unificato per i contatti. È importante ricordare che questa rimozione è temporanea. Dopo che i contatti di Ken sono stati rimossi dall'archivio contatti unificato, Skype for Business Server attende 7 giorni e quindi controlla se i criteri dei servizi utente sono stati assegnati a Ken. Se a Ken è ancora assegnato un criterio che consente l'utilizzo dell'archivio unificato per i contatti, i contatti saranno automaticamente spostati nuovamente nell'archivio unificato per i contatti. Per rimuovere temporaneamente i contatti dall'archivio unificato per i contatti, è necessario modificare il criterio dei servizi utente, oltre ad eseguire il cmdlet Invoke-CsUcsRollback.
  
A causa del numero elevato di variabili che possono influire sulla migrazione, è difficile stimare il tempo necessario prima che gli account vengano completamente migrati nell'archivio contatti unificato. Come regola generale, tuttavia, la migrazione non ha effetto immediato: anche quando si esegue la migrazione di un numero limitato di contatti potrebbe essere necessario 10 minuti o più prima che lo spostamento sia stato completato.
  

