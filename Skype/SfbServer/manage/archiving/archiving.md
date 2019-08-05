---
title: Gestire l'archiviazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: "Riepilogo: informazioni su come gestire l'archiviazione per Skype for Business Server."
ms.openlocfilehash: e4566760a9d071b87596e581689f6373ca3cda49
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189350"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>Gestire l'archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come gestire l'archiviazione per Skype for Business Server.
  
Quando si distribuisce l'archiviazione per l'organizzazione, è necessario specificare la configurazione iniziale durante la distribuzione. In alcuni casi, tuttavia, può essere necessario modificare la modalità di implementazione del supporto dell'archiviazione per la gestione giornaliera o per soddisfare i nuovi requisiti per l'organizzazione. Ad esempio, potrebbe essere necessario configurare il supporto per l'archiviazione in modo diverso per un sito specifico, un pool specifico o utenti specifici all'interno dell'organizzazione. Per gli utenti residenti in Skype for Business Server, è possibile creare e personalizzare le opzioni di configurazione dell'archiviazione e i criteri degli utenti. 
  
Prima di leggere questo argomento, accertarsi di avere familiarità con le informazioni in [piano per l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e [distribuire l'archiviazione per Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md).
  
> [!NOTE]
> Se si Abilita l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e le cassette postali vengono messe sul posto. Per informazioni dettagliate, vedere [pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e [configurare l'integrazione con lo spazio di archiviazione di Exchange per Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="archiving-configuration-options"></a>Opzioni di configurazione dell'archiviazione

Le opzioni di configurazione dell'archiviazione specificano se:
  
- Abilitare o disabilitare l'archiviazione
    
- Archivia sessioni di messaggistica istantanea
    
- Sessioni di Web Conferencing di archiviazione
    
- Bloccare l'attività quando l'archiviazione non è disponibile
    
- Usare l'integrazione di Exchange
    
- Configurare l'eliminazione e l'esportazione dei dati
    
Queste opzioni possono essere impostate a livello globale, del sito o del pool. Per altre informazioni, vedere [gestire le opzioni di archiviazione in Skype for Business Server](options.md).
  
## <a name="archiving-policies"></a>Criteri di archiviazione

I criteri di archiviazione determinano se archiviare gli elementi seguenti:
  
- Comunicazioni interne
    
- Comunicazioni esterne
    
Questi criteri possono essere impostati a livello globale, del sito o dell'utente. Per altre informazioni, vedere [gestire i criteri di archiviazione in Skype for Business Server](policies.md).
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Gestire l'archiviazione tramite il pannello di controllo o tramite Windows PowerShell

È possibile gestire l'archiviazione tramite il pannello di controllo o tramite Windows PowerShell. La tabella seguente riepiloga i cmdlet disponibili per facilitare la gestione dell'archiviazione. Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, Vedi [Skype for Business Server Management Shell](../management-shell.md). 


|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Esporta i record archiviati nel database di archiviazione di Skype for Business Server.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Restituisce informazioni sulle impostazioni di configurazione dell'archiviazione nell'organizzazione.  <br/> |
|Get-CsArchivingPolicy  <br/> |Restituisce informazioni sui criteri di archiviazione dell'organizzazione per le comunicazioni interne ed esterne.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Assegna criteri di archiviazione delle sessioni di messaggistica istantanea a utenti o gruppi di utenti. Questi criteri offrono la possibilità di archiviare tutte le sessioni di messaggistica istantanea che si svolgono tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea che si svolgono tra utenti interni e partner esterni.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |Elimina manualmente record dal database di archiviazione.  <br/> |
|New-CsArchivingConfiguration  <br/> |Crea un nuovo set di impostazioni di messaggistica istantanea, che può essere usato per abilitare o disabilitare il salvataggio automatico delle sessioni di messaggistica istantanea e per bloccare i messaggi istantanei che non possono essere archiviati.  <br/> |
|New-CsArchivingPolicy  <br/> |Crea nuovi criteri di archiviazione della sessione messaggistica istantanea. Questi criteri offrono la possibilità di archiviare tutte le sessioni di messaggistica istantanea che si svolgono tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea che si svolgono tra utenti interni e partner esterni.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Rimuove la raccolta specificata di impostazioni di archiviazione usate per abilitare o disabilitare il salvataggio automatico delle sessioni di messaggistica istantanea e per bloccare facoltativamente qualsiasi messaggio istantaneo che non può essere archiviato.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Rimuove i criteri di archiviazione di messaggistica istantanea specificati che determinano se Skype for Business Server Salva automaticamente tutte le sessioni di messaggistica istantanea che si svolgono tra utenti interni e/o tutte le sessioni di messaggistica istantanea tra utenti interni e partner federati.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica una raccolta esistente di opzioni di configurazione dell'archiviazione di messaggistica istantanea (IM).  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica un criterio di archiviazione della messaggistica istantanea esistente. Un criterio di archiviazione offre la possibilità di archiviare tutte le sessioni di messaggistica istantanea e le conferenze che si svolgono tra gli utenti interni; è anche possibile archiviare le sessioni che si svolgono tra utenti interni e partner federati.  <br/> |
|Set-CsArchivingServer  <br/> |Consente di specificare un nuovo percorso del database per uno o più server di archiviazione.  <br/> |
   

