---
title: "Impostazione delle lingue dell'operatore automatico per le conferenze Audio"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
description: "See how to select the auto-attendant lanugages for a dial-in conferencing number."
---

# Impostazione delle lingue dell'operatore automatico per le conferenze Audio

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](26d73dda-ab26-4af4-8aec-d17f3479ae50.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/26d73dda-ab26-4af4-8aec-d17f3479ae50). 
  
L'operatore automatico di conferenze Audio per Skype for Business e Teams Microsoft è possibile accogliere i chiamanti audio a un numero di lingue diverse, quando accedono a una riunione.
  
Scegliere una lingua principale e fino a quattro lingue secondarie. La lingua primaria verrà usata per prima e le lingue secondarie verranno usate dall'operatore automatico nell'ordine selezionato. 
  
> [!NOTE]
> È possibile configurare le lingue nel solo numeri di telefono di accesso audio nazionali. 
  
## Configurare i servizi di conferenza lingue dell'operatore automatico

Per eseguire questo passaggio, è necessario essere un [Informazioni sui ruoli di amministratore di Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) o un[Informazioni sui ruoli di amministratore di Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d). 
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. In **Skype for Business admin center**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** e quindi fare clic su **bridge Microsoft**.
    
4. Selezionare il numero di telefono audioconferenza dall'elenco nel riquadro azioni, quindi fare clic su **Imposta lingue**.
    
5. Nella pagina **Imposta lingue**, fare clic sull'elenco **lingua principale** per visualizzare l'elenco completo delle lingue disponibili. Se necessario, fare clic su ognuno degli elenchi di **lingue secondarie** per selezionare la lingua secondaria.
    
    > [!NOTE]
    > Sono elencate le lingue primarie e secondarie che sono supportate. L'ordine in cui si selezionarli negli elenchi di sarà l'ordine delle lingue presentate per i chiamanti. 
  
6. Fai clic su **Salva**.
    
## Per saperne di più

- Per visualizzare l'elenco delle lingue supportate per conferenze Audio, consulta [Lingue supportate da audioconferenza](audio-conferencing-supported-languages.md).
    
- È possibile impostare lingue per dedicato ma non per i numeri di telefono condiviso.
    
- Per visualizzare un elenco di paesi/aree geografiche in cui è disponibile conferenze Audio in Office 365 usando Microsoft come provider, vedere [Numeri di telefono per i servizi di audioconferenza](phone-numbers-for-audio-conferencing.md).
    
## Vuoi usare Windows PowerShell?

Per automatizzare questa operazione, è possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingServiceNumber ](https://go.microsoft.com/fwlink/?LinkId=617689) e[Get-CsOnlineDialInConferencingLanguagesSupported ](https://go.microsoft.com/fwlink/?LinkId=617684) .
  
Per ulteriori informazioni, vedere Uso di Windows PowerShell per eseguire comuni Skype per Business Online attività di gestione[](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  
## Vedere anche
<a name="MT_Footer"> </a>

#### 

[Configurare le audioconferenze per Skype for Business e Microsoft Teams](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)

