---
title: Modificare i criteri di archiviazione esistenti in Skype for Business Server
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
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Riepilogo: informazioni su come modificare i criteri di archiviazione degli utenti per Skype for Business Server.'
ms.openlocfilehash: 010365b5805517db8f40aa7e3e839fdb15115c06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818988"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>Modificare i criteri di archiviazione esistenti in Skype for Business Server
 
**Riepilogo:** Informazioni su come modificare i criteri di archiviazione degli utenti per Skype for Business Server.
  
Quando si distribuisce Skype for Business Server per la prima volta, si configurano i criteri di archiviazione iniziali che determinano il modo in cui l'archiviazione viene implementata per gli utenti della distribuzione. Questo argomento descrive come gestire e modificare i criteri. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>Modificare i criteri di archiviazione tramite il pannello di controllo

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.
    
4. Nell'elenco dei criteri eseguire una delle operazioni seguenti: 
    
   - Per modificare il criterio per l'intera distribuzione, fare clic su **globale** nell'elenco dei criteri, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
   - Per modificare i criteri per un singolo sito, fare clic sul nome del sito nell'elenco dei criteri, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
   - Per modificare i criteri per un singolo utente o un gruppo di utenti, fare clic sul nome del gruppo di utenti o utenti nell'elenco dei criteri, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
5. Nella pagina **modifica criteri di archiviazione** eseguire le operazioni seguenti:
    
   - Per abilitare o disabilitare l'archiviazione interna per il criterio, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .
    
   - Per abilitare o disabilitare l'archiviazione esterna per il criterio, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .
    
6. Fare clic su **Commit**.
    
    > [!IMPORTANT]
    > Le impostazioni di un criterio utente si applicano solo agli utenti e ai gruppi utente specifici a cui si applicano i criteri. Per informazioni dettagliate, vedere [applicare un criterio di archiviazione agli utenti in Skype for Business Server](apply-a-policy-to-users.md). 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>Modificare i criteri di archiviazione tramite Windows PowerShell

È anche possibile modificare i criteri di archiviazione usando il cmdlet **Set-CsArchivingPolicy** di Windows PowerShell.
  
### <a name="enable-archiving-policies"></a>Abilitare i criteri di archiviazione

Per abilitare l'archiviazione delle sessioni di comunicazione interne, imposta il valore del parametro ArchiveInternal su true ($True): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

Per abilitare l'archiviazione delle sessioni di comunicazione esterne, imposta il valore del parametro ArchiveExternal su true ($True): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

Per abilitare l'archiviazione delle sessioni di comunicazione interne ed esterne, imposta il valore dei parametri ArchiveInternal e ArchiveExternal su true: 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>Disabilitare i criteri di archiviazione

Per disabilitare complessivamente l'archiviazione, imposta il valore dei parametri ArchiveInternal e ArchiveExternal su false ($False): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
