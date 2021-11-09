---
title: Gestire i criteri di archiviazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: "Riepilogo: informazioni su come gestire i criteri utente per l'archiviazione per Skype for Business Server."
ms.openlocfilehash: aefb05c4ee1be0af0af4d2ab4ab4d53efbd71912
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856763"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>Gestire i criteri di archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come gestire i criteri utente per l'archiviazione per Skype for Business Server.
  
I criteri di archiviazione vengono inizialmente impostati quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare configurazioni dopo la distribuzione. I criteri di archiviazione determinano se archiviare: 
  
- Comunicazioni interne
    
- Comunicazioni esterne
    
I criteri di archiviazione possono essere impostati a livello globale, di sito o di utente.
  
> [!NOTE]
> Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e che le cassette postali vengono In-Place conservazione. Per informazioni dettagliate, vedere [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e Configure integration with Exchange storage for [Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>Gestire i criteri di archiviazione tramite il Pannello di controllo

È possibile gestire i criteri di archiviazione utilizzando il Pannello di controllo come segue:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo. 
    
3. Sulla barra di spostamento sinistra fare clic su **Criteri di archiviazione**
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Gestire i criteri di archiviazione tramite Windows PowerShell

È inoltre possibile configurare i criteri di archiviazione utilizzando i cmdlet Windows PowerShell elencati nella tabella seguente. Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, [vedere Skype for Business Server Management Shell](../management-shell.md).
  

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |Restituisce informazioni sui criteri di archiviazione delle sessioni di messaggistica istantanea dell'organizzazione.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Assegna i criteri di archiviazione delle sessioni di messaggistica istantanea agli utenti o ai set di utenti. Tali criteri consentono di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e partner esterni.  <br/> |
|New-CsArchivingPolicy  <br/> |Crea nuovi criteri di archiviazione per sessioni di messaggistica istantanea. Tali criteri consentono di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e partner esterni.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Rimuove il criterio di archiviazione della messaggistica istantanea specificato che determina se Skype for Business Server salverà automaticamente tutte le sessioni di messaggistica istantanea tra utenti interni e/o tutte le sessioni di messaggistica istantanea tra utenti interni e partner federati.  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica un criterio di archiviazione di messaggistica istantanea esistente. I criteri di archiviazione consentono di archiviare tutte le sessioni di messaggistica istantanea e le conferenze che si svolgono tra utenti interni. è inoltre possibile archiviare le sessioni che si svolgono tra utenti interni e partner federati.  <br/> |
   

