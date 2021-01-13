---
title: Creare un nuovo criterio di archiviazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Riepilogo: informazioni su come creare un nuovo criterio di archiviazione per Skype for Business Server.'
ms.openlocfilehash: 3e1f538aba26025f5868a09babd3b67df36f9a3f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817646"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>Creare un nuovo criterio di archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come creare un nuovo criterio di archiviazione per Skype for Business Server.
  
È possibile creare nuovi criteri di archiviazione utilizzando il pannello di controllo o i cmdlet di Windows PowerShell.
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>Creare un nuovo criterio di archiviazione utilizzando il pannello di controllo

Per creare un nuovo criterio di archiviazione utilizzando il pannello di controllo:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.
    
4. Fare clic su **Nuovo** e quindi eseguire una delle operazioni seguenti: 
    
   - Per creare criteri di archiviazione a livello di sito, fare clic su **criteri sito** e quindi in **Seleziona un sito** fare clic sul sito a cui deve essere applicato il criterio.
    
   - Per creare criteri di archiviazione a livello di utente, fare clic su **Criteri utente**.
    
5. In **Nuovi criteri di archiviazione** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per i nuovi criteri, ad esempio ContosoEsterni.
    
   - In **Descrizione** immettere informazioni dettagliate sugli scopi dei criteri, ad esempio "Criteri di archiviazione degli utenti esterni per Contoso".
    
   - Per controllare l'archiviazione delle comunicazioni con gli utenti interni, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne**.
    
   - Per controllare l'archiviazione delle comunicazioni con gli utenti esterni, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne**.
    
6. Fare clic su **Commit**.
    
    > [!IMPORTANT]
    > Le impostazioni dei criteri utente sono valide solo per gli utenti e i gruppi di utenti specifici a cui vengono applicati i criteri. Per ulteriori informazioni, vedere [applicare un criterio di archiviazione agli utenti in Skype for Business Server](apply-a-policy-to-users.md). 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>Creare un nuovo criterio di archiviazione tramite Windows PowerShell

È inoltre possibile creare nuovi criteri di archiviazione utilizzando il cmdlet **New-CsArchivingPolicy** di Windows PowerShell. Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) .
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>Per creare un nuovo criterio di archiviazione a livello di sito

Questo comando crea nuovi criteri di archiviazione per il sito Redmond:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>Per creare un nuovo criterio di archiviazione a livello di utente

Per creare un nuovo criterio di archiviazione a livello di utente, è sufficiente specificare un'identità univoca quando si crea il criterio:
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>Per creare un nuovo criterio di archiviazione che consenta l'archiviazione delle sessioni di comunicazione interne

Dal momento che nei comandi precedenti non sono stati specificati parametri, oltre al parametro Identity obbligatorio, i nuovi criteri useranno i valori predefiniti per ogni proprietà. Per creare criteri che usano valori di proprietà diversi, includere semplicemente il parametro e il valore di parametro appropriato. Ad esempio, il comando seguente consente di creare un criterio di archiviazione che consenta l'archiviazione delle sessioni di messaggistica istantanea interna: 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>Per creare un nuovo criterio di archiviazione che consenta l'archiviazione delle sessioni di comunicazione interne ed esterne

È possibile modificare più valori di proprietà includendo più parametri. Ad esempio, questo comando consente di configurare il nuovo criterio per l'archiviazione delle sessioni di messaggistica istantanea interne ed esterne:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```
