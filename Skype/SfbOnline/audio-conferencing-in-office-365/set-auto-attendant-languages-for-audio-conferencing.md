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
ms.openlocfilehash: 34ed4ccee5239923f68b089ce14551fe43c32320
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776801"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Impostare le lingue dell'operatore automatico per Audioconferenza in Skype for Business online

> [!Note]
> Per informazioni sull'impostazione della lingua dell'operatore automatico in Microsoft Teams, vedere [Impostare le lingue dell'operatore automatico per l'Audioconferenza in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

L'operatore automatico di Audioconferenza per Skype for Business può dare il benvenuto ai partecipanti in diverse lingue quando questi ultimi aderiscono a una riunione.
  
Choose one primary language and up to four secondary languages. The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select. 
  
> [!NOTE]
>  È possibile modificare solo le lingue dei numeri di servizi di audioconferenza della categoria dedicata. Le lingue del numero di audioconferenza condiviso non possono essere modificate.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Impostare le lingue dell'operatore automatico per i servizi di conferenza

Per eseguire questo passaggio, è necessario essere un amministratore [globale](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) o un [amministratore di Skype for business](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) .
    
1. Nell'interfaccia di **amministrazione di Skype for business**, nella barra di spostamento sinistra, vai a **portale legacy**. Nel portale legacy Selezionare Servizi di **audioconferenza**e quindi fare clic su **Microsoft Bridge**.
    
2. Selezionare il numero di telefono dell'audioconferenza nell'elenco e fare clic su **imposta lingue**nel riquadro azioni. È possibile cambiare solo le lingue dei numeri di servizi di audioconferenza dedicati.  
    
3. Nella pagina **Imposta lingue,** fai clic sull'elenco **Lingua principale** per visualizzare l'elenco completo delle lingue supportate. Se lo desideri, fai clic su ognuno degli elenchi delle **Lingue secondarie** per selezionare una lingua secondaria.
    
    > [!NOTE]
    > Vengono elencate le lingue principali e secondarie supportate. L'ordine in cui vengono selezionati gli elenchi sarà l'ordine delle lingue presentate ai chiamanti. 
  
4. Fare clic su **Salva**.
    
## <a name="want-else-should-i-know"></a>Altre informazioni utili

- Per visualizzare l'elenco delle lingue supportate per Audioconferenza, consulta [Lingue supportate per Audioconferenza](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Le lingue possono essere impostate per numeri specifici, ma non per i numeri di telefono condivisi.
    
- Per visualizzare un elenco dei paesi/aree geografiche in cui sono disponibili i servizi di Audioconferenza in Office 365 con Microsoft come provider, vedere [Numeri di telefono per Audioconferenza](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Desideri utilizzare Windows PowerShell?

Per automatizzare questo passaggio, è possibile usare i cmdlet [set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) e [Get-renderle](https://go.microsoft.com/fwlink/?LinkId=617684) .
  
Per altre informazioni, vedere [uso di Windows PowerShell per eseguire comuni attività di gestione di Skype for business online](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
