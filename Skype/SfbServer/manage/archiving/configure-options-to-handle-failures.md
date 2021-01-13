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
description: "Riepilogo: informazioni su come bloccare le sessioni di messaggistica istantanea e di conferenza nel caso di un errore di Skype for Business Server che impediva l'archiviazione."
ms.openlocfilehash: 9a39c5f54fbdd4a738f4e67e7f70ff199a204672
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817676"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Configurare le opzioni di archiviazione per gestire gli errori in Skype for Business Server

**Riepilogo:** Informazioni su come bloccare le sessioni di messaggistica istantanea e di conferenza nel caso di un errore di Skype for Business Server che impediva l'archiviazione.
  
Se l'archiviazione è un requisito per la propria organizzazione, è possibile bloccare le sessioni di messaggistica istantanea e di conferenza nel caso di un errore di Skype for Business Server che impediva l'archiviazione. A volte viene chiamata modalità critica. Ad esempio, se si verifica un problema con un servizio di archiviazione, la messaggistica istantanea verrebbe bloccata per gli utenti le cui comunicazioni sono abilitate per l'archiviazione. Sia la funzionalità di messaggistica immediata che il servizio di conferenza vengono ripristinati automaticamente subito dopo la correzione degli errori. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Configurazione della modalità critica tramite il pannello di controllo

Per specificare se le sessioni di comunicazione devono essere consentite in caso di errori che impediscono l'archiviazione:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.
    
4. Fare clic sul nome della configurazione globale, del sito o del pool appropriata nell'elenco delle configurazioni di archiviazione, fare clic su **modifica** e quindi su **Mostra dettagli**.
    
5. Per impostare la modalità di funzionamento dell'archiviazione quando si verifica un errore, selezionare o deselezionare la casella di controllo **blocca sessioni di messaggistica istantanea o Web Conferencing se l'archiviazione non riesce** .
    
6. Fare clic su **Commit**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Configurare la modalità critica tramite Windows PowerShell

È inoltre possibile specificare se le sessioni di comunicazione devono essere consentite in caso di errori che impediscono l'archiviazione utilizzando il cmdlet **Set-CsArchivingConfiguration** con il parametro BlockOnArchiveFailure.
  
Ad esempio, il comando seguente disattiva le comunicazioni nel caso di un errore di archiviazione:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

Il comando seguente consente di abilitare le comunicazioni nel caso di un errore di archiviazione:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) .
  

