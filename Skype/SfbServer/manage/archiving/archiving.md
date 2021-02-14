---
title: Gestire l'archiviazione in Skype for Business Server
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
# <a name="manage-archiving-in-skype-for-business-server"></a>Gestire l'archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come gestire l'archiviazione per Skype for Business Server.
  
Quando si distribuisce l'archiviazione per l'organizzazione, è necessario specificare la configurazione iniziale durante la distribuzione. In alcuni casi, tuttavia, potrebbe essere necessario modificare la modalità di implementazione del supporto dell'archiviazione per la gestione quotidiana o per soddisfare nuovi requisiti per l'organizzazione. Ad esempio, potrebbe essere necessario configurare il supporto dell'archiviazione in modo diverso per un sito specifico, un pool specifico o utenti specifici all'interno dell'organizzazione. Per gli utenti ospitati in Skype for Business Server, è possibile farlo creando e personalizzando le opzioni di configurazione dell'archiviazione e i criteri utente. 
  
Prima di leggere questo argomento, assicurarsi di avere familiarità con le informazioni contenute in Pianificare l'archiviazione [in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e distribuire l'archiviazione per Skype for Business [Server.](../../deploy/deploy-archiving/deploy-archiving.md)
  
> [!NOTE]
> Se si abilita l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e le cassette postali vengono In-Place archiviazione. Per informazioni dettagliate, vedere [Pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e Configurare l'integrazione con l'archiviazione di Exchange per Skype for Business [Server.](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md) 
  
## <a name="archiving-configuration-options"></a>Opzioni di configurazione dell'archiviazione

Le opzioni di configurazione dell'archiviazione specificano se:
  
- Abilitare o disabilitare l'archiviazione
    
- Archivia sessioni di messaggistica istantanea
    
- Archiviare le sessioni di Web Conferencing
    
- Bloccare l'attività quando l'archiviazione non è disponibile
    
- Utilizzare l'integrazione di Exchange
    
- Configurare l'eliminazione e l'esportazione dei dati
    
Queste opzioni possono essere impostate a livello globale, di sito o di pool. Per ulteriori informazioni, vedere [Gestire le opzioni di archiviazione in Skype for Business Server.](options.md)
  
## <a name="archiving-policies"></a>Criteri di archiviazione

I criteri di archiviazione determinano se archiviare quanto segue:
  
- Comunicazioni interne
    
- Comunicazioni esterne
    
Questi criteri possono essere impostati a livello globale, di sito o di utente. Per ulteriori informazioni, vedere [Gestire i criteri di archiviazione in Skype for Business Server.](policies.md)
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Gestire l'archiviazione utilizzando il Pannello di controllo o Windows PowerShell

È possibile gestire l'archiviazione utilizzando il Pannello di controllo o Windows PowerShell. Nella tabella seguente sono riepilogati i cmdlet disponibili per la gestione dell'archiviazione. Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, vedere [Skype for Business Server Management Shell.](../management-shell.md) 


|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Esporta i record archiviati nel database di archiviazione di Skype for Business Server.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Restituisce informazioni sulle impostazioni di configurazione dell'archiviazione nell'organizzazione.  <br/> |
|Get-CsArchivingPolicy  <br/> |Restituisce informazioni sui criteri di archiviazione dell'organizzazione per le comunicazioni interne ed esterne.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Assegna i criteri di archiviazione delle sessioni di messaggistica istantanea agli utenti o ai set di utenti. Tali criteri consentono di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e partner esterni.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |Elimina manualmente record dal database di archiviazione.  <br/> |
|New-CsArchivingConfiguration  <br/> |Crea un nuovo set di impostazioni di messaggistica istantanea, che può essere utilizzato per abilitare o disabilitare il salvataggio automatico delle sessioni di messaggistica istantanea e per bloccare i messaggi istantanei che non possono essere archiviati.  <br/> |
|New-CsArchivingPolicy  <br/> |Crea nuovi criteri di archiviazione per sessioni di messaggistica istantanea. Tali criteri consentono di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e partner esterni.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Rimuove la raccolta specificata di impostazioni di archiviazione utilizzate per abilitare o disabilitare il salvataggio automatico delle sessioni di messaggistica istantanea e per bloccare facoltativamente i messaggi istantanei che non possono essere archiviati.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Rimuove il criterio di archiviazione della messaggistica istantanea specificato che determina se Skype for Business Server salverà automaticamente tutte le sessioni di messaggistica istantanea tra utenti interni e/o tutte le sessioni di messaggistica istantanea tra utenti interni e partner federati.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica una raccolta esistente di opzioni di configurazione dell'archiviazione di messaggistica istantanea.  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica un criterio di archiviazione di messaggistica istantanea esistente. I criteri di archiviazione consentono di archiviare tutte le sessioni di messaggistica istantanea e le conferenze che si svolgono tra utenti interni; è inoltre possibile archiviare le sessioni che si svolgono tra utenti interni e partner federati.  <br/> |
|Set-CsArchivingServer  <br/> |Consente di specificare un nuovo percorso di database per uno o più server di archiviazione.  <br/> |
   

