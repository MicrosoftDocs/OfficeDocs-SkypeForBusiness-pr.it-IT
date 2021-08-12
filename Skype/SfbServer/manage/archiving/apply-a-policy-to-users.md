---
title: Applicare un criterio di archiviazione agli utenti in Skype for Business Server
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
ms.openlocfilehash: b7dbd8a4222065c2bc53029b75672d6905dcd73b3a79e0d35ebfc6ce980f9865
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54311094"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Applicare un criterio di archiviazione agli utenti in Skype for Business Server

**Riepilogo:** Informazioni su come assegnare un criterio di archiviazione agli utenti in Skype for Business Server.
  
Se sono stati creati uno o più criteri utente per l'archiviazione per gli utenti ospitati in Skype for Business Server, è possibile implementare il supporto di archiviazione per utenti specifici applicando i criteri appropriati a tali utenti o gruppi di utenti. Ad esempio, se si crea un criterio per supportare l'archiviazione delle comunicazioni interne, è possibile applicarlo ad almeno un utente o a un gruppo di utenti per supportare l'archiviazione delle comunicazioni Skype for Business Server'utente.
  
> [!NOTE]
> Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di blocco del Exchange In-Place controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e che le cassette postali vengono In-Place conservazione. Per informazioni dettagliate, vedere [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for [Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Applicare criteri utente tramite il Pannello di controllo

Per applicare un criterio utente tramite il Pannello di controllo:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna. 
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 
    
3. Sulla barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente che si desidera configurare. 
    
4. Nella tabella dei risultati di ricerca fare clic sull'account utente, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.
    
5. In **Modifica utente Lync Server** in Criteri di **archiviazione** selezionare il criterio utente di archiviazione che si desidera applicare.
    
    > [!NOTE]
    > Le **\<Automatic\>** impostazioni applicano le impostazioni di installazione predefinite del server. Queste impostazioni vengono applicate automaticamente dal server.
  
6. Fare clic su **Commit**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Applicare criteri utente tramite Windows PowerShell

È inoltre possibile applicare un criterio utente utilizzando il cmdlet **Windows PowerShell Grant-CsArchivingPolicy.**
  
Il comando seguente assegna il criterio di archiviazione per utente RedmondArchivingPolicy all'utente Ken Myer:
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Questo comando assegna il criterio di archiviazione per utente RedmondArchivingPolicy a tutti gli utenti che dispongono di account ospitati nel pool di registrazione atl-cs-001.contoso.com. Per informazioni dettagliate sul parametro Filter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser.](/powershell/module/skype/get-csuser?view=skype-ps)
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

Il comando seguente consente di rimuovere tutti i criteri di archiviazione per utente precedentemente assegnati a Ken Myer. Dopo la rimozione dei criteri per utente, Ken Myer verrà gestito automaticamente utilizzando il criterio globale o, se esistente, il criterio del sito locale. I criteri del sito hanno la precedenza sui criteri globali.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Per informazioni dettagliate, vedere la documentazione relativa al cmdlet [Grant-CsArchivingPolicy.](/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps)
