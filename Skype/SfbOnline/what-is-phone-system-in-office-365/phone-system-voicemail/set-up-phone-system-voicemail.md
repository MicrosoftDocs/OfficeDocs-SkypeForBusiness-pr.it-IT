---
title: Impostare segreteria telefonica del Sistema telefonico
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
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
- Phone System
description: 'Impara come impostare la segreteria telefonica (Cloud PBX) per gli utenti di Skype for Business. '
ms.openlocfilehash: d311c6d0c0f6965d81f557c2080a9bb331de557b
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252890"
---
# <a name="set-up-phone-system-voicemail"></a>Impostare segreteria telefonica del Sistema telefonico

Questo articolo è rivolto agli [amministratori di Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) che vogliono configurare la segreteria telefonica del Sistema telefonico per tutti i dipendenti dell'azienda.

> [!NOTE]
> La segreteria telefonica del Sistema telefonico supporta la registrazione di messaggi vocali solo in una casella Exchange e non supporta i sistemi e-mail di terze parti. Come meccanismo di fallback, la segreteria telefonica del Sistema telefonico può reinviare messaggi tramite SMTP, quindi gli utenti con una casella di posta su un sistema e-mail di terze parti riceveranno i messaggi vocali senza tempo di attività del servizio garantito o altre funzionalità della segreteria telefonica come la modifica del messaggio di saluto e altre impostazioni.

## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a>Ambienti solo su cloud: Impostare la segreteria telefonica del Sistema telefonico

Per gli utenti Skype for Business online e Piani per chiamate, la segreteria telefonica del Sistema telefonico viene configurata e messa in servizio automaticamente per gli utenti una volta assegnata una licenza **Sistema telefonico** e un numero di telefono.

1. Se la funzione Sistema telefonico non è inclusa nel tuo piano, può essere necessario acquistare licenze per il componente aggiuntivo **Sistema telefonico**. Inoltre è necessario acquistare una licenza Exchange Online. Consulta [Licenze per componenti aggiuntivi di Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

2. [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) e le[Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) e le licenze Exchange Online ai dipendenti dell'azienda. Terminate queste operazioni, potranno ricevere i messaggi vocali.

3. Il supporto per la trascrizione segreteria telefonica è stato aggiunto a partire da marzo 2017 ed è attivato per impostazione predefinita per tutte le organizzazioni e gli utenti. Puoi disattivare la trascrizione per la tua organizzazione usando Windows PowerShell e attenendoti alle seguenti istruzioni.

## <a name="phone-system-with-on-premises-environments"></a>Sistema telefonico con ambienti locali

Le seguenti informazioni indicano come configurare la segreteria telefonica del Sistema telefonico con ambienti con Piano per chiamate locale.

1. Se la funzione Sistema telefonico non è inclusa nel tuo piano, può essere necessario acquistare licenze per il componente aggiuntivo **Sistema telefonico**. Inoltre è necessario acquistare una licenza Exchange Online. Consulta [Licenze per componenti aggiuntivi di Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

2. [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) e le[Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) e le licenze Exchange Online ai dipendenti dell'azienda.

3. Segui le istruzioni illustrate nella sezione **Abilitare gli utenti per i servizi vocali Sistema telefonico e segreteria telefonica** della guida[Configurare Skype for Business Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605228.aspx).

4. Il supporto per la trascrizione segreteria telefonica è stato aggiunto a partire da marzo 2017 ed è attivato per impostazione predefinita per tutte le organizzazioni e gli utenti. Puoi disattivare la trascrizione per la tua organizzazione usando Windows PowerShell e attenendoti alle seguenti istruzioni.

5. Puoi anche consultare l'[Assistenza per segreteria telefonica Azure PBX per Exchange Server](https://support.microsoft.com/en-us/kb/3195158) per sapere come configurare la consegna dei messaggi vocali Azure per gli utenti di Sistema telefonico con una cassetta postale locale.

## <a name="setting-voicemail-policies-in-your-organization"></a>Impostazione dei criteri di segreteria telefonica dell'organizzazione

La trascrizione della segreteria telefonica è abilitata per impostazione predefinita e il mascheramento di volgarità è disabilitato per impostazione predefinita per tutte le organizzazioni e utenti. Tuttavia, è possibile controllarli utilizzando il cmdlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx).

> [!IMPORTANT]
> Non è possibile creare una nuova istanza di criteri trascrizione utilizzando il cmdlet **New-CsOnlineVoiceMailPolicy** e non è possibile rimuovere un'istanza di criteri esistente utilizzando il cmdlet **Remove-CsOnlineVoiceMailPolicy**.

È possibile gestire le impostazioni di trascrizione per gli utenti che utilizzano i criteri di segreteria telefonica. Per visualizzare tutte le istanze di criteri di segreteria telefonica disponibili, è possibile utilizzare il cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

 **PS C:\\> Get-CsOnlineVoicemailPolicy**

![Get-CsOnlineVoiceMailPolicy finestra risultati.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)

### <a name="turning-off-transcription-for-your-organization"></a>Disattivare la trascrizione per la propria organizzazione

Dato che l'impostazione predefinita per la trascrizione è attiva per la propria organizzazione, si consiglia di disabilitarla utilizzando il cmdlet [set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Per farlo, eseguire quanto segue:

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Attivazione del mascheramento di volgarità sulla trascrizione per la propria organizzazione

Il mascheramento di volgarità sulla trascrizione è disabilitato per impostazione predefinita per l'organizzazione. Se non vi è un requisito aziendale per abilitarlo, è possibile abilitare il mascheramento di volgarità sulla trascrizione tramite [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Per farlo, eseguire:

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Disattivare la trascrizione per un utente

I criteri utente vengono valutati prima delle impostazioni predefinite dell'organizzazione. Ad esempio, se la trascrizione segreteria telefonica è abilitata per tutti gli utenti è possibile assegnare un criterio per disabilitare la trascrizione per un utente specifico utilizzando il cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).

Per disabilitare la trascrizione per un singolo utente, eseguire:

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Attivazione del mascheramento di volgarità sulla trascrizione per un utente

Per abilitare il mascheramento di volgarità sulla trascrizione per un utente specifico, è possibile assegnare un criterio per abilitare il mascheramento di volgarità sulla trascrizione per un utente specifico utilizzando il cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx).

Per abilitare il mascheramento di volgarità sulla trascrizione per un singolo utente, eseguire:

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Il servizio di segreteria telefonica in Office 365 memorizza in cache i criteri di segreteria telefonica e aggiorna la cache ogni 4 ore. Perciò le modifiche apportate ai criteri possono impiegare fino a 4 ore per essere applicate.

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Aiutare gli utenti a imparare le funzioni della segreteria telefonica Skype for Business

Abbiamo informazioni e articoli di formazione per aiutare gli utenti a usare con successo la segreteria telefonica Skype for Business. Questi sono gli articoli che gli utenti vorranno consultare:

- [Controllare le opzioni e la segreteria telefonica di Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Questo articolo illustra come ascoltare i messaggi vocali in Skype for Business e ascoltare i messaggi vocali a velocità diverse.

- [Formazione per Skype for Business 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business Online](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[Ecco cosa offre il Sistema telefonico in Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)


