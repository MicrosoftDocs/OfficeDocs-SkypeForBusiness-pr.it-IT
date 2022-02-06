---
title: Gestire l'archiviazione in Skype for Business Server
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
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 'Riepilogo: informazioni su come gestire l''archiviazione per Skype for Business Server.'
---

# <a name="manage-archiving-in-skype-for-business-server"></a>Gestire l'archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come gestire l'archiviazione per Skype for Business Server.
  
Quando si distribuisce l'archiviazione per l'organizzazione, si specifica la configurazione iniziale durante la distribuzione. In alcuni casi, tuttavia, potrebbe essere necessario modificare la modalità di implementazione del supporto di archiviazione per la gestione quotidiana o soddisfare nuovi requisiti per l'organizzazione. Ad esempio, potrebbe essere necessario configurare il supporto dell'archiviazione in modo diverso per un sito specifico, un pool specifico o utenti specifici all'interno dell'organizzazione. Per gli utenti ospitati in Skype for Business Server, è possibile creare e personalizzare le opzioni di configurazione dell'archiviazione e i criteri utente. 
  
Prima di leggere questo argomento, assicurarsi di avere familiarità con le informazioni contenute in [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) [and Deploy archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md).
  
> [!NOTE]
> Se si abilita l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e che le cassette postali vengono abilitate In-Place archiviazione. Per informazioni dettagliate, vedere [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="archiving-configuration-options"></a>Opzioni di configurazione dell'archiviazione

Le opzioni di configurazione dell'archiviazione specificano se:
  
- Abilitare o disabilitare l'archiviazione
    
- Archivia sessioni di messaggistica istantanea
    
- Archiviare le sessioni di conferenza Web
    
- Blocca attività quando l'archiviazione non è disponibile
    
- Usare Exchange integrazione
    
- Configurare l'eliminazione e l'esportazione dei dati
    
Queste opzioni possono essere impostate a livello globale, di sito o di pool. Per ulteriori informazioni, vedere [Manage archiving options in Skype for Business Server](options.md).
  
## <a name="archiving-policies"></a>Criteri di archiviazione

I criteri di archiviazione determinano se archiviare quanto segue:
  
- Comunicazioni interne
    
- Comunicazioni esterne
    
Questi criteri possono essere impostati a livello globale, di sito o di utente. Per ulteriori informazioni, vedere [Manage archiving policies in Skype for Business Server](policies.md).
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Gestire l'archiviazione tramite il Pannello di controllo o tramite Windows PowerShell

È possibile gestire l'archiviazione utilizzando il Pannello di controllo o Windows PowerShell. Nella tabella seguente sono riepilogati i cmdlet disponibili per la gestione dell'archiviazione. Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, [vedere Skype for Business Server Management Shell](../management-shell.md). 


|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Esporta i record archiviati nel database Skype for Business Server di archiviazione.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Restituisce informazioni sulle impostazioni di configurazione dell'archiviazione nell'organizzazione.  <br/> |
|Get-CsArchivingPolicy  <br/> |Restituisce informazioni sui criteri di archiviazione dell'organizzazione per le comunicazioni interne ed esterne.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Assegna i criteri di archiviazione delle sessioni di messaggistica istantanea agli utenti o ai set di utenti. Tali criteri consentono di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e partner esterni.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |Elimina manualmente record dal database di archiviazione.  <br/> |
|New-CsArchivingConfiguration  <br/> |Crea un nuovo set di impostazioni di messaggistica istantanea, che possono essere utilizzate per abilitare o disabilitare il salvataggio automatico delle sessioni di messaggistica istantanea e per bloccare eventuali messaggi istantanei che non possono essere archiviati.  <br/> |
|New-CsArchivingPolicy  <br/> |Crea nuovi criteri di archiviazione per sessioni di messaggistica istantanea. Tali criteri consentono di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e partner esterni.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Rimuove la raccolta specificata di impostazioni di archiviazione utilizzate per abilitare o disabilitare il salvataggio automatico delle sessioni di messaggistica istantanea e per bloccare facoltativamente i messaggi istantanei che non possono essere archiviati.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Rimuove il criterio di archiviazione della messaggistica istantanea specificato che determina se Skype for Business Server salverà automaticamente tutte le sessioni di messaggistica istantanea tra utenti interni e/o tutte le sessioni di messaggistica istantanea tra utenti interni e partner federati.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica una raccolta esistente di opzioni di configurazione dell'archiviazione di messaggistica istantanea.  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica un criterio di archiviazione di messaggistica istantanea esistente. I criteri di archiviazione consentono di archiviare tutte le sessioni di messaggistica istantanea e le conferenze che si svolgono tra utenti interni. è inoltre possibile archiviare le sessioni che si svolgono tra utenti interni e partner federati.  <br/> |
|Set-CsArchivingServer  <br/> |Consente di specificare un nuovo percorso di database per uno o più server di archiviazione.  <br/> |
   

