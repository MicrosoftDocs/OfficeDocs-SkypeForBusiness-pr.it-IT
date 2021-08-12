---
title: Impostare le lingue dell'operatore automatico per Audioconferenza in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Vedere come selezionare le lingue dell'operatore automatico per un numero di Audioconferenza in Skype for Business online.
ms.openlocfilehash: 044d05ec8b67f1e7732140a90c47b0666568fafe241fe3a45f2d02c46824e903
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326992"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Impostare le lingue dell'operatore automatico per Audioconferenza in Skype for Business online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Per informazioni sull'impostazione della lingua dell'operatore automatico in Microsoft Teams, vedere [Impostare le lingue dell'operatore automatico per l'Audioconferenza in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

L'operatore automatico di Audioconferenza per Skype for Business può dare il benvenuto ai partecipanti in diverse lingue quando questi ultimi aderiscono a una riunione.
  
Scegliere una lingua principale e fino a quattro lingue secondarie. La lingua impostata come principale verrà utilizzata per prima e le lingue secondarie verranno utilizzate dall'operatore automatico nell'ordine selezionato. 
  
> [!NOTE]
>  È possibile modificare solo le lingue dei numeri di audioconferenza della categoria Dedicata. Non è possibile modificare le lingue del numero di audioconferenza condiviso.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Impostare le lingue dell'operatore automatico per i servizi di conferenza

Per eseguire questo [passaggio,](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) è necessario essere un amministratore globale [o Skype for Business](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) amministratore globale.
    
1. **Nell'Skype for Business di amministrazione,** nel riquadro di spostamento sinistro, passare a **Portale legacy.** Una volta nel portale legacy, selezionare **Audioconferenza** e quindi fare clic su **Bridge Microsoft.**
    
2. Selezionare il numero di telefono per i servizi di audioconferenza nell'elenco e nel riquadro Azioni fare clic **su Imposta lingue.** È possibile cambiare solo le lingue dei numeri di audioconferenza dedicati.  
    
3. Nella pagina **Imposta lingue,** fai clic sull'elenco **Lingua principale** per visualizzare l'elenco completo delle lingue supportate. Se lo desideri, fai clic su ognuno degli elenchi delle **Lingue secondarie** per selezionare una lingua secondaria.
    
    > [!NOTE]
    > Vengono elencate le lingue principali e secondarie supportate. L'ordine in cui vengono selezionati negli elenchi sarà l'ordine delle lingue presentate ai chiamanti. 
  
4. Fare clic su **Salva**.
    
## <a name="want-else-should-i-know"></a>Se vuoi altro, devo saperlo?

- Per visualizzare l'elenco delle lingue supportate per Audioconferenza, consulta [Lingue supportate per Audioconferenza](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Le lingue possono essere impostate per numeri specifici, ma non per i numeri di telefono condivisi.
    
- Per visualizzare un elenco di paesi/aree geografiche in cui è disponibile l'audioconferenza in Microsoft 365 o Office 365 che usano Microsoft come provider, vedere numeri di Telefono per le [audioconferenze.](phone-numbers-for-audio-conferencing.md)
    
## <a name="want-to-use-windows-powershell"></a>Desideri utilizzare Windows PowerShell?

Per automatizzare questo passaggio, è possibile usare i cmdlet [Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) e [Get-CsOnlineDialInConferencingLanguagesSupported.](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported)
  
Per altre informazioni, vedere [Uso di Windows PowerShell per eseguire attività Skype for Business gestione online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
