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
description: 'Informazioni su come configurare la segreteria telefonica cloud per gli utenti. '
ms.openlocfilehash: df8e6d5962e3bff2148165466400e90ee3a4607d
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031072"
---
# <a name="set-up-cloud-voicemail"></a>Configurare Cloud Voicemail

Questo articolo riguarda l'amministratore di Microsoft 365 o Office 365, come descritto in [informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) che vogliono configurare la funzionalità per la segreteria telefonica cloud per tutti gli utenti dell'azienda.

> [!NOTE]
> Cloud Voicemail supporta il deposito dei messaggi della segreteria telefonica solo in una cassetta postale di Exchange e non supporta sistemi di posta elettronica di terze parti. 

> [!NOTE]
> Quando un delegato risponde a una chiamata per conto di un delegante, le notifiche non sono disponibili nel cloud Voicemail. Gli utenti possono ricevere notifiche per le chiamate perse.

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>Ambienti solo cloud: configurare la segreteria telefonica cloud per gli utenti del sistema telefonico online

Per gli utenti del sistema telefonico online, cloud Voicemail viene configurato automaticamente e provisionato per gli utenti dopo l'assegnazione di una licenza per il **sistema telefonico** agli utenti. 

> [!NOTE]
> Per gli utenti di sistemi telefonici Skype for business online con numeri di telefono forniti in locale, potrebbe essere necessario abilitare la segreteria telefonica ospitata con [Set-CsUser-HostedVoicemail $true](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps). 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurare cloud Voicemail per gli utenti di cassette postali di Exchange Server

Le informazioni seguenti includono la configurazione della segreteria telefonica cloud per l'utilizzo con gli utenti online per il sistema telefonico, ma con la cassetta postale in Exchange Server. 
  
1. I messaggi della segreteria telefonica vengono recapitati alla cassetta postale di Exchange degli utenti tramite SMTP instradato tramite Exchange Online Protection. Per consentire il corretto recapito di questi messaggi, verificare che i connettori di Exchange siano configurati correttamente tra i server Exchange e la protezione di Exchange Online. [Usare i connettori per configurare il flusso di posta](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow). 

