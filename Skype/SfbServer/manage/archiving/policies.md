---
title: Gestire i criteri di archiviazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: "Riepilogo: informazioni su come gestire i criteri utente per l'archiviazione per Skype for Business Server."
ms.openlocfilehash: 949ac807faea4f563ee078512a3c0a335a517d2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828551"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>Gestire i criteri di archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come gestire i criteri utente per l'archiviazione per Skype for Business Server.
  
I criteri di archiviazione vengono inizialmente impostati quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare configurazioni dopo la distribuzione. I criteri di archiviazione determinano se archiviare: 
  
- Comunicazioni interne
    
- Comunicazioni esterne
    
I criteri di archiviazione possono essere impostati a livello globale, di sito o di utente.
  
> [!NOTE]
> Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e le cassette postali vengono In-Place archiviazione. Per informazioni dettagliate, vedere [Pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e Configurare l'integrazione con l'archiviazione di Exchange per Skype for Business [Server.](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md) 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>Gestire i criteri di archiviazione tramite il Pannello di controllo

È possibile gestire i criteri di archiviazione utilizzando il Pannello di controllo nel modo seguente:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna. 
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **Criteri di archiviazione**
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Gestire i criteri di archiviazione tramite Windows PowerShell

È inoltre possibile configurare i criteri di archiviazione utilizzando Windows PowerShell cmdlet elencati nella tabella seguente. Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, vedere [Skype for Business Server Management Shell.](../management-shell.md)
  

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |Restituisce informazioni sui criteri di archiviazione delle sessioni di messaggistica istantanea dell'organizzazione.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Assegna i criteri di archiviazione delle sessioni di messaggistica istantanea agli utenti o ai set di utenti. Tali criteri consentono di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e partner esterni.  <br/> |
|New-CsArchivingPolicy  <br/> |Crea nuovi criteri di archiviazione per sessioni di messaggistica istantanea. Tali criteri consentono di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e partner esterni.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Rimuove il criterio di archiviazione della messaggistica istantanea specificato che determina se Skype for Business Server salverà automaticamente tutte le sessioni di messaggistica istantanea tra utenti interni e/o tutte le sessioni di messaggistica istantanea tra utenti interni e partner federati.  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica un criterio di archiviazione di messaggistica istantanea esistente. I criteri di archiviazione consentono di archiviare tutte le sessioni di messaggistica istantanea e le conferenze che si svolgono tra utenti interni; è inoltre possibile archiviare le sessioni che si svolgono tra utenti interni e partner federati.  <br/> |
   

