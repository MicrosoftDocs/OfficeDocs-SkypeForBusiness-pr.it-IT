---
title: Creare un nuovo criterio di archiviazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Riepilogo: informazioni su come creare un nuovo criterio di archiviazione per Skype for Business Server.'
ms.openlocfilehash: 8542c31050cf4ca9383c22b39c83b28309d3ea32
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992733"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>Creare un nuovo criterio di archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come creare un nuovo criterio di archiviazione per Skype for Business Server.
  
È possibile creare nuovi criteri di archiviazione usando il pannello di controllo o usando i cmdlet di Windows PowerShell.
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>Creare un nuovo criterio di archiviazione tramite il pannello di controllo

Per creare un nuovo criterio di archiviazione tramite il pannello di controllo:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.
    
4. Fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti: 
    
   - Per creare criteri di archiviazione a livello di sito, fare clic su **criteri sito**e quindi, in **selezionare un sito**, fare clic sul sito a cui applicare il criterio.
    
   - Per creare criteri di archiviazione a livello di utente, fare clic su **criteri utente**.
    
5. In **nuovi criteri di archiviazione**eseguire le operazioni seguenti:
    
   - In **nome**specificare un nome per il nuovo criterio, ad esempio ContosoEsterni.
    
   - In **Descrizione**specificare i dettagli relativi al criterio, ad esempio criteri di archiviazione degli utenti esterni per contoso.
    
   - Per controllare l'archiviazione delle comunicazioni con gli utenti interni, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .
    
   - Per controllare l'archiviazione delle comunicazioni con utenti esterni, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .
    
6. Fare clic su **Commit**.
    
    > [!IMPORTANT]
    > Le impostazioni di un criterio utente si applicano solo agli utenti e ai gruppi utente specifici a cui si applicano i criteri. Per informazioni dettagliate, vedere [applicare un criterio di archiviazione agli utenti in Skype for Business Server](apply-a-policy-to-users.md). 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>Creare un nuovo criterio di archiviazione tramite Windows PowerShell

Puoi anche creare nuovi criteri di archiviazione usando il cmdlet **New-CsArchivingPolicy** di Windows PowerShell. Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) .
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>Per creare un nuovo criterio di archiviazione a livello di sito

Questo comando crea un nuovo criterio di archiviazione per il sito Redmond:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>Per creare un nuovo criterio di archiviazione a livello per utente

Per creare un nuovo criterio di archiviazione a livello per utente, è sufficiente specificare un'identità univoca quando si creano i criteri:
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>Per creare un nuovo criterio di archiviazione che consente l'archiviazione delle sessioni di comunicazione interne

Dato che nei comandi precedenti non sono stati specificati parametri (ad eccezione del parametro di identità obbligatoria), i nuovi criteri utilizzeranno i valori predefiniti per tutte le relative proprietà. Per creare criteri che usano valori di proprietà diversi, includere semplicemente il parametro e il valore del parametro appropriati. Ad esempio, il comando seguente crea un criterio di archiviazione che consente l'archiviazione delle sessioni di messaggistica istantanea interne: 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>Per creare un nuovo criterio di archiviazione che consente l'archiviazione di sessioni di comunicazione interne ed esterne

Più valori di proprietà possono essere modificati includendo più parametri. Questo comando, ad esempio, configura il nuovo criterio per l'archiviazione delle sessioni di messaggistica istantanea interne ed esterne:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```
