---
title: Gestione dell'archiviazione in Skype for Business Server
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
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: "Riepilogo: informazioni su come gestire l'archiviazione per Skype for Business Server."
ms.openlocfilehash: 3c84fe35e59d14f957391ecb9bdc503e1bff6b87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817736"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>Gestione dell'archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come gestire l'archiviazione per Skype for Business Server.
  
Quando si distribuisce l'archiviazione per l'organizzazione, è necessario specificare la configurazione iniziale durante la distribuzione. Tuttavia, è possibile che si verifichino momenti in cui si desidera modificare la modalità di implementazione del supporto per l'archiviazione per la gestione quotidiana o per soddisfare i nuovi requisiti per l'organizzazione. Ad esempio, potrebbe essere necessario configurare il supporto per l'archiviazione in modo diverso per un sito specifico, per un pool specifico o per utenti specifici all'interno dell'organizzazione. Per gli utenti ospitati su Skype for Business Server, è necessario creare e personalizzare le opzioni di configurazione di archiviazione e i criteri utente. 
  
Prima di leggere questo argomento, assicurarsi di avere familiarità con le informazioni contenute in [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e [deploy Archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md).
  
> [!NOTE]
> Se si Abilita l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e le cassette postali vengono inserite In-Place blocco. Per ulteriori informazioni, vedere [pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e [configurare l'integrazione con l'archivio di Exchange per Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="archiving-configuration-options"></a>Opzioni di configurazione dell'archiviazione

Le opzioni di configurazione di archiviazione specificano se:
  
- Abilitare o disabilitare l'archiviazione
    
- Archivia sessioni di messaggistica istantanea
    
- Sessioni di Web Conferencing di archiviazione
    
- Blocca attività quando l'archiviazione non è disponibile
    
- Utilizzo dell'integrazione di Exchange
    
- Configurare l'eliminazione e l'esportazione dei dati
    
Queste opzioni possono essere impostate a livello globale, di sito o di pool. Per ulteriori informazioni, vedere [gestire le opzioni di archiviazione in Skype for Business Server](options.md).
  
## <a name="archiving-policies"></a>Criteri di archiviazione

I criteri di archiviazione determinano se archiviare gli elementi seguenti:
  
- Comunicazioni interne
    
- Comunicazioni esterne
    
Questi criteri possono essere impostati a livello globale, del sito o dell'utente. Per ulteriori informazioni, vedere [gestire i criteri di archiviazione in Skype for Business Server](policies.md).
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Gestire l'archiviazione tramite il pannello di controllo oppure tramite Windows PowerShell

È possibile gestire l'archiviazione tramite il pannello di controllo oppure tramite Windows PowerShell. Nella tabella seguente sono riepilogati i cmdlet disponibili per la gestione dell'archiviazione. Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, vedere [Skype for Business Server Management Shell](../management-shell.md). 


|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Esporta i record archiviati nel database di archiviazione di Skype for Business Server.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Restituisce informazioni sulle impostazioni di configurazione dell'archiviazione nell'organizzazione.  <br/> |
|Get-CsArchivingPolicy  <br/> |Restituisce informazioni sui criteri di archiviazione dell'organizzazione per le comunicazioni interne ed esterne.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Consente di assegnare criteri di archiviazione delle sessioni di messaggistica istantanea agli utenti o ai gruppi di utenti. Tali criteri consentono di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e partner esterni.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |Elimina manualmente record dal database di archiviazione.  <br/> |
|New-CsArchivingConfiguration  <br/> |Crea un nuovo set di impostazioni di messaggistica istantanea, che può essere utilizzato per abilitare o disabilitare il salvataggio automatico delle sessioni di messaggistica istantanea e per bloccare tutti i messaggi istantanei che non possono essere archiviati.  <br/> |
|New-CsArchivingPolicy  <br/> |Crea nuovi criteri di archiviazione per sessioni di messaggistica istantanea. Tali criteri consentono di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e partner esterni.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Rimuove la raccolta specificata di impostazioni di archiviazione utilizzate per abilitare o disabilitare il salvataggio automatico delle sessioni di messaggistica istantanea e, facoltativamente, per bloccare tutti i messaggi istantanei che non possono essere archiviati.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Rimuove il criterio di archiviazione dei messaggi istantanei specificato che determina se Skype for Business Server salverà automaticamente tutte le sessioni di messaggistica istantanea che si verificano tra gli utenti interni e/o tutte le sessioni di messaggistica istantanea tra gli utenti interni e i partner federati.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica una raccolta esistente di opzioni di configurazione di archiviazione di messaggistica istantanea (IM).  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica un criterio di archiviazione di messaggistica istantanea esistente. I criteri di archiviazione offrono la possibilità di archiviare tutte le sessioni di messaggistica istantanea e le conferenze che si verificano tra gli utenti interni; è inoltre possibile archiviare le sessioni che si verificano tra gli utenti interni e i partner federati.  <br/> |
|Set-CsArchivingServer  <br/> |Consente di specificare un nuovo percorso di database per uno o più server di archiviazione.  <br/> |
   

