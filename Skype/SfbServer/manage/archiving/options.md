---
title: Gestire le opzioni di archiviazione in Skype for Business Server
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
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Riepilogo: informazioni su come configurare le opzioni di archiviazione per Skype for Business Server.'
---

# <a name="manage-archiving-options-in-skype-for-business-server"></a>Gestire le opzioni di archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come configurare le opzioni di archiviazione per Skype for Business Server.
  
L'archiviazione viene inizialmente configurata durante la distribuzione, ma è possibile modificare, aggiungere ed eliminare configurazioni dopo la distribuzione. Le opzioni di archiviazione determinano se: 
  
- Abilitare o disabilitare l'archiviazione
    
- Archivia sessioni di messaggistica istantanea
    
- Archiviare le sessioni di conferenza Web
    
- Blocca attività quando l'archiviazione non è disponibile
    
- Usare Exchange integrazione
    
- Configurare l'eliminazione e l'esportazione dei dati
    
È possibile specificare le opzioni di configurazione nei livelli seguenti:
  
- Configurazione a livello globale creata per impostazione predefinita quando si distribuisce Skype for Business Server
    
- Configurazioni facoltative a livello di sito che specificano la modalità di implementazione dell'archiviazione per un sito specifico
    
- Configurazioni facoltative a livello di pool che specificano la modalità di implementazione dell'archiviazione per un pool specifico
    
È possibile eliminare una configurazione di sito o di pool, ma non è possibile eliminare la configurazione globale. Se si elimina la configurazione globale, viene reimpostata automaticamente sui valori predefiniti. Per informazioni dettagliate sull'implementazione delle configurazioni di archiviazione e sulla gerarchia delle configurazioni di archiviazione, vedere [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurare le opzioni di archiviazione tramite il Pannello di controllo

È possibile configurare le opzioni di archiviazione utilizzando il Pannello di controllo nel modo seguente:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo. 
    
3. Sulla barra di spostamento sinistra fare clic su **Configurazione archiviazione**.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configurare le opzioni di archiviazione tramite Windows PowerShell

È inoltre possibile configurare le opzioni di archiviazione utilizzando i cmdlet Windows PowerShell elencati nella tabella seguente. Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, [vedere Skype for Business Server Management Shell](../management-shell.md).
  

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |Restituisce informazioni sulle impostazioni di configurazione dell'archiviazione nell'organizzazione.  <br/> |
|New-CsArchivingConfiguration  <br/> |Crea un nuovo set di impostazioni di messaggistica istantanea, che possono essere utilizzate per abilitare o disabilitare il salvataggio automatico delle sessioni di messaggistica istantanea e per bloccare eventuali messaggi istantanei che non possono essere archiviati.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Rimuove la raccolta specificata di impostazioni di archiviazione utilizzate per abilitare o disabilitare il salvataggio automatico delle sessioni di messaggistica istantanea e per bloccare facoltativamente i messaggi istantanei che non possono essere archiviati.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica una raccolta esistente di opzioni di configurazione dell'archiviazione di messaggistica istantanea.  <br/> |
