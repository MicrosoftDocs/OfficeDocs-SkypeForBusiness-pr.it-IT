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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Vedere come selezionare le lingue dell'operatore automatico per un numero di Audioconferenza in Skype for Business online.
ms.openlocfilehash: 393ba3433ba7241ca5c992114de02191b7fb1044
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229215"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Impostare le lingue dell'operatore automatico per Audioconferenza in Skype for Business online

> [!Note]
> Per informazioni sull'impostazione della lingua dell'operatore automatico in Microsoft Teams, vedere [Impostare le lingue dell'operatore automatico per l'Audioconferenza in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

L'operatore automatico di Audioconferenza per Skype for Business può dare il benvenuto ai partecipanti in diverse lingue quando questi ultimi aderiscono a una riunione.
  
Choose one primary language and up to four secondary languages. The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select. 
  
> [!NOTE]
>  È possibile modificare solo le lingue di numeri di accesso esterno alle audioconferenze della categoria dedicata. Le lingue del numero di conferenze audio condivisi non possono essere modificate.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Impostare le lingue dell'operatore automatico per i servizi di conferenza

È necessario essere un [amministratore globale di Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) o [Skype for Business](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) per eseguire questo passaggio.
    
1. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro sinistro passare al **portale Legacy**. Una volta nel portale legacy, selezionare **conferenze Audio**e quindi fare clic su **Microsoft bridge**.
    
2. Selezionare il numero di telefono di accesso esterno alle audioconferenze dall'elenco, quindi nel riquadro azioni, fare clic su **Imposta lingue**. È possibile solo modificare la lingua dei numeri di audioconferenza dedicato.  
    
3. Nella pagina **Imposta lingue,** fai clic sull'elenco **Lingua principale** per visualizzare l'elenco completo delle lingue supportate. Se lo desideri, fai clic su ognuno degli elenchi delle **Lingue secondarie** per selezionare una lingua secondaria.
    
    > [!NOTE]
    > Vengono elencate le lingue principali e secondarie supportate. L'ordine in cui vengono selezionati negli elenchi è l'ordine delle lingue disponibili per i chiamanti. 
  
4. Fai clic su **Salva**.
    
## <a name="want-else-should-i-know"></a>Desidera, in caso contrario, è necessario conoscere?

- Per visualizzare l'elenco delle lingue supportate per Audioconferenza, consulta [Lingue supportate per Audioconferenza](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Le lingue possono essere impostate per numeri specifici, ma non per i numeri di telefono condivisi.
    
- Per visualizzare un elenco dei paesi/aree geografiche in cui sono disponibili i servizi di Audioconferenza in Office 365 con Microsoft come provider, vedere [Numeri di telefono per Audioconferenza](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Desideri utilizzare Windows PowerShell?

Per automatizzare questo passaggio, è possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) e [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) .
  
Per ulteriori informazioni, vedere [Using Windows PowerShell per eseguire Skype comuni per le attività di gestione in linea aziendale](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
