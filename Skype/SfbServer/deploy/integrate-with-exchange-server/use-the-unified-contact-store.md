---
title: Configurazione di Skype for Business Server 2015 per l'utilizzo dell'archivio contatti unificato
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: "Riepilogo: configurare l'archivio contatti unificato per Exchange Server e Skype for Business Server."
ms.openlocfilehash: fd70c4b0b3d94ba26b76847ff053bf33d5902799
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188099"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>Configurazione di Skype for Business Server 2015 per l'utilizzo dell'archivio contatti unificato
 
**Riepilogo:** Configurare l'archivio contatti unificati per Exchange Server 2016 o Exchange Server 2013 e Skype for Business Server.
  
L'uso dell'archivio contatti unificato consente agli utenti di gestire un unico elenco di contatti e di avere questi contatti disponibili in più applicazioni, tra cui Skype for business, Microsoft Outlook 2013 e Microsoft Outlook Web App 2013. Quando si Abilita l'archivio contatti unificato per un utente, i contatti dell'utente non vengono archiviati in Skype for Business Server e recuperati in base alle esigenze. I suoi contatti vengono invece archiviati in Exchange Server 2016 o Exchange Server 2013 e recuperati tramite servizi Web di Exchange.
  
> [!NOTE]
> Tecnicamente, le informazioni di contatto vengono archiviate in una coppia di cartelle presenti nella cassetta postale di Exchange dell'utente. I contatti sono archiviati in una cartella denominata contatti di Skype for business visibile agli utenti finali; i metadati relativi ai contatti vengono archiviati in una sottocartella non visibile agli utenti finali. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>Abilitazione dell'archivio contatti unificato per un utente

Se l'autenticazione da server a server tra Skype for Business Server ed Exchange Server è già configurata, è stato abilitato anche l'archivio contatti unificato; non è necessaria alcuna configurazione del server aggiuntiva. Tuttavia, per trasferire i contatti di un utente nell'archivio contatti unificato è necessaria la configurazione di un account utente aggiuntivo. Per impostazione predefinita, i contatti utente vengono conservati in Skype for Business Server e non nell'archivio contatti unificato.
  
L'accesso all'archivio contatti unificato viene gestito usando i criteri dei servizi utente di Skype for Business Server. I criteri per i server degli utenti hanno una sola proprietà (UcsAllowed); Questa proprietà viene usata per determinare la posizione in cui vengono archiviati i contatti di un utente. Se un utente è gestito da un criterio dei servizi utente in cui UcsAllowed è stato impostato su true ($True), i contatti dell'utente verranno archiviati nell'archivio contatti unificato. Se l'utente è gestito da un criterio dei servizi utente in cui UcsAllowed è stato impostato su false ($False), i suoi contatti verranno archiviati in Skype for Business Server.
  
Quando si installa Skype for Business Server, viene installato anche un criterio per i servizi utente singoli (configurato in ambito globale). Il valore UcsAllowed in questo criterio è impostato su true, quindi, per impostazione predefinita, i contatti utente verranno archiviati nell'archivio contatti unificato (supponendo che sia stato distribuito e configurato). Se si vuole eseguire la migrazione di tutti i contatti utente nell'archivio contatti unificato, non è necessario eseguire alcuna operazione. 
  
Se si preferisce non eseguire la migrazione di tutti i contatti all'archivio contatti unificato, è possibile disabilitare l'archivio contatti unificato per tutti gli utenti impostando la proprietà UcsAllowed nel criterio globale su false:
  
```
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

Dopo aver disabilitato l'archivio contatti unificato nel criterio globale, è possibile creare un criterio per utente che consenta l'uso dell'archivio contatti unificato; in questo modo è possibile che alcuni utenti mantengano i propri contatti nell'archivio contatti unificato mentre altri utenti continuano a mantenere i contatti in Skype for Business Server. Puoi creare criteri per i servizi utente per utente usando un comando simile al seguente:
  
```
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

Dopo aver creato il nuovo criterio, devi assegnare i criteri a qualsiasi utente che deve avere accesso all'archivio contatti unificato. I criteri per utente possono essere assegnati agli utenti usando comandi simili alla seguente:
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

Dopo aver assegnato il criterio, Skype for Business Server inizierà a eseguire la migrazione dei contatti dell'utente nell'archivio contatti unificato. Una volta completata la migrazione, l'utente dovrà quindi archiviare i suoi contatti in Exchange anziché in Skype for Business Server. Se l'utente ha eseguito l'accesso a Lync 2013 al termine della migrazione, verrà visualizzata una finestra di messaggio e verrà richiesto di disconnettersi da Skype for business e quindi di accedere di nuovo per completare il processo. Agli utenti a cui non è stato assegnato questo criterio per utente non verranno trasferiti i contatti nell'archivio contatti unificato. Questo perché gli utenti vengono gestiti dal criterio globale e l'uso dell'archivio contatti unificato è stato disabilitato nel criterio globale.
  
Puoi verificare che i contatti di un utente siano stati correttamente migrati nell'archivio contatti unificato eseguendo il cmdlet [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) da Skype for Business Server Management Shell:
  
