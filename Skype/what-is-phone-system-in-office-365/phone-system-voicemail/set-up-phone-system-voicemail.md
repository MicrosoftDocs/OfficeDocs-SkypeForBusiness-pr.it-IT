---
title: "Impostare la segreteria telefonica del Sistema telefonico - Guida per gli amministratori"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/15/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
description: "Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. "
---

# Impostare la segreteria telefonica del Sistema telefonico - Guida per gli amministratori

Questo articolo è rivolto agli [Informazioni sui ruoli di amministratore di Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) che vogliono configurare la segreteria telefonica del Sistema telefonico per tutti i dipendenti dell'azienda.
  
> [!NOTE]
> La segreteria telefonica del Sistema telefonico supporta la registrazione di messaggi vocali solo in una casella Exchange e non supporta i sistemi e-mail di terze parti. Come meccanismo di fallback, la segreteria telefonica del Sistema telefonico può reinviare messaggi tramite SMTP, quindi gli utenti con una casella di posta su un sistema e-mail di terze parti riceveranno i messaggi vocali senza tempo di attività del servizio garantito o altre funzionalità della segreteria telefonica come la modifica del messaggio di saluto e altre impostazioni. 
  
## Ambienti solo su cloud: Impostare la segreteria telefonica del Sistema telefonico

Per gli utenti Skype for Business online e Piani per chiamate, la segreteria telefonica del Sistema telefonico viene configurata e messa in servizio automaticamente per gli utenti una volta assegnata una licenza **Sistema telefonico** e un numero di telefono.
  
1. Se la funzione Sistema telefonico non è inclusa nel tuo piano, può essere necessario acquistare licenze per il componente aggiuntivo **Sistema telefonico**. Inoltre è necessario acquistare una licenza Exchange Online. Consulta l'articolo [Skype for Business e Teams Microsoft componente aggiuntivo per le licenze](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) e le[Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) e le licenze Exchange Online ai dipendenti dell'azienda. Terminate queste operazioni, potranno ricevere i messaggi vocali.
    
3. Il supporto per la trascrizione segreteria telefonica è stato aggiunto a partire da marzo 2017 ed è attivato per impostazione predefinita per tutte le organizzazioni e gli utenti. Puoi disattivare la trascrizione per la tua organizzazione usando Windows PowerShell e attenendoti alle seguenti istruzioni.
    
## Sistema telefonico con ambienti locali

Le seguenti informazioni indicano come configurare la segreteria telefonica del Sistema telefonico con ambienti con Piano per chiamate locale.
  
1. Se la funzione Sistema telefonico non è inclusa nel tuo piano, può essere necessario acquistare licenze per il componente aggiuntivo **Sistema telefonico**. Inoltre è necessario acquistare una licenza Exchange Online. Consulta l'articolo [Skype for Business e Teams Microsoft componente aggiuntivo per le licenze](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) e le[Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) e le licenze Exchange Online ai dipendenti dell'azienda.
    
3. Segui le istruzioni illustrate nella sezione **Abilitare gli utenti per i servizi vocali Sistema telefonico e segreteria telefonica** della guida[Configurare Skype for Business Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605228.aspx).
    
4. Il supporto per la trascrizione segreteria telefonica è stato aggiunto a partire da marzo 2017 ed è attivato per impostazione predefinita per tutte le organizzazioni e gli utenti. Puoi disattivare la trascrizione per la tua organizzazione usando Windows PowerShell e attenendoti alle seguenti istruzioni. 
    
5. Puoi anche consultare l'[Assistenza per segreteria telefonica Azure PBX per Exchange Server](https://support.microsoft.com/en-us/kb/3195158) per sapere come configurare la consegna dei messaggi vocali Azure per gli utenti di Sistema telefonico con una cassetta postale locale.
    
## Impostazione dei criteri di segreteria telefonica dell'organizzazione

La trascrizione segreteria telefonica è attivata per impostazione predefinita per tutte le organizzazioni e gli utenti; tuttavia, è possibile controllarla utilizzando i cmdlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) e[Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx).
  
> [!IMPORTANT]
> Non è possibile creare una nuova istanza di criteri trascrizione utilizzando il cmdlet **New-CsOnlineVoiceMailPolicy** e non è possibile rimuovere un'istanza di criteri esistente utilizzando il cmdlet **Remove-CsOnlineVoiceMailPolicy**.
  
È possibile gestire le impostazioni di trascrizione per gli utenti che utilizzano i criteri segreteria telefonica. Per visualizzare tutte le istanze di criteri segreteria telefonica disponibili, è possibile utilizzare il cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/en-us/library/mt798311.aspx)[]().
  
 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### Disattivare la trascrizione per la propria organizzazione

Dato che l'impostazione predefinita per la trascrizione è attiva per la propria organizzazione, si consiglia di disabilitarla utilizzando il cmdlet [set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Per farlo, eseguire quanto segue:
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### Disattivare la trascrizione per un utente

I criteri utente vengono valutati prima delle impostazioni predefinite dell'organizzazione. Ad esempio, se la trascrizione segreteria telefonica è abilitata per tutti gli utenti è possibile assegnare un criterio per disabilitare la trascrizione per un utente specifico utilizzando il cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx).
  
Per disabilitare la trascrizione per un singolo utente, eseguire:
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Il servizio di segreteria telefonica in Office 365 memorizza in cache i criteri di segreteria telefonica e aggiorna la cache ogni 4 ore. Perciò le modifiche apportate ai criteri possono impiegare fino a 4 ore per essere applicate. 
  
## Aiutare gli utenti a imparare le funzioni della segreteria telefonica Skype for Business

Abbiamo informazioni e articoli di formazione per aiutare gli utenti a usare con successo la segreteria telefonica Skype for Business. Questi sono gli articoli che gli utenti vorranno consultare: 
  
- [Controllare le opzioni e la segreteria telefonica di Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Questo articolo illustra come ascoltare i messaggi vocali in Skype for Business e ascoltare i messaggi vocali a velocità diverse.
    
- [Formazione per Skype for Business 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## Argomenti correlati

[Configurare Skype for Business online](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Ecco cosa viene visualizzato con sistema telefonico in Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system-in-office-365.md)
  

