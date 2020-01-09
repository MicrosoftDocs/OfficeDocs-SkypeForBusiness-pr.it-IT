---
title: Applicare un criterio di archiviazione agli utenti in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Riepilogo: informazioni su come assegnare un criterio di archiviazione agli utenti in Skype for Business Server.'
ms.openlocfilehash: 5dbd1624813b187e8c0981aa1a84b6096b79e86a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992783"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Applicare un criterio di archiviazione agli utenti in Skype for Business Server

**Riepilogo:** Informazioni su come assegnare un criterio di archiviazione agli utenti in Skype for Business Server.
  
Se sono stati creati uno o più criteri per l'archiviazione per gli utenti ospitati in Skype for Business Server, è possibile implementare il supporto per l'archiviazione per utenti specifici applicando i criteri appropriati a tali utenti o a gruppi di utenti. Ad esempio, se crei un criterio per supportare l'archiviazione delle comunicazioni interne, puoi applicarlo ad almeno un utente o un gruppo di utenti per supportare l'archiviazione delle comunicazioni di Skype for Business Server dell'utente.
  
> [!NOTE]
> Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di blocco sul posto di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e le cassette postali vengono messe sul posto. Per informazioni dettagliate, vedere [pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e [configurare l'integrazione con lo spazio di archiviazione di Exchange per Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Applicare un criterio utente tramite il pannello di controllo

Per applicare un criterio utente tramite il pannello di controllo:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Nella barra di spostamento sinistra fare clic su **utenti**e quindi cercare l'account utente che si vuole configurare. 
    
4. Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.
    
5. In **modifica utenti di Lync Server** in **criteri di archiviazione**Selezionare i criteri utente di archiviazione che si desidera applicare.
    
    > [!NOTE]
    > Le ** \<impostazioni\> automatiche** applicano le impostazioni di installazione del server predefinite. Queste impostazioni vengono applicate automaticamente dal server.
  
6. Fare clic su **Commit**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Applicare un criterio utente tramite Windows PowerShell

Puoi anche applicare un criterio utente usando il cmdlet **Grant-CsArchivingPolicy** di Windows PowerShell.
  
Con il comando seguente viene assegnato il criterio di archiviazione per utente RedmondArchivingPolicy all'utente Ken.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Questo comando assegna il criterio di archiviazione per utente RedmondArchivingPolicy a tutti gli utenti che hanno account assegnati nel pool di registrazione atl-cs-001.contoso.com. Per informazioni dettagliate sul parametro Filter usato in questo comando, vedere la documentazione del cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

Il comando seguente rimuove tutti i criteri di archiviazione per utente assegnati in precedenza a Ken. Dopo che il criterio per utente viene rimosso, Ken è gestito automaticamente tramite il criterio globale oppure, se disponibile, il criterio del sito locale. Un criterio di sito ha la precedenza sui criteri globali.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Per informazioni dettagliate, vedere la documentazione del cmdlet [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .
  

