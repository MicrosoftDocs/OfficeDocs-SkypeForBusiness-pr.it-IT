---
title: Creare un nuovo criterio di archiviazione in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Riepilogo: informazioni su come creare un nuovo criterio di archiviazione per Skype for Business Server.'
---

# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>Creare un nuovo criterio di archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come creare un nuovo criterio di archiviazione per Skype for Business Server.
  
È possibile creare nuovi criteri di archiviazione utilizzando il Pannello di controllo o Windows PowerShell cmdlet.
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>Creare un nuovo criterio di archiviazione utilizzando il Pannello di controllo

Per creare un nuovo criterio di archiviazione utilizzando il Pannello di controllo:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo. 
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.
    
4. Fare clic su **Nuovo** e quindi eseguire una delle operazioni seguenti: 
    
   - Per creare un criterio di archiviazione **a** livello di sito, fare clic su Criteri sito e quindi in Selezionare un sito fare clic sul sito a cui applicare il criterio.
    
   - Per creare criteri di archiviazione a livello di utente, fare clic su **Criteri utente**.
    
5. In **Nuovi criteri di archiviazione** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per i nuovi criteri, ad esempio ContosoEsterni.
    
   - In **Descrizione** immettere informazioni dettagliate sugli scopi dei criteri, ad esempio "Criteri di archiviazione degli utenti esterni per Contoso".
    
   - Per controllare l'archiviazione delle comunicazioni con gli utenti interni, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne**.
    
   - Per controllare l'archiviazione delle comunicazioni con gli utenti esterni, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne**.
    
6. Fare clic su **Commit**.
    
    > [!IMPORTANT]
    > Le impostazioni dei criteri utente sono valide solo per gli utenti e i gruppi di utenti specifici a cui vengono applicati i criteri. Per informazioni dettagliate, vedere [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md). 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>Creare un nuovo criterio di archiviazione tramite Windows PowerShell

È inoltre possibile creare nuovi criteri di archiviazione utilizzando Windows PowerShell **cmdlet New-CsArchivingPolicy**. Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) .
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>Per creare un nuovo criterio di archiviazione a livello di sito

Questo comando crea nuovi criteri di archiviazione per il sito Redmond:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>Per creare un nuovo criterio di archiviazione a livello di singolo utente

Per creare un nuovo criterio di archiviazione a livello di singolo utente, è sufficiente specificare un'identità univoca durante la creazione del criterio:
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>Per creare un nuovo criterio di archiviazione che consenta l'archiviazione delle sessioni di comunicazione interne

Dal momento che nei comandi precedenti non sono stati specificati parametri, oltre al parametro Identity obbligatorio, i nuovi criteri useranno i valori predefiniti per ogni proprietà. Per creare criteri che usano valori di proprietà diversi, includere semplicemente il parametro e il valore di parametro appropriato. Ad esempio, il comando seguente crea un criterio di archiviazione che consente l'archiviazione delle sessioni di messaggistica istantanea interne: 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>Per creare un nuovo criterio di archiviazione che consenta l'archiviazione di sessioni di comunicazione sia interne che esterne

È possibile modificare più valori di proprietà includendo più parametri. Ad esempio, questo comando configura il nuovo criterio per archiviare le sessioni di messaggistica istantanea sia interne che esterne:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```