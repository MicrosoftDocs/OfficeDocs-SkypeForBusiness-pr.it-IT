---
title: Configurare Cloud Voicemail
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Scopri come configurare cloud voicemail per gli utenti. '
ms.openlocfilehash: 81e5f83b251a0bd648cb2ab2afd69f35357fc49f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662211"
---
# <a name="set-up-cloud-voicemail"></a>Configurare Cloud Voicemail

Questo articolo è per l'amministratore di Microsoft 365 o Office 365, come descritto [in](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) Informazioni sui ruoli di amministratore che vogliono configurare la funzionalità Cloud Voicemail per tutti gli utenti dell'azienda.

> [!NOTE]
> Cloud Voicemail supporta la registrazione di messaggi vocali solo in una cassetta postale di Exchange e non supporta i sistemi e-mail di terze parti. 

> [!NOTE]
> Quando un delegato risponde a una chiamata per conto di un delegante, le notifiche non sono disponibili in Cloud Voicemail. Gli utenti possono ricevere notifiche per le chiamate perse.

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>Ambienti solo cloud: configurare Cloud Voicemail per gli utenti del Sistema telefonico online

Per gli utenti di Sistema telefonico online, la segreteria telefonica cloud  viene automaticamente impostata ed eseguita il provisioning per gli utenti dopo l'assegnazione di una licenza Sistema telefonico agli utenti. 

