---
title: Gestire le opzioni di archiviazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Riepilogo: informazioni su come configurare le opzioni di archiviazione per Skype for Business Server.'
ms.openlocfilehash: c7353c305125e8e35523c573150471821f53301e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188222"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>Gestire le opzioni di archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come configurare le opzioni di archiviazione per Skype for Business Server.
  
L'archiviazione viene inizialmente configurata in fase di distribuzione, ma è possibile modificare, aggiungere ed eliminare configurazioni dopo la distribuzione. Le opzioni di archiviazione determinano se: 
  
- Abilitare o disabilitare l'archiviazione
    
- Archivia sessioni di messaggistica istantanea
    
- Sessioni di Web Conferencing di archiviazione
    
- Bloccare l'attività quando l'archiviazione non è disponibile
    
- Usare l'integrazione di Exchange
    
- Configurare l'eliminazione e l'esportazione dei dati
    
È possibile specificare le opzioni di configurazione ai livelli seguenti:
  
- Configurazione a livello globale creata per impostazione predefinita quando si distribuisce Skype for Business Server
    
- Configurazioni facoltative a livello di sito che specificano la modalità di implementazione dell'archiviazione per un sito specifico
    
- Configurazioni facoltative a livello di pool che specificano la modalità di implementazione dell'archiviazione per un pool specifico
    
È possibile eliminare una configurazione del sito o una configurazione del pool, ma non è possibile eliminare la configurazione globale. Se elimini la configurazione globale, viene reimpostata automaticamente sui valori predefiniti. Per informazioni dettagliate sull'implementazione delle configurazioni di archiviazione e sulla gerarchia delle configurazioni di archiviazione, vedere [pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurare le opzioni di archiviazione tramite il pannello di controllo

È possibile configurare le opzioni di archiviazione usando il pannello di controllo come indicato di seguito:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **Configurazione archiviazione**.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configurare le opzioni di archiviazione tramite Windows PowerShell

È anche possibile configurare le opzioni di archiviazione usando i cmdlet di Windows PowerShell elencati nella tabella seguente. Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, Vedi [Skype for Business Server Management Shell](../management-shell.md).
  

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |Restituisce informazioni sulle impostazioni di configurazione dell'archiviazione nell'organizzazione.  <br/> |
|New-CsArchivingConfiguration  <br/> |Crea un nuovo set di impostazioni di messaggistica istantanea, che può essere usato per abilitare o disabilitare il salvataggio automatico delle sessioni di messaggistica istantanea e per bloccare i messaggi istantanei che non possono essere archiviati.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Rimuove la raccolta specificata di impostazioni di archiviazione usate per abilitare o disabilitare il salvataggio automatico delle sessioni di messaggistica istantanea e per bloccare facoltativamente qualsiasi messaggio istantaneo che non può essere archiviato.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica una raccolta esistente di opzioni di configurazione dell'archiviazione di messaggistica istantanea (IM).  <br/> |
