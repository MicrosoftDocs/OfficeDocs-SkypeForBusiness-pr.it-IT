---
title: Modificare un criterio di archiviazione esistente in Skype for Business Server
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
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Riepilogo: informazioni su come modificare i criteri di archiviazione degli utenti per Skype for Business Server.'
---

# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>Modificare un criterio di archiviazione esistente in Skype for Business Server
 
**Riepilogo:** Informazioni su come modificare i criteri di archiviazione degli utenti per Skype for Business Server.
  
Quando si distribuisce per la Skype for Business Server, si impostano i criteri di archiviazione iniziali che determinano la modalità di implementazione dell'archiviazione per gli utenti nella distribuzione. In questo argomento viene descritto come gestire e modificare i criteri. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>Modificare i criteri di archiviazione tramite il Pannello di controllo

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo. 
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.
    
4. Nell'elenco dei criteri eseguire una delle operazioni seguenti: 
    
   - Per modificare i criteri per l'intera distribuzione, fare clic su **Globale** nell'elenco dei criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.
    
   - Per modificare i criteri per un singolo sito, fare clic sul nome del sito nell'elenco dei criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.
    
   - Per modificare i criteri per un singolo utente o gruppo di utenti, fare clic sul nome dell'utente o del gruppo di utenti nell'elenco dei criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.
    
5. Nella pagina **Modifica Criteri di archiviazione** eseguire le operazioni seguenti:
    
   - Per abilitare o disabilitare l'archiviazione interna per i criteri, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne**.
    
   - Per abilitare o disabilitare l'archiviazione esterna per i criteri, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne**.
    
6. Fare clic su **Commit**.
    
    > [!IMPORTANT]
    > Le impostazioni dei criteri utente sono valide solo per gli utenti e i gruppi di utenti specifici a cui vengono applicati i criteri. Per informazioni dettagliate, vedere [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md). 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>Modificare i criteri di archiviazione tramite Windows PowerShell

È inoltre possibile modificare i criteri di archiviazione utilizzando Windows PowerShell **cmdlet Set-CsArchivingPolicy**.
  
### <a name="enable-archiving-policies"></a>Abilitare i criteri di archiviazione

Per abilitare l'archiviazione delle sessioni di comunicazione interne, impostare il valore del parametro ArchiveInternal su True ($True): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

Per abilitare l'archiviazione delle sessioni di comunicazione esterne, impostare il valore del parametro ArchiveExternal su True ($True): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

Per abilitare l'archiviazione delle sessioni di comunicazione sia interne che esterne, impostare il valore dei parametri ArchiveInternal e ArchiveExternal su True: 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>Disabilitare i criteri di archiviazione

Per disabilitare completamente l'archiviazione, impostare il valore dei parametri ArchiveInternal e ArchiveExternal su False ($False): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