> [!NOTE]
> Per gli utenti del Sistema telefonico Skype for Business online con numeri di telefono locali, potrebbe essere necessario abilitare la segreteria telefonica ospitata con [set-CsUser -HostedVoicemail $True.](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurare Cloud Voicemail per gli utenti Exchange Server cassette postali

Le informazioni seguenti riguardano la configurazione della segreteria telefonica cloud per l'uso con utenti online per il Sistema telefonico, ma che hanno la propria cassetta postale Exchange Server. 
  
1. I messaggi della segreteria telefonica vengono recapitati alla cassetta postale di Exchange degli utenti tramite SMTP instradato tramite Exchange Online Protection. Per abilitare il recapito corretto di questi messaggi, assicurarsi che Exchange Connectors sia configurato correttamente tra i server Exchange e Exchange Online Protection; [Usare i connettori per configurare il flusso di posta.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 

2. Per abilitare le funzionalità della segreteria telefonica, come la personalizzazione dei saluti e la visualizzazione della segreteria telefonica nei client Skype for Business, è necessaria la connettività da Microsoft 365 o Office 365 alla cassetta postale del server Exchange tramite Servizi Web Exchange. Per abilitare questa connettività, è necessario configurare il nuovo protocollo di autenticazione Oauth di Exchange descritto in Configurare l'autenticazione [OAuth](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)tra le organizzazioni di Exchange ed Exchange Online oppure eseguire la Procedura guidata ibrida di Exchange da Exchange 2013 CU5 o versione successiva. Inoltre, è necessario configurare l'integrazione e l'autenticazione tra Skype for Business Online ed Exchange Server descritto in Configurare l'integrazione e [OAuth tra Skype for Business online e Exchange Server.](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises) 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Configurare cloud voicemail per gli utenti di Skype for Business Server

Per configurare gli utenti server di Skype for Business per la segreteria telefonica cloud, consulta Pianificare il servizio [Cloud Voicemail per gli utenti locali.](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)

## <a name="enabling-protected-voicemail-in-your-organization"></a>Abilitazione della segreteria telefonica protetta nell'organizzazione

Quando un utente lascia un messaggio della segreteria telefonica per un utente dell'organizzazione, il messaggio viene recapitato alla cassetta postale dell'utente come allegato di un messaggio di posta elettronica. Usando le regole del flusso di posta per applicare la crittografia dei messaggi, è possibile impedire l'inoltro dei messaggi della segreteria telefonica ad altri destinatari. Quando si abilita la segreteria telefonica protetta, gli utenti possono ascoltare i messaggi della segreteria telefonica protetti chiamando nella propria casella vocale o aprendo il messaggio in Outlook, Outlook sul Web o in Outlook per Android o iOS. I messaggi di segreteria telefonica protetti non possono essere aperti in Skype for Business o Microsoft Teams.

Per altre informazioni sulla crittografia dei messaggi, vedere [Crittografia della posta elettronica.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)

Per configurare la segreteria telefonica protetta, procedere come segue:

1. Accedere con un account con autorizzazioni https://admin.microsoft.com di amministratore globale e accedere.
2. Selezionare **Mostra tutto** e quindi passare a Interfaccia di amministrazione **di**  >  **Exchange.**
3. Nell'interfaccia di amministrazione di Exchange selezionare **Regole flusso di**  >  **posta.**
4. Selezionare **+** **Aggiungi** e quindi Applica protezione di **Office 365 Message Encryption e dei diritti ai messaggi.**
5. Specificare un nome per la nuova regola del flusso di posta e quindi in Applica questa regola **se** selezionare Le proprietà del messaggio Includono il tipo  >  **di messaggio** Segreteria  >  **telefonica.** Scegliere **OK.**
6. In **Eseguire le operazioni seguenti** selezionare Applica office **365 Message Encryption e** protezione dei diritti al messaggio con, quindi **selezionarne uno.** Nel **modello RMS** selezionare Non **inoltrare.** Selezionare **OK** e quindi **Salva.**
    > [!NOTE]
    > Se **l'elenco dei** modelli RMS è vuoto, è necessario configurare Message Encryption. Per altre informazioni sulla configurazione di Message Encryption, vedere gli articoli seguenti:
    > - [Configurare nuove funzionalità di crittografia dei messaggi](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Configurazione e gestione di modelli per Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [Opzione Non inoltrare per i messaggi di posta elettronica](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>Impostazione dei criteri di segreteria telefonica dell'organizzazione

> [!WARNING]
> Per i clienti Skype for Business, la disabilitazione della segreteria telefonica tramite un criterio di chiamata di Microsoft Teams potrebbe anche disabilitare il servizio di segreteria telefonica per gli utenti Skype for Business.

La trascrizione della segreteria telefonica è abilitata per impostazione predefinita e il mascheramento di volgarità è disabilitato per impostazione predefinita per tutte le organizzazioni e utenti. Tuttavia, è possibile controllarli utilizzando il cmdlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

I messaggi di segreteria telefonica ricevuti dagli utenti dell'organizzazione sono trascritti nell'area geografica in cui è ospitata l'organizzazione di Microsoft 365 o Office 365. L'area geografica in cui è ospitato il tenant potrebbe non essere la stessa area geografica in cui si trova l'utente che riceve il messaggio della segreteria telefonica. Per visualizzare l'area geografica in cui [](https://go.microsoft.com/fwlink/p/?linkid=2067339) è ospitato il tenant, passare alla pagina del profilo organizzazione e quindi fare clic su Visualizza dettagli **accanto** a **Posizione dati.**

> [!IMPORTANT]
> Non puoi creare una nuova istanza di criteri per mascherare le profanità della trascrizione e della trascrizione utilizzando il cmdlet **New-CsOnlineVoiceMailPolicy** e non puoi rimuovere un'istanza di criteri esistente utilizzando il cmdlet **Remove-CsOnlineVoiceMailPolicy.**

È possibile gestire le impostazioni di trascrizione per gli utenti che utilizzano i criteri segreteria telefonica. Per visualizzare tutte le istanze di criteri segreteria telefonica disponibili, puoi utilizzare il cmdlet [Get-CsOnlineVoicemailPolicy.](https://technet.microsoft.com/library/mt798311.aspx)

 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy finestra risultati.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>Disattivare la trascrizione per la propria organizzazione

Dato che l'impostazione predefinita per la trascrizione è attiva per la propria organizzazione, si consiglia di disabilitarla utilizzando il cmdlet [set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Per farlo, eseguire quanto segue:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Attivazione del mascheramento di volgarità sulla trascrizione per la propria organizzazione

Il mascheramento di volgarità sulla trascrizione è disabilitato per impostazione predefinita per l'organizzazione. Se non vi è un requisito aziendale per abilitarlo, è possibile abilitare il mascheramento di volgarità sulla trascrizione tramite [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Per farlo, eseguire quanto segue:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Disattivare la trascrizione per un utente

I criteri utente vengono valutati prima delle impostazioni predefinite dell'organizzazione. Ad esempio, se la trascrizione segreteria telefonica è abilitata per tutti gli utenti, puoi assegnare un criterio per disabilitare la trascrizione per un utente specifico utilizzando il cmdlet [Grant-CsOnlineVoicemailPolicy.](https://technet.microsoft.com/library/mt798309.aspx)

Per disabilitare la trascrizione per un singolo utente, eseguire:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Attivazione del mascheramento di volgarità sulla trascrizione per un utente

Per abilitare il mascheramento di volgarità sulla trascrizione per un utente specifico, è possibile assegnare un criterio per abilitare il mascheramento di volgarità sulla trascrizione per un utente specifico utilizzando il cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).

Per abilitare il mascheramento di volgarità sulla trascrizione per un singolo utente, eseguire:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Il servizio di segreteria telefonica di Microsoft 365 e Office 365 memorizza nella cache i criteri della segreteria telefonica e aggiorna la cache ogni 4 ore. Perciò le modifiche apportate ai criteri possono impiegare fino a 4 ore per essere applicate.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Aiutare gli utenti a imparare le funzionalità di segreteria telefonica di Teams

Abbiamo le seguenti informazioni per gli utenti sulla gestione delle impostazioni della segreteria telefonica, oltre ad altre funzionalità di chiamata in Teams:

- [Gestisci le impostazioni delle chiamate in Teams.](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) Questo articolo spiega come gestire tutte le funzionalità di chiamata di Teams per l'utente finale. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Aiutare gli utenti a imparare le funzioni della segreteria telefonica Skype for Business

Abbiamo informazioni e articoli di formazione per aiutare gli utenti a usare con successo la segreteria telefonica Skype for Business. Questi sono gli articoli che gli utenti vorranno consultare:

- [Controllare le opzioni e la segreteria telefonica di Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Questo articolo illustra come ascoltare i messaggi vocali in Skype for Business e ascoltare i messaggi vocali a velocità diverse.

- [Formazione per Skype for Business 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Vantaggi offerti dal Sistema telefonico](here-s-what-you-get-with-phone-system.md)

[Pianificare la migrazione per Skype for Business Server ed Exchange Server](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
