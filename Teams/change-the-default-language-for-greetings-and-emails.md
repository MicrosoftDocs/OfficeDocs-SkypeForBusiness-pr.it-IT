---
title: Modificare la lingua predefinita per i messaggi di saluto e le e-mail
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: Informazioni su come configurare Microsoft Teams e Skype for Business per l'uso di un'altra lingua per il messaggio di saluto predefinito della segreteria telefonica dell'organizzazione.
ms.openlocfilehash: 5e486e94470fd6303d132fdaa9c23b0ca6f65b98
ms.sourcegitcommit: 4435ac0efcb95e4e5e1f21289e46761e79482ab5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2022
ms.locfileid: "65624090"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a>Modificare la lingua predefinita per i messaggi di saluto e le e-mail

Cloud Voicemail usa varie impostazioni della lingua per riprodurre i saluti, generare traduzioni di trascrizione e generare messaggi della segreteria telefonica. Le impostazioni della lingua possono essere specificate per impostazione predefinita a livello di tenant, in base ai criteri o singolarmente a un determinato utente.

## <a name="greetings"></a>Saluti
I saluti vengono riprodotti al chiamante che lascia la segreteria telefonica e può essere dei tipi seguenti:

- Messaggi di saluto del sistema
- Saluti personalizzati registrati dall'utente chiamato
- Messaggio di saluto personalizzato per la sintesi vocale specificato per l'utente chiamato

La lingua usata per riprodurre il messaggio di saluto del sistema è, in ordine di priorità, la lingua del prompt principale e secondaria specificata nei criteri della segreteria telefonica online assegnati all'utente, la lingua preferita specificata per l'utente o la lingua del tenant predefinita.

Il saluto personalizzato e fuori sede viene registrato dall'utente nella lingua scelta dall'utente.

Se per l'utente vengono specificati saluti di sintesi vocale personalizzati dall'utente o dall'amministratore del tenant, la lingua usata per generare il riconoscimento vocale è la lingua PromptLanguage specificata insieme ai saluti di sintesi vocale.

I saluti di sintesi vocale personalizzati vengono usati solo se non sono registrati messaggi di saluto personalizzati per l'utente.

## <a name="transcription"></a>Trascrizione
Se abilitata dai criteri della segreteria telefonica online per l'utente chiamato, Cloud Voicemail tenterà di trascrivere la segreteria telefonica lasciata dal chiamante. Utilizzerà il rilevamento vocale per comprendere la lingua utilizzata nel contenuto audio e, se possibile, trascrivere il contenuto utilizzando la lingua rilevata.

## <a name="transcription-translation"></a>Traduzione trascrizione
Se abilitata dai criteri della segreteria telefonica online per l'utente chiamato, Cloud Voicemail traduce la segreteria telefonica trascritta. Verrà tradotta dalla lingua rilevata durante il rilevamento del riconoscimento vocale in, in ordine di priorità, la lingua preferita specificata per l'utente o la lingua tenant predefinita.

## <a name="voicemail-message-template"></a>Modello di messaggio segreteria telefonica
Cloud Voicemail genererà il messaggio della segreteria telefonica usando un modello di lingua basato, in ordine di priorità, sulla lingua preferita specificata per l'utente o sulla lingua del tenant predefinita.

## <a name="setting-the-preferred-language-for-a-user"></a>Impostazione della lingua preferita per un utente
È possibile impostare la lingua preferita per un utente che usa PowerShell in Azure Active Directory o nel Active Directory locale. Per altre informazioni, vedere [Come impostare le impostazioni di lingua e area geografica per Microsoft 365 o Office 365](/office365/troubleshoot/access-management/set-language-and-region).

Gli utenti possono modificare la propria lingua preferita tramite le impostazioni dopo l'accesso. Per altre informazioni, vedere [Cambiare la lingua visualizzata e il fuso orario in Microsoft 365 for Business](https://support.office.com/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)

## <a name="change-the-system-language-for-everyone-in-your-organization"></a>Cambiare la lingua di sistema per tutti i membri dell'organizzazione.

1. Accedere con [l'account di amministratore globale all'indirizzo](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).

2. Nella interfaccia di amministrazione di Microsoft 365 scegliere **Impostazioni** >  **ImpostazioniOrgImpostazioniOrganizzazione** >  **profilo**.
3. Scegliere **Informazioni sull'organizzazione**.
4. Scegli una lingua dall'elenco **Lingua preferita** per tutti i membri dell'organizzazione.
5. Scegli **Salva**.

**Le lingue disponibili sono determinate dalla località dell'organizzazione**. Ad esempio, se la tua organizzazione si trova negli Stati Uniti, puoi impostare inglese o spagnolo come lingua predefinita. Se la tua organizzazione si trova in Canada, puoi scegliere fra inglese e francese.

## <a name="supported-languages-in-cloud-voicemail"></a>Lingue supportate in Cloud Voicemail
Per un elenco delle lingue supportate in Cloud Voicemail per Microsoft Teams e Skype for Business, vedere [Cloud Voicemail lingue supportate](languages-for-voicemail-greetings-and-messages.md).
  

## <a name="custom-greeting-recorded-by-a-user"></a>Messaggio di saluto personalizzato registrato da un utente
Gli utenti possono registrare il proprio messaggio di saluto personalizzato e fuori sede. Vedi [Teams impostazioni del client desktop](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) e [Controlla Skype for Business la segreteria telefonica e le opzioni](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).

## <a name="custom-text-to-speech-greeting-specified-for-a-user"></a>Messaggio di saluto personalizzato per la sintesi vocale specificato per un utente
L'amministratore del tenant può specificare il messaggio di saluto personalizzato per la sintesi vocale di testo e la lingua del prompt per un utente utilizzando il cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) .

## <a name="custom-text-to-speech-greeting-specified-by-a-user"></a>Messaggio di saluto personalizzato per la sintesi vocale specificato da un utente
Gli utenti possono specificare messaggi di saluto personalizzati per la sintesi vocale e la lingua usata per i saluti. Per Microsoft Teams - Gli utenti possono modificare il messaggio di saluto della segreteria telefonica dalle [impostazioni del client desktop Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f). Per Skype for Business - [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) e scegliere una nuova lingua in **Lingua prompt**. 


## <a name="related-articles"></a>Articoli correlati

[Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings)

[Get-CsOnlineVoicemailUserSettings](/powershell/module/skype/get-csonlinevoicemailusersettings)

[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

[Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)
