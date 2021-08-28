---
title: Creare o modificare una raccolta di impostazioni di configurazione di registrazione dei dati in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 'Riepilogo: informazioni sulla registrazione dettagli chiamata in Skype for Business Server.'
ms.openlocfilehash: e9b30eee578fd83dd0d94fbd78a490bf1b0e65de
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626608"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Creare o modificare una raccolta di impostazioni di configurazione di registrazione dei dati in Skype for Business Server
 
**Riepilogo:** Informazioni sulla registrazione dettagli chiamata (CDR) in Skype for Business Server.
  
La registrazione dettagli chiamata consente di tenere traccia dell'utilizzo di elementi quali le sessioni di messaggistica istantanea peer-to-peer, le chiamate telefoniche VoIP (Voice over Internet Protocol) e le conferenze telefoniche. Questi dati relativi all'utilizzo includono informazioni sull'utente chiamante e sull'utente chiamato, sulla data della chiamata e sulla durata della conversazione.
  
Quando si installa Skype for Business Server viene creata automaticamente una singola raccolta globale di impostazioni di configurazione della registrazione dei dati. Gli amministratori hanno inoltre la possibilità di creare impostazioni personalizzato con ambito sito. Ogni volta che vengono utilizzate tali impostazioni con ambito sito, queste avranno la precedenza rispetto alle impostazioni globali. Ad esempio, se si creano impostazioni con ambito sito per il sito Redmond, tali impostazioni (anziché le impostazioni globali) verranno utilizzate per gestire la registrazione dei dati in Redmond.
  
È possibile creare le impostazioni di configurazione della registrazione dei dati utilizzando Skype for Business Server pannello di controllo o il cmdlet [New-CsCdrConfiguration.](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) È possibile utilizzare Skype for Business Server pannello di controllo o il cmdlet [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) per modificare le impostazioni esistenti. Se si utilizza il Skype for Business Server di controllo per creare o modificare le impostazioni, saranno disponibili le opzioni seguenti:
  
|**Impostazione dell'interfaccia utente**|**Parametro di PowerShell**|**Descrizione**|
|:-----|:-----|:-----|
|Nome  <br/> |Identità  <br/> |Identificatore univoco delle impostazioni di configurazione di registrazione dettagli chiamata che si desidera creare. Queste impostazioni possono essere create solo nell'ambito del sito.  <br/> |
|Abilita monitoraggio registrazioni dettagli chiamata  <br/> |EnableCDR  <br/> |Indica se la registrazione dettagli chiamata è abilitata o meno.  <br/> |
|Abilita eliminazione registrazioni dettagli chiamata  <br/> |EnablePurging  <br/> |Indica se le registrazioni dettagli chiamata saranno eliminate periodicamente dal relativo database.  <br/> |
|Mantieni registrazioni dettagli chiamata per durata massima (giorni)  <br/> |KeepCallDetailForDays  <br/> |Indica per quanti giorni le registrazioni dettagli chiamata verranno mantenute nel relativo database. Le eventuali registrazioni antecedenti al numero di giorni specificato verranno eliminate automaticamente. Si noti che questa operazione verrà eseguita soltanto se è stata abilitata l'eliminazione.  <br/> |
|Mantieni dati delle segnalazioni errori per durata massima (giorni)  <br/> |KeepErrorReportForDays  <br/> |Indica per quanti giorni verranno mantenuti i rapporti sugli errori di registrazione dettagli chiamata. Gli eventuali rapporti antecedenti al numero di giorni specificato verranno eliminati automaticamente. I rapporti sugli errori di registrazione dettagli chiamata sono rapporti di diagnostica caricati da applicazioni client.  <br/> |
   
> [!NOTE]
> I cmdlet New-CsCdrConfiguration e Set-CsCdrConfiguration includono opzioni aggiuntive non disponibili Skype for Business Server Pannello di controllo. Per ulteriori informazioni, vedere gli argomenti della Guida [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) e [Set-CsCdrConfiguration.](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Per creare le impostazioni di configurazione della registrazione dei dati tramite Skype for Business Server pannello di controllo

1. Nel Skype for Business Server di controllo fare clic **su Monitoraggio e archiviazione.**
    
2. Nella scheda **Registrazione dettagli chiamata** fare clic su **Nuovo.**
    
3. Nella finestra di dialogo **Seleziona un sito** selezionare il sito in cui devono essere create le nuove impostazioni di configurazione. Se la finestra di dialogo è vuota, è stata già assegnata una raccolta di impostazioni di configurazione di registrazione dettagli chiamata a tutti i siti. Ogni sito è limitato a una sola raccolta di questo tipo. In tal caso, è possibile eliminare e quindi ricreare le impostazioni oppure modificare semplicemente le impostazioni esistenti.
    
4. Nella finestra di dialogo **Nuova impostazione di registrazione dettagli chiamata** selezionare le opzioni desiderate e quindi fare clic su **Commit**.
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Per modificare le impostazioni di configurazione della registrazione dei dati esistenti tramite il Skype for Business Server di controllo

1. Nel Skype for Business Server di controllo fare clic **su Monitoraggio e archiviazione.**
    
2. Fare doppio clic sulla raccolta di impostazioni da modificare oppure selezionare la raccolta, fare clic su **Modifica** e quindi su **Mostra dettagli.** Si noti che è possibile modificare una sola raccolta alla volta. Per apportare le stesse modifiche a più raccolte, utilizzare Skype for Business Server Management Shell.
    
3. Nella finestra di dialogo **Modifica impostazione di registrazione dettagli chiamata** selezionare le opzioni desiderate e quindi fare clic su **Commit**.
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creazione delle impostazioni di configurazione di registrazione dei dati tramite Windows PowerShell cmdlet

È inoltre possibile creare impostazioni di configurazione della registrazione dei dati tramite Windows PowerShell e il cmdlet **New-CsCdrConfiguration.** È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo del blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>Per creare una nuova raccolta di impostazioni di configurazione di registrazione dettagli chiamata

 Il comando seguente crea una nuova raccolta di impostazioni di configurazione di registrazione dettagli chiamata applicate al sito Redmond:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>Per creare una raccolta di impostazioni di configurazione di registrazione dettagli chiamata che disabilitano la registrazione dettagli chiamata

 Poiché nel comando precedente non sono stati specificati parametri, eccetto il parametro obbligatorio Identity, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per le relative proprietà. Per creare impostazioni basate su valori di proprietà diversi, è sufficiente includere il parametro appropriato e il valore corrispondente. Per creare ad esempio una raccolta di impostazioni di configurazione di registrazione dettagli chiamata che consentano per impostazione predefinita di disabilitare la registrazione dettagli chiamata, utilizzare un comando simile al seguente:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>Per specificare più valori di proprietà quando si crea una nuova raccolta di impostazioni di configurazione di registrazione dettagli chiamata

 È possibile modificare più valori di proprietà includendo più parametri. Il comando seguente ad esempio configura le nuove impostazioni in modo da mantenere le registrazioni dettagli chiamata per 30 giorni e i rapporti sugli errori per 90 giorni:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsCdrConfiguration.](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)
