---
title: Set di lingue con operatore automatico per le conferenze Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Vedere come selezionare le lingue di operatore automatico conferenza per un numero di conferenze audio.
ms.openlocfilehash: c352609926a7bc6bf7f72015447ba9f7ae115487
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2018
---
# <a name="set-auto-attendant-languages-for-audio-conferencing"></a>Set di lingue con operatore automatico per le conferenze Audio

L'operatore automatico di audioconferenza per Skype per le aziende e Teams Microsoft può greet i chiamanti audio in numerose lingue diverse quando partecipano a una riunione.
  
Scegliere una lingua principale e fino a quattro lingue secondarie. Verrà utilizzata la lingua principale impostata prima e lingue secondarie da utilizzare per l'operatore automatico in modo che si seleziona. 
  
> [!NOTE]
>  È possibile configurare le lingue su solo i numeri di telefono interno accesso audio.
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Impostare i servizi di conferenza lingue operatore automatico

È necessario essere un [amministratore globale di Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) o [Skype per Business admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) per eseguire questo passaggio.
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nel **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**e quindi **bridge di Microsoft**.
    
4. Selezionare il numero di telefono di accesso esterno alle audioconferenze dall'elenco, quindi nel riquadro azioni, fare clic su **Imposta lingue**. 
    
5. Nella pagina **gruppo** di lingue, fare clic sull'elenco **lingua principale** per visualizzare l'elenco completo delle lingue disponibili. Se si desidera, fare clic su ognuno degli elenchi di **lingue secondarie** per selezionare una lingua secondaria.
    
    > [!NOTE]
    > Vengono elencate le lingue principale e secondarie supportati. L'ordine in cui vengono selezionati negli elenchi è l'ordine delle lingue disponibili per i chiamanti. 
  
6. Fai clic su **Salva**.
    
## <a name="want-else-should-i-know"></a>Desidera, in caso contrario, è necessario conoscere?

- Per visualizzare l'elenco delle lingue supportate per le conferenze Audio, vedere [servizi di conferenza Audio lingue supportate](audio-conferencing-supported-languages.md).
    
- Lingue possono essere impostate per dedicato, ma non per i numeri di telefono condivisa.
    
- Per visualizzare un elenco dei paesi in cui è disponibile per conferenze Audio in Office 365 con Microsoft come provider, vedere [i numeri di telefono per le audioconferenze](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Se si desidera utilizzare Windows PowerShell?

Per automatizzare questo passaggio, è possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) e [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) .
  
Per ulteriori informazioni, vedere [Using Windows PowerShell per eseguire Skype comuni per le attività di gestione in linea aziendale](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>See also

[Servizi di conferenza telefonica con accesso esterno in Office 365](set-up-audio-conferencing.md)
