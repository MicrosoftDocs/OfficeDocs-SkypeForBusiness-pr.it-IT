---
title: Applicazione di un criterio di archiviazione agli utenti in Skype for Business Server
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
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Riepilogo: informazioni su come assegnare un criterio di archiviazione agli utenti in Skype for Business Server.'
ms.openlocfilehash: 8dc74fcc8befe39b424b89c77aebca683fe17586
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817766"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Applicazione di un criterio di archiviazione agli utenti in Skype for Business Server

**Riepilogo:** Informazioni su come assegnare un criterio di archiviazione agli utenti in Skype for Business Server.
  
Se sono stati creati uno o più criteri utente per l'archiviazione per gli utenti ospitati in Skype for Business Server, è possibile implementare il supporto di archiviazione per utenti specifici applicando i criteri corretti a tali utenti o gruppi di utenti. Ad esempio, se si crea un criterio per il supporto dell'archiviazione delle comunicazioni interne, è possibile applicarlo ad almeno un utente o un gruppo di utenti per supportare l'archiviazione delle comunicazioni di Skype for Business Server dell'utente.
  
> [!NOTE]
> Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange In-Place conservazione determinano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e le cassette postali vengono inserite In-Place blocco. Per ulteriori informazioni, vedere [pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e [configurare l'integrazione con l'archivio di Exchange per Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Applicazione di un criterio utente tramite il pannello di controllo

Per applicare un criterio utente utilizzando il pannello di controllo:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente che si desidera configurare. 
    
4. Nella tabella dei risultati di ricerca fare clic sull'account utente, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.
    
5. In **modifica utente di Lync Server** in **criteri di archiviazione** Selezionare i criteri utente di archiviazione che si desidera applicare.
    
    > [!NOTE]
    > Le **\<Automatic\>** impostazioni applicano le impostazioni di installazione predefinite del server. Queste impostazioni vengono applicate automaticamente dal server.
  
6. Fare clic su **Commit**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Applicazione di un criterio utente tramite Windows PowerShell

È anche possibile applicare un criterio utente utilizzando il cmdlet **Grant-CsArchivingPolicy** di Windows PowerShell.
  
Il comando seguente assegna il criterio di archiviazione per utente RedmondArchivingPolicy all'utente Ken Myer:
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Questo comando consente di assegnare il criterio di archiviazione per utente RedmondArchivingPolicy a tutti gli utenti che dispongono di account ospitati nel pool di registrazione atl-cs-001.contoso.com. Per informazioni dettagliate sul parametro Filter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

Il seguente comando consente di rimuovere tutti i criteri di archiviazione per utente precedentemente assegnati a Ken. Dopo che il criterio per utente è stato rimosso, Ken è gestito automaticamente tramite il criterio globale o, se esiste, il criterio del sito locale. I criteri del sito hanno la precedenza sui criteri globali.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Per informazioni dettagliate, vedere la documentazione relativa al cmdlet [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .
  

