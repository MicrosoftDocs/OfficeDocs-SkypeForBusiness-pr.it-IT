---
title: Gestire i criteri di archiviazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: "Riepilogo: informazioni su come gestire i criteri degli utenti per l'archiviazione per Skype for Business Server."
ms.openlocfilehash: f6918907f73ffe1b098ed96e1997d8ab8ffe4f9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188213"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>Gestire i criteri di archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come gestire i criteri degli utenti per l'archiviazione per Skype for Business Server.
  
I criteri di archiviazione sono stati inizialmente impostati quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare configurazioni dopo la distribuzione. I criteri di archiviazione determinano se eseguire l'archiviazione: 
  
- Comunicazioni interne
    
- Comunicazioni esterne
    
I criteri di archiviazione possono essere impostati a livello globale, del sito o dell'utente.
  
> [!NOTE]
> Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e le cassette postali vengono messe sul posto. Per informazioni dettagliate, vedere [pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e [configurare l'integrazione con lo spazio di archiviazione di Exchange per Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>Gestire i criteri di archiviazione tramite il pannello di controllo

È possibile gestire i criteri di archiviazione usando il pannello di controllo come indicato di seguito:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **criteri di archiviazione**
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Gestire i criteri di archiviazione tramite Windows PowerShell

È anche possibile configurare i criteri di archiviazione usando i cmdlet di Windows PowerShell elencati nella tabella seguente. Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, Vedi [Skype for Business Server Management Shell](../management-shell.md).
  

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |Restituisce informazioni sui criteri di archiviazione delle sessioni di messaggistica istantanea (IM) dell'organizzazione.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Assegna criteri di archiviazione delle sessioni di messaggistica istantanea a utenti o gruppi di utenti. Questi criteri offrono la possibilità di archiviare tutte le sessioni di messaggistica istantanea che si svolgono tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea che si svolgono tra utenti interni e partner esterni.  <br/> |
|New-CsArchivingPolicy  <br/> |Crea nuovi criteri di archiviazione della sessione messaggistica istantanea. Questi criteri offrono la possibilità di archiviare tutte le sessioni di messaggistica istantanea che si svolgono tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea che si svolgono tra utenti interni e partner esterni.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Rimuove i criteri di archiviazione di messaggistica istantanea specificati che determinano se Skype for Business Server Salva automaticamente tutte le sessioni di messaggistica istantanea che si svolgono tra utenti interni e/o tutte le sessioni di messaggistica istantanea tra utenti interni e partner federati.  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica un criterio di archiviazione della messaggistica istantanea esistente. Un criterio di archiviazione offre la possibilità di archiviare tutte le sessioni di messaggistica istantanea e le conferenze che si svolgono tra gli utenti interni; è anche possibile archiviare le sessioni che si svolgono tra utenti interni e partner federati.  <br/> |
   

