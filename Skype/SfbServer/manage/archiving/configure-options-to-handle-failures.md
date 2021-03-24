---
title: Configurare le opzioni di archiviazione per gestire gli errori in Skype for Business Server
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
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: "Riepilogo: informazioni su come bloccare le sessioni di messaggistica istantanea e di conferenza in caso di errore di Skype for Business Server che impedirebbe l'archiviazione."
ms.openlocfilehash: 8bfe4d3f8e02fa0d7d7d3f1f6b55f224aaa1451a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095450"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Configurare le opzioni di archiviazione per gestire gli errori in Skype for Business Server

**Riepilogo:** Informazioni su come bloccare le sessioni di messaggistica istantanea e conferenza in caso di errore di Skype for Business Server che impedirebbe l'archiviazione.
  
Se l'archiviazione è un requisito per l'organizzazione, è possibile bloccare le sessioni di messaggistica istantanea e conferenza in caso di un errore di Skype for Business Server che impedirebbe l'archiviazione. Questa operazione viene talvolta definita modalità critica. Ad esempio, se si verifica un problema con un servizio di archiviazione, la messaggistica istantanea verrà bloccata per gli utenti le cui comunicazioni sono abilitate per l'archiviazione. Sia la funzionalità di messaggistica immediata che il servizio di conferenza vengono ripristinati automaticamente subito dopo la correzione degli errori. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Configurare la modalità critica tramite il Pannello di controllo

Per specificare se le sessioni di comunicazione devono essere consentite in caso di errore che impedisse l'archiviazione:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.
    
4. Fare clic sul nome della configurazione globale, del sito o del pool appropriata nell'elenco delle configurazioni di archiviazione, fare clic su Modifica **e** quindi su **Mostra dettagli.**
    
5. Per impostare il comportamento dell'archiviazione quando si verifica un errore, selezionare o deselezionare la casella di controllo Blocca sessioni di messaggistica istantanea o **Web Conferencing** se l'archiviazione ha esito negativo.
    
6. Fare clic su **Commit**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Configurare la modalità critica tramite Windows PowerShell

È inoltre possibile specificare se le sessioni di comunicazione devono essere consentite in caso di errore che impedirebbe l'archiviazione utilizzando il cmdlet **Set-CsArchivingConfiguration** con il parametro BlockOnArchiveFailure.
  
Ad esempio, il comando seguente disabilita le comunicazioni in caso di errore di archiviazione:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

Il comando successivo abilita le comunicazioni in caso di errore di archiviazione:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsArchivingConfiguration.](/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps)
