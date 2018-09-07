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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Vedere come selezionare le lingue dell'operatore automatico per un numero di Audioconferenza in Skype for Business online.
ms.openlocfilehash: 70313648f04b05e622ddb34e871ff1b303ac02a7
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23864986"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Impostare le lingue dell'operatore automatico per Audioconferenza in Skype for Business online

> [!Note]
> Per informazioni sull'impostazione della lingua dell'operatore automatico in Microsoft Teams, vedere [Impostare le lingue dell'operatore automatico per l'Audioconferenza in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

L'operatore automatico di Audioconferenza per Skype for Business può dare il benvenuto ai partecipanti in diverse lingue quando questi ultimi aderiscono a una riunione.
  
Scegliere una lingua principale e fino a quattro lingue secondarie. La lingua impostata come principale verrà utilizzata per prima e le lingue secondarie verranno utilizzate dall'operatore automatico nell'ordine selezionato. 
  
> [!NOTE]
>  È possibile configurare le lingue solo per i numeri di telefono interni di accesso all'audio.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Impostare le lingue dell'operatore automatico per i servizi di conferenza

È necessario essere un [amministratore globale di Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) o [Skype for Business](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) per eseguire questo passaggio.
    
1. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di navigazione sinistra, vai su **Audioconferenza**, poi fai clic su **Microsoft bridge**.
    
2. Seleziona dall'elenco il numero di telefono di accesso all'audioconferenza, quindi nel riquadro Azioni, fai clic su **Imposta lingue**. 
    
3. Nella pagina **Imposta lingue,** fai clic sull'elenco **Lingua principale** per visualizzare l'elenco completo delle lingue supportate. Se lo desideri, fai clic su ognuno degli elenchi delle **Lingue secondarie** per selezionare una lingua secondaria.
    
    > [!NOTE]
    > Vengono elencate le lingue principali e secondarie supportate. L'ordine in cui vengono selezionate le lingue negli elenchi è l'ordine delle lingue disponibili per i chiamanti. 
  
4. Fai clic su **Salva**.
    
## <a name="want-else-should-i-know"></a>Quali altre informazioni sono necessarie?

- Per visualizzare l'elenco delle lingue supportate per Audioconferenza, consulta [Lingue supportate per Audioconferenza](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Le lingue possono essere impostate per numeri specifici, ma non per i numeri di telefono condivisi.
    
- Per visualizzare un elenco dei paesi/aree geografiche in cui sono disponibili i servizi di Audioconferenza in Office 365 con Microsoft come provider, vedere [Numeri di telefono per Audioconferenza](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Desideri utilizzare Windows PowerShell?

Per automatizzare questo passaggio, puoi utilizzare i cmdlet [Set-CsOnlineDialInConferencingServiceNumber ](https://go.microsoft.com/fwlink/?LinkId=617689) e [Get-CsOnlineDialInConferencingLanguagesSupported ](https://go.microsoft.com/fwlink/?LinkId=617684) .
  
Per maggiori informazioni, consulta [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare ll'audioconferenza in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
