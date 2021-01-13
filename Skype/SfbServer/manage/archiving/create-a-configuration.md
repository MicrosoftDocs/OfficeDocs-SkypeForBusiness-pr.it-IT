---
title: Creare una configurazione di archiviazione in Skype for Business Server
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
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 'Riepilogo: informazioni su come creare una configurazione di archiviazione per Skype for Business Server.'
ms.openlocfilehash: c5c8dde9a12d0599d962d8c7bcf402796022af7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817656"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a>Creare una configurazione di archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come creare una configurazione di archiviazione per Skype for Business Server.
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurare le opzioni di archiviazione utilizzando il pannello di controllo

Per configurare le opzioni di archiviazione per un sito o un pool specifico: 
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.
    
4. Nella pagina **Configurazione archiviazione** fare clic su **Nuovo** e quindi eseguire una delle operazioni seguenti: 
    
   - Per creare una configurazione di archiviazione del sito, fare clic su **configurazione sito** e quindi in **Seleziona un sito** Selezionare il sito da configurare per l'archiviazione.
    
   - Per creare una configurazione di archiviazione del pool, fare clic su **Configurazione pool** e quindi selezionare il pool da configurare per l'archiviazione in **Seleziona pool**.
    
5. Nell'elenco a discesa **Impostazione di archiviazione** in **Nuova impostazione di archiviazione** eseguire una delle operazioni seguenti:
    
   - Per abilitare l'archiviazione solo per le sessioni di messaggistica istantanea, fare clic su **Archivia sessioni di messaggistica istantanea**.
    
   - Per abilitare l'archiviazione per le sessioni di messaggistica istantanea e le conferenze Web, fare clic su **Archivia sessioni di messaggistica istantanea e Web Conferencing**.
    
   - Per disabilitare l'archiviazione per questa configurazione, fare clic su **Disattiva archiviazione**.
    
6. Sempre in **Nuova impostazione di archiviazione** eseguire le operazioni seguenti:
    
   - Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca sessioni di messaggistica istantanea o Web Conferencing se l'archiviazione non riesce**.
    
   - Per utilizzare Microsoft Exchange Server per archiviare i dati di archiviazione, fare clic sulla casella di controllo **integrazione di Microsoft Exchange** .
    
   - Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:
    
     - Per specificare l'eliminazione dopo un numero specifico di giorni, fare clic su **Elimina dati di archiviazione esportati e archiviati dopo durata massima (giorni)** e quindi specificare il numero di giorni.
    
     - Per limitare l'eliminazione ai dati di archiviazione esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.
    
7. Fare clic su **Commit**.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configurare le opzioni di archiviazione tramite Windows PowerShell

È inoltre possibile configurare le opzioni di archiviazione per un sito o un pool specifico utilizzando il cmdlet **New-CsArchivingConfiguration** .
  
Con il comando seguente viene creata una nuova raccolta di impostazioni di configurazione di archiviazione per il sito Redmond:
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

Poiché nel comando precedente non sono stati specificati parametri, eccetto il parametro obbligatorio Identity, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per le relative proprietà. 
  
Per creare impostazioni basate su valori di proprietà diversi, è sufficiente includere il parametro appropriato e il valore corrispondente. Nell'esempio seguente viene creata una raccolta di impostazioni di configurazione dell'archiviazione che, per impostazione predefinita, consentono l'archiviazione solo delle sessioni di messaggistica istantanea:
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

È possibile modificare più valori di proprietà includendo più parametri. Con il comando seguente ad esempio vengono configurate nuove impostazioni per archiviare le sessioni di messaggistica istantanea e per bloccare la messaggistica istantanea del servizio di archiviazione, se non disponibile:
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) .
