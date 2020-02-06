---
title: Creare o modificare una raccolta di impostazioni di configurazione CDR in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 'Riepilogo: informazioni sulla registrazione dei dettagli delle chiamate (CDR) in Skype for Business Server.'
ms.openlocfilehash: 88e86aaec7ca922db39b8c74dc1b354ab0389ba7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818046"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Creare o modificare una raccolta di impostazioni di configurazione CDR in Skype for Business Server
 
**Riepilogo:** Informazioni sulla registrazione dei dettagli delle chiamate (CDR) in Skype for Business Server.
  
La registrazione dei dettagli delle chiamate (CDR) consente di tenere traccia dell'uso di elementi come sessioni di messaggistica istantanea peer-to-peer, chiamate telefoniche VoIP (Voice over Internet Protocol) e chiamate in conferenza. Questo dati di utilizzo include informazioni su chi ha chiamato chi, quando ha chiamato, e per quanto tempo ha parlato.
  
Quando si installa Skype for Business Server, viene creata una singola raccolta globale di impostazioni di configurazione CDR. Gli amministratori hanno anche la possibilità di creare impostazioni personalizzate nell'ambito del sito. Ogni volta che vengono usate queste impostazioni con ambito sito, hanno la precedenza sulle impostazioni globali. Ad esempio, se si creano impostazioni con ambito sito per il sito Redmond, le impostazioni (invece delle impostazioni globali) verranno usate per gestire CDR in Redmond.
  
È possibile creare impostazioni di configurazione CDR usando il pannello di controllo di Skype for Business Server o il cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) . Puoi usare il pannello di controllo di Skype for Business Server o il cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) per modificare le impostazioni esistenti. Se si usa il pannello di controllo di Skype for Business Server per creare o modificare le impostazioni, le opzioni seguenti saranno disponibili:
  
|**Impostazione dell'interfaccia utente**|**Parametro di PowerShell**|**Descrizione**|
|:-----|:-----|:-----|
|Nome  <br/> |Identity  <br/> |Identificatore univoco per le impostazioni di configurazione CDR da creare. Queste impostazioni possono essere create solo nell'ambito del sito.  <br/> |
|Abilitare il monitoraggio di CDRs  <br/> |EnableCDR  <br/> |Indica se CDR è abilitato o meno.  <br/> |
|Abilitare l'eliminazione di CDRs  <br/> |EnablePurging  <br/> |Indica se i record CDR verranno eliminati periodicamente dal database CDR.  <br/> |
|Mantieni CDRs per la durata massima (giorni)  <br/> |KeepCallDetailForDays  <br/> |Indica il numero di giorni in cui i record CDR verranno conservati nel database CDR. Tutti i record antecedenti al numero di giorni specificato verranno eliminati automaticamente. Tieni presente che l'eliminazione verrà eseguita solo se l'eliminazione è stata abilitata.  <br/> |
|Mantieni i dati del report degli errori per la durata massima (giorni)  <br/> |KeepErrorReportForDays  <br/> |Indica il numero di giorni in cui vengono mantenuti i report di errore CDR. Tutti i report antecedenti al numero di giorni specificato verranno eliminati automaticamente. I report di errore CDR sono report di diagnostica caricati dalle applicazioni client.  <br/> |
   
> [!NOTE]
> I cmdlet New-CsCdrConfiguration e Set-CsCdrConfiguration includono opzioni aggiuntive non disponibili nel pannello di controllo di Skype for Business Server. Per altre informazioni, vedere gli argomenti della Guida [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) e [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Per creare impostazioni di configurazione CDR tramite il pannello di controllo di Skype for Business Server

1. Nel pannello di controllo di Skype for Business Server fare clic su **monitoraggio e archiviazione**.
    
2. Nella scheda **registrazione dettagli chiamata** fare clic su **nuovo**.
    
3. Nella finestra di dialogo **Seleziona sito** selezionare il sito in cui devono essere create le nuove impostazioni di configurazione. Se la finestra di dialogo è vuota, significa che a tutti i siti è già stata assegnata una raccolta di impostazioni di configurazione CDR. Ogni sito è limitato a una singola raccolta di questo tipo. In questo caso, è possibile eliminare e ricreare le impostazioni oppure semplicemente modificare le impostazioni esistenti.
    
4. Nella finestra di dialogo **nuova impostazione registrazione dettagli chiamata (CDR)** effettuare le selezioni desiderate e quindi fare clic su **commit**.
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Per modificare le impostazioni di configurazione CDR esistenti tramite il pannello di controllo di Skype for Business Server

1. Nel pannello di controllo di Skype for Business Server fare clic su **monitoraggio e archiviazione**.
    
2. Fare doppio clic sulla raccolta di impostazioni da modificare oppure selezionare la raccolta, fare clic su **modifica**e quindi su **Mostra dettagli**. Tieni presente che puoi modificare solo una singola raccolta alla volta. Per apportare le stesse modifiche a più raccolte, USA invece Skype for Business Server Management Shell.
    
3. Nella finestra di dialogo **Modifica impostazione registrazione dettagli chiamata (CDR)** effettuare le selezioni desiderate e quindi fare clic su **commit**.
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creazione di impostazioni di configurazione CDR con i cmdlet di Windows PowerShell

È possibile creare impostazioni di configurazione CDR anche tramite Windows PowerShell e il cmdlet **New-CsCdrConfiguration** . Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>Per creare una nuova raccolta di impostazioni di configurazione CDR

 Questo comando crea una nuova raccolta di impostazioni di configurazione CDR applicate al sito Redmond:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>Per creare una raccolta di impostazioni di configurazione CDR che disabilitano la registrazione dei dettagli delle chiamate

 Poiché non sono stati specificati parametri (ad eccezione del parametro di identità obbligatorio) nel comando precedente, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per tutte le relative proprietà. Per creare impostazioni che usano valori di proprietà diversi, includere semplicemente il parametro e il valore del parametro appropriati. Ad esempio, per creare una raccolta di impostazioni di configurazione dei dettagli delle chiamate che, per impostazione predefinita, Consenti Disabilita registrazione dettagli chiamata usa un comando simile al seguente:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>Per specificare più valori di proprietà quando si crea una nuova raccolta di impostazioni di configurazione CDR

 Puoi modificare più valori di proprietà includendo più parametri. Ad esempio, questo comando Configura le nuove impostazioni per conservare i record dei dettagli delle chiamate per 30 giorni e i report degli errori per 90 giorni:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) .
  

