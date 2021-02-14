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
ms.openlocfilehash: 93b6ea917c7f79747273366893efc47a22b89bb2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163902"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Impostare le lingue dell'operatore automatico per Audioconferenza in Skype for Business online

> [!Note]
> Per informazioni sull'impostazione della lingua dell'operatore automatico in Microsoft Teams, vedere [Impostare le lingue dell'operatore automatico per l'Audioconferenza in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

L'operatore automatico di Audioconferenza per Skype for Business può dare il benvenuto ai partecipanti in diverse lingue quando questi ultimi aderiscono a una riunione.
  
Choose one primary language and up to four secondary languages. The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select. 
  
> [!NOTE]
>  Puoi cambiare solo le lingue dei numeri di audioconferenza che sono della categoria Dedicata. Non è possibile modificare le lingue del numero di audioconferenza condiviso.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Impostare le lingue dell'operatore automatico per i servizi di conferenza

Per eseguire questo passaggio [devi essere un amministratore globale](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) o un amministratore Skype for [Business.](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)
    
1. **Nell'interfaccia di amministrazione di Skype for Business,** nella barra di spostamento sinistra, passa a Portale **legacy.** Nel portale legacy seleziona **Audioconferenza** e quindi fai clic su **Microsoft bridge.**
    
2. Seleziona il numero di telefono per i servizi di audioconferenza dall'elenco e, nel riquadro Azioni, fai clic **su Imposta lingue.** È possibile cambiare solo le lingue dei numeri di audioconferenza dedicati.  
    
3. Nella pagina **Imposta lingue,** fai clic sull'elenco **Lingua principale** per visualizzare l'elenco completo delle lingue supportate. Se lo desideri, fai clic su ognuno degli elenchi delle **Lingue secondarie** per selezionare una lingua secondaria.
    
    > [!NOTE]
    > Vengono elencate le lingue principali e secondarie supportate. L'ordine in cui le si seleziona nell'elenco sarà l'ordine delle lingue presentate ai chiamanti. 
  
4. Fare clic su **Salva**.
    
## <a name="want-else-should-i-know"></a>Altre informazioni da conoscere

- Per visualizzare l'elenco delle lingue supportate per Audioconferenza, consulta [Lingue supportate per Audioconferenza](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Le lingue possono essere impostate per numeri specifici, ma non per i numeri di telefono condivisi.
    
- Per visualizzare un elenco dei paesi e delle aree geografiche in cui sono disponibili i servizi di audioconferenza in Microsoft 365 o Office 365 che utilizzano Microsoft come provider, consulta Numeri di telefono per i servizi [di audioconferenza.](phone-numbers-for-audio-conferencing.md)
    
## <a name="want-to-use-windows-powershell"></a>Desideri utilizzare Windows PowerShell?

Per automatizzare questo passaggio, puoi utilizzare i cmdlet [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) e [Get-CsOnlineDialInConferencingLanguagesSupported.](https://go.microsoft.com/fwlink/?LinkId=617684)
  
Per ulteriori informazioni, consulta Uso Windows PowerShell [eseguire le più comuni attività di](https://go.microsoft.com/fwlink/?LinkId=525038) gestione di Skype for Business Online
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
