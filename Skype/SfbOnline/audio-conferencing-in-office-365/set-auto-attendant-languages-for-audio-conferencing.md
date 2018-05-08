---
title: Set di lingue con operatore automatico per le conferenze Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Vedere come selezionare le lingue di operatore automatico conferenza per un numero di conferenze audio.
ms.openlocfilehash: c4461f61ce05afedc2663a3e5b61d37370394cd4
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="set-auto-attendant-languages-for-audio-conferencing"></a>Set di lingue con operatore automatico per le conferenze Audio

L'operatore automatico di audioconferenza per Skype per le aziende e Teams Microsoft può greet i chiamanti audio in numerose lingue diverse quando partecipano a una riunione.
  
Scegliere una lingua principale e fino a quattro lingue secondarie. Verrà utilizzata la lingua principale impostata prima e lingue secondarie da utilizzare per l'operatore automatico in modo che si seleziona. 
  
> [!NOTE]
>  È possibile configurare le lingue su solo i numeri di telefono interno accesso audio.
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Impostare i servizi di conferenza lingue operatore automatico

![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**

1. Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**.

2. Selezionare il numero di telefono di accesso esterno alle audioconferenze dall'elenco nella parte superiore della pagina, quindi fare clic su **Modifica**.

3. Nel riquadro a destra, scegliere la lingua predefinita desiderata e le lingue alternative. 
 
    > [!NOTE]
    > L'impostazione predefinita e le relative lingue alternative supportati sono elencate. L'ordine in cui vengono selezionati negli elenchi è l'ordine delle lingue disponibili per i chiamanti. 

4. Fare clic su **Applica**.

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **Utilizzando Skype for Business in linea**

È necessario essere un [amministratore globale di Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) o [Skype per Business admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) per eseguire questo passaggio.
    
1. Nel **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**e quindi **bridge di Microsoft**.
    
2. Selezionare il numero di telefono di accesso esterno alle audioconferenze dall'elenco, quindi nel riquadro azioni, fare clic su **Imposta lingue**. 
    
3. Nella pagina **gruppo** di lingue, fare clic sull'elenco **lingua principale** per visualizzare l'elenco completo delle lingue disponibili. Se si desidera, fare clic su ognuno degli elenchi di **lingue secondarie** per selezionare una lingua secondaria.
    
    > [!NOTE]
    > Vengono elencate le lingue principale e secondarie supportati. L'ordine in cui vengono selezionati negli elenchi è l'ordine delle lingue disponibili per i chiamanti. 
  
4. Fai clic su **Salva**.
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-else-should-i-know"></a>Desidera, in caso contrario, è necessario conoscere?

- Per visualizzare l'elenco delle lingue supportate per le conferenze Audio, vedere [servizi di conferenza Audio lingue supportate](audio-conferencing-supported-languages.md).
    
- Lingue possono essere impostate per dedicato, ma non per i numeri di telefono condivisa.
    
- Per visualizzare un elenco dei paesi in cui è disponibile per conferenze Audio in Office 365 con Microsoft come provider, vedere [i numeri di telefono per le audioconferenze](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Se si desidera utilizzare Windows PowerShell?

Per automatizzare questo passaggio, è possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) e [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) .
  
Per ulteriori informazioni, vedere [Using Windows PowerShell per eseguire Skype comuni per le attività di gestione in linea aziendale](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>See also

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