```
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

Se Test-CsUnifiedContactStore ha esito positivo, significa che i contatti per l'utente SIP:<span></span>kenmyer<span></span>@ litwareinc. com sono stati migrati nell'archivio contatti unificato.
  
## <a name="rolling-back-the-unified-contact-store"></a>Rollback dell'archivio contatti unificato

Se è necessario rimuovere i contatti di un utente dall'archivio contatti unificato, ad esempio se l'utente deve essere reinstallato in Microsoft Lync Server 2010 e quindi non può più usare l'archivio contatti unificato, è necessario eseguire due operazioni. Prima di tutto, devi assegnare all'utente un nuovo criterio per i servizi utente, uno che impedisce l'archiviazione dei contatti nell'archivio contatti unificato. Ovvero un criterio in cui la proprietà UcsAllowed è stata impostata su $False. Se non si dispone di un criterio di questo tipo, è possibile crearne uno usando un comando simile al seguente:
  
```
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

Puoi quindi assegnare questo nuovo criterio per utente (NoUnifiedContactStore) usando un comando come questo:
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

Il comando precedente assegna il nuovo criterio all'utente Ken e impedisce inoltre che i contatti di Ken vengano migrati nell'archivio contatti unificato.
  
> [!NOTE]
> In alcuni casi è possibile ottenere lo stesso effetto netto semplicemente deassegnando i criteri dei servizi utente correnti dell'utente. Supponiamo ad esempio che Ken ha un criterio per i servizi utente per utente che Abilita l'archivio contatti unificato, ma il criterio globale vieta l'uso dell'archivio contatti unificato. In questo caso, puoi annullare l'assegnazione dei criteri di servizi per utente di Ken. Quando si esegue questa operazione, Ken verrà gestito automaticamente dal criterio globale e quindi non potrà più accedere all'archivio contatti unificato. Per annullare l'assegnazione di un criterio per utente assegnato in precedenza, USA lo stesso comando illustrato prima, ma questa volta imposta il parametro PolicyName su un valore null: Grant-CsUserServicesPolicy-Identity "Ken"-PolicyName $Null 
  
La terminologia "impedisce la migrazione dei contatti di Ken all'archivio contatti unificato" è importante da tenere presente quando si lavora con l'archivio contatti unificato. Semplicemente assegnando a Ken un nuovo criterio per i servizi utente non sposterà i suoi contatti dall'archivio contatti unificato. Quando un utente accede a Skype for Business Server, il sistema controlla i criteri dei servizi utente dell'utente per verificare se i suoi contatti devono essere conservati nell'archivio contatti unificato. Se la risposta è sì, ovvero se la proprietà UcsAllowed è impostata su $True, i contatti verranno migrati nell'archivio contatti unificato, presupponendo che i contatti non siano già presenti nell'archivio contatti unificato. Se la risposta è No, Skype for Business Server ignora semplicemente i contatti dell'utente e passa alla relativa attività successiva. Ciò significa che Skype for Business Server non sposterà automaticamente i contatti di un utente dall'archivio contatti unificato, indipendentemente dal valore della proprietà UcsAllowed.
  
Ciò significa anche che, dopo aver assegnato un nuovo criterio ai servizi utente, devi quindi eseguire il cmdlet [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps) per trasferire i contatti dell'utente da Exchange Server e tornare a Skype for Business Server. Ad esempio, dopo aver assegnato a Ken un nuovo criterio per i servizi utente, è possibile rimuovere i contatti dall'archivio contatti unificato usando il comando seguente:
  
```
Invoke-CsUcsRollback -Identity "Ken Myer"
```

Se si modificano i criteri dei servizi utente ma non si esegue il cmdlet Invoke-CsUcsRollback, i contatti di Ken non verranno rimossi dall'archivio contatti unificato. Cosa succede se si esegue Invoke-CsUcsRollback ma non si modificano i criteri dei servizi utente di Ken? In questo caso, i contatti di Ken verranno temporaneamente rimossi dall'archivio contatti unificato. Il fatto che questa rimozione sia temporanea è importante da ricordare. Dopo che i contatti di Ken sono stati rimossi dall'archivio contatti unificato, Skype for Business Server attenderà 7 giorni e quindi verificherà che il criterio dei servizi utente sia stato assegnato a Ken. Se a Ken viene ancora assegnato un criterio che consente all'utente dell'archivio contatti unificato, i suoi contatti verranno automaticamente spostati nell'archivio contatti. Per rimuovere definitivamente i contatti dall'archivio contatti unificato, è necessario modificare i criteri dei servizi utente oltre a eseguire il cmdlet Invoke-CsUcsRollback.
  
A causa del numero elevato di variabili che possono influire sulla migrazione, è difficile stimare il tempo necessario prima che gli account vengano completamente migrati nell'archivio contatti unificato. Come regola generale, tuttavia, la migrazione non viene applicata immediatamente: anche quando si esegue la migrazione di un numero limitato di contatti potrebbe essere necessario 10 minuti o più prima del completamento dello spostamento.
  

