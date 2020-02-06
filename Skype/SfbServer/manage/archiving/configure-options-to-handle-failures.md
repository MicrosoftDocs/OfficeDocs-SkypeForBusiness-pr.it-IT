---
title: Configurare le opzioni di archiviazione per gestire gli errori in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: "Riepilogo: informazioni su come bloccare le sessioni di messaggistica istantanea e di conferenza nel caso di un errore di Skype for Business Server che impedisce l'archiviazione."
ms.openlocfilehash: c1a6b9930d9f27e9d679710708141c0394c41dc4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818968"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Configurare le opzioni di archiviazione per gestire gli errori in Skype for Business Server

**Riepilogo:** Informazioni su come bloccare le sessioni di messaggistica istantanea e di conferenza nel caso di un errore di Skype for Business Server che impedirebbe l'archiviazione.
  
Se l'archiviazione è un requisito per l'organizzazione, è possibile bloccare le sessioni di messaggistica istantanea e di conferenza in caso di errore di Skype for Business Server che impedirebbe l'archiviazione. Questa operazione viene talvolta chiamata modalità critica. Ad esempio, se si verifica un problema con un servizio di archiviazione, la messaggistica istantanea verrebbe bloccata per gli utenti le cui comunicazioni sono abilitate per l'archiviazione. Sia la funzionalità di messaggistica istantanea che il servizio di conferenza vengono ripristinati automaticamente subito dopo la correzione degli errori. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Configurare la modalità critica tramite il pannello di controllo

Per specificare se le sessioni di comunicazione devono essere consentite in caso di errore che impedirebbe l'archiviazione:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.
    
4. Fare clic sul nome della configurazione globale, del sito o del pool appropriata nell'elenco delle configurazioni di archiviazione, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
5. Per impostare la modalità di funzionamento dell'archiviazione quando si verifica un errore, selezionare o deselezionare la casella di controllo **Blocca messaggistica istantanea o sessioni di conferenza Web se l'archiviazione non riesce** .
    
6. Fare clic su **Commit**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Configurare la modalità critica tramite Windows PowerShell

Puoi anche specificare se le sessioni di comunicazione devono essere consentite in caso di un errore che impedirebbe l'archiviazione usando il cmdlet **Set-CsArchivingConfiguration** con il parametro BlockOnArchiveFailure.
  
Ad esempio, il comando seguente disabilita le comunicazioni in caso di errore di archiviazione:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

Il comando successivo consente di abilitare le comunicazioni in caso di errore di archiviazione:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) .
  

