---
title: Creare una configurazione di archiviazione in Skype for Business Server
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
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 'Riepilogo: informazioni su come creare una configurazione di archiviazione per Skype for Business Server.'
ms.openlocfilehash: bc7319f2de8398dd3d9e9a79948d1af6eaeb98bc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818958"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a>Creare una configurazione di archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come creare una configurazione di archiviazione per Skype for Business Server.
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurare le opzioni di archiviazione tramite il pannello di controllo

Per configurare le opzioni di archiviazione per un sito o un pool specifico: 
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.
    
4. Nella pagina **Configurazione archiviazione** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti: 
    
   - Per creare una configurazione di archiviazione del sito, fare clic su **configurazione sito**e quindi selezionare il sito da configurare per l'archiviazione in **selezionare un sito**.
    
   - Per creare una configurazione di archiviazione del pool, fare clic su **Configurazione pool**e quindi in **selezionare un pool**Selezionare il pool da configurare per l'archiviazione.
    
5. In **nuova impostazione archiviazione**, nella casella di riepilogo a discesa **Impostazioni archiviazione** eseguire una delle operazioni seguenti:
    
   - Per abilitare l'archiviazione solo per le sessioni di messaggistica istantanea (IM), fare clic su **Archivia sessioni**istantanee.
    
   - Per abilitare l'archiviazione sia per le sessioni di messaggistica istantanea che per le conferenze Web, fare clic su **Archivia messaggistica istantanea e sessioni di conferenza Web**.
    
   - Per disabilitare l'archiviazione per questa configurazione, fare clic su **Disattiva archiviazione**.
    
6. Anche in **nuove impostazioni di archiviazione**eseguire le operazioni seguenti:
    
   - Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca messaggistica istantanea o servizi di conferenza Web se l'archiviazione non riesce** .
    
   - Per usare Microsoft Exchange Server per archiviare i dati di archiviazione, fare clic sulla casella di controllo **integrazione di Microsoft Exchange** .
    
   - Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita l'eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:
    
     - Per specificare l'eliminazione dopo un determinato numero di giorni, fare clic su **Elimina dati di archiviazione esportati e archivia dati archiviati dopo la durata massima (giorni)** e quindi specificare il numero di giorni.
    
     - Per limitare l'eliminazione all'archiviazione dei dati esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.
    
7. Fare clic su **Commit**.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configurare le opzioni di archiviazione tramite Windows PowerShell

È anche possibile configurare le opzioni di archiviazione per un sito o un pool specifico usando il cmdlet **New-CsArchivingConfiguration** .
  
Il comando seguente crea una nuova raccolta di impostazioni di configurazione dell'archiviazione per il sito Redmond:
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

Poiché non sono stati specificati parametri (ad eccezione del parametro di identità obbligatorio) nel comando precedente, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per tutte le relative proprietà. 
  
Per creare impostazioni che usano valori di proprietà diversi, includere semplicemente il parametro e il valore del parametro appropriati. L'esempio seguente crea una raccolta di impostazioni di configurazione dell'archiviazione che, per impostazione predefinita, consentono l'archiviazione solo delle sessioni di messaggistica istantanea:
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

Più valori di proprietà possono essere modificati includendo più parametri. Ad esempio, questo comando Configura le nuove impostazioni per l'archiviazione delle sessioni di messaggistica istantanea e per bloccare la messaggistica istantanea del servizio archiviazione non disponibile:
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) .