2. Per abilitare le caratteristiche della segreteria telefonica, ad esempio la personalizzazione dei messaggi di saluto e la segreteria telefonica visiva nei client Skype for business, è necessaria la connettività da Microsoft 365 o Office 365 alla cassetta postale di Exchange Server tramite servizi Web Exchange. Per abilitare questa connettività, è necessario configurare il nuovo protocollo di autenticazione OAuth di Exchange descritto in [configurare l'autenticazione OAuth tra le organizzazioni Exchange e Exchange Online](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)oppure eseguire la procedura guidata ibrida di Exchange da Exchange 2013 CU5 o versione successiva. Inoltre, è necessario configurare Integration e OAuth tra Skype for business online ed Exchange Server descritto in [configurare Integration e OAuth tra Skype for business online ed Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises). 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Configurare cloud Voicemail per gli utenti di Skype for Business Server

Per configurare gli utenti di Skype for Business Server per la segreteria telefonica cloud, vedere [pianificare il servizio di segreteria cloud per gli utenti locali](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail).

## <a name="enabling-protected-voicemail-in-your-organization"></a>Abilitazione della segreteria telefonica protetta nell'organizzazione

Quando qualcuno lascia un messaggio vocale per un utente dell'organizzazione, la segreteria telefonica viene recapitata alla cassetta postale dell'utente come allegato di un messaggio di posta elettronica. Uso delle regole del flusso di posta per applicare la crittografia dei messaggi, è possibile impedire che i messaggi della segreteria telefonica vengano inoltrati ad altri destinatari. Quando si Abilita la segreteria telefonica protetta, gli utenti possono ascoltare i messaggi vocali protetti chiamandoli nella cassetta postale della segreteria telefonica o aprendo il messaggio in Outlook, Outlook sul Web o in Outlook per Android o iOS. Non è possibile aprire messaggi vocali protetti in Skype for business.

Per altre informazioni sulla crittografia dei messaggi, vedere [crittografia della posta elettronica](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).

Per configurare la segreteria telefonica protetta, eseguire le operazioni seguenti:

1. Accedere https://admin.microsoft.com e accedere usando un account con autorizzazioni di amministratore globale.
2. Selezionare **Mostra tutto** e quindi vai a interfaccia di **Amministrazione** di  >  **Exchange**.
3. Nell'interfaccia di amministrazione di Exchange selezionare **regole flusso di posta**  >  **Rules**.
4. Selezionare **+** **Aggiungi** e quindi applicare la **crittografia dei messaggi di Office 365 e i diritti di protezione ai messaggi**.
5. Specificare un nome per la nuova regola del flusso di posta e quindi in **applica questa regola se** selezionare **le proprietà del messaggio**  >  **includono il tipo di messaggio** segreteria  >  **telefonica**. Selezionare **OK**.
6. In **eseguire le operazioni seguenti** selezionare **Applica crittografia messaggi di Office 365 e protezione dei diritti al messaggio con** e quindi selezionare **selezionarne uno**. In **modello RMS** selezionare non **inoltrare**. Selezionare **OK** e quindi **Salva**.
    > [!NOTE]
    > Se l'elenco di **modelli RMS** è vuoto, è necessario configurare la crittografia dei messaggi. Per altre informazioni sulla configurazione della crittografia dei messaggi, vedere gli articoli seguenti:
    > - [Configurare nuove funzionalità di crittografia messaggi](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Configurazione e gestione di modelli per la protezione delle informazioni di Azure](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [Opzione non inoltra per i messaggi di posta elettronica](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>Impostazione dei criteri di segreteria telefonica dell'organizzazione

> [!WARNING]
> Per i clienti Skype for business, la disabilitazione della segreteria telefonica tramite un criterio di chiamata di Microsoft teams può anche disabilitare il servizio di segreteria telefonica per gli utenti di Skype for business.

La trascrizione della segreteria telefonica è abilitata per impostazione predefinita e il mascheramento di volgarità è disabilitato per impostazione predefinita per tutte le organizzazioni e utenti. Tuttavia, è possibile controllarli utilizzando il cmdlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

I messaggi della segreteria telefonica ricevuti dagli utenti dell'organizzazione vengono trascritti nell'area geografica in cui è ospitata l'organizzazione Microsoft 365 o Office 365. L'area in cui è ospitato il tenant potrebbe non essere la stessa area in cui si trova l'utente che riceve il messaggio della segreteria telefonica. Per visualizzare l'area geografica in cui è ospitato il tenant, accedere alla pagina del [profilo dell'organizzazione](https://go.microsoft.com/fwlink/p/?linkid=2067339) e quindi fare clic su **Visualizza dettagli** accanto a **posizione dati**.

> [!IMPORTANT]
> Non è possibile creare una nuova istanza di criteri per la trascrizione e la trascrizione delle maschere profane usando il cmdlet **New-CsOnlineVoiceMailPolicy** e non è possibile rimuovere un'istanza di criteri esistente usando il cmdlet **Remove-CsOnlineVoiceMailPolicy** .

È possibile gestire le impostazioni di trascrizione per gli utenti che utilizzano i criteri segreteria telefonica. Per visualizzare tutte le istanze dei criteri di segreteria telefonica disponibili, è possibile usare il cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .

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

I criteri utente vengono valutati prima delle impostazioni predefinite dell'organizzazione. Ad esempio, se la trascrizione della segreteria telefonica è abilitata per tutti gli utenti, puoi assegnare un criterio per disabilitare la trascrizione per un utente specifico usando il cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .

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
> Il servizio di segreteria telefonica in Microsoft 365 e Office 365 memorizza nella cache i criteri della segreteria telefonica e aggiorna la cache ogni 4 ore. Perciò le modifiche apportate ai criteri possono impiegare fino a 4 ore per essere applicate.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Aiutare gli utenti a conoscere le caratteristiche della segreteria telefonica

Per gli utenti sono disponibili le informazioni seguenti per gestire le impostazioni della segreteria telefonica e altre funzionalità di chiamata in teams:

- [Gestire le impostazioni delle chiamate in teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f). Questo articolo illustra come gestire tutti i team di utenti finali che chiamano le funzionalità. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Aiutare gli utenti a imparare le funzioni della segreteria telefonica Skype for Business

Abbiamo informazioni e articoli di formazione per aiutare gli utenti a usare con successo la segreteria telefonica Skype for Business. Questi sono gli articoli che gli utenti vorranno consultare:

- [Controllare le opzioni e la segreteria telefonica di Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Questo articolo illustra come ascoltare i messaggi vocali in Skype for Business e ascoltare i messaggi vocali a velocità diverse.

- [Formazione per Skype for Business 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Vantaggi offerti dal Sistema telefonico](here-s-what-you-get-with-phone-system.md)

[Pianificare la migrazione per Skype for Business Server ed Exchange Server](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
