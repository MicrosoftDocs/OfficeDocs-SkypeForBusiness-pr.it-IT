---
title: Configurare Cloud Voicemail
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Informazioni su come configurare le Cloud Voicemail per gli utenti.
ms.openlocfilehash: f4547d081cf7b0175da7222bf68fde97cecd21c9
ms.sourcegitcommit: d23185cf6caeeeb055c36609e7c788a2b2e8d07d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2021
ms.locfileid: "60367508"
---
# <a name="set-up-cloud-voicemail"></a>Configurare Cloud Voicemail

Questo articolo è per l'amministratore Microsoft 365 o Office 365, come descritto [in](/microsoft-365/admin/add-users/about-admin-roles) Informazioni sui ruoli di amministratore che vogliono configurare la caratteristica Cloud Voicemail per tutti gli utenti dell'azienda.

> [!NOTE]
> Cloud Voicemail supporta il deposito dei messaggi della segreteria telefonica solo in una cassetta postale Exchange e non supporta sistemi di posta elettronica di terze parti.

> [!NOTE]
> Quando un delegato risponde a una chiamata per conto di un delegato, le notifiche non sono disponibili in Cloud Voicemail. Gli utenti possono ricevere notifiche per le chiamate perse.

## <a name="cloud-voicemail-for-teams-users"></a>Cloud Voicemail per Teams utenti

Per Teams utenti, Cloud Voicemail viene configurato ed eseguito automaticamente il provisioning. Si noti che per Sistema telefonico non è necessaria una licenza Cloud Voicemail.

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurare i Cloud Voicemail per gli utenti Exchange Server cassette postali

Le informazioni seguenti riguardano la configurazione Cloud Voicemail per l'utilizzo con utenti online per Sistema telefonico ma che hanno la propria cassetta postale Exchange Server.

1. I messaggi della segreteria telefonica vengono recapitati alla cassetta postale Exchange degli utenti tramite SMTP instradati tramite Exchange Online Protection. Per abilitare il recapito corretto di questi messaggi, assicurarsi che i connettori Exchange siano configurati correttamente tra i server di Exchange e Exchange Online Protection; [Usare Connettori per configurare la posta Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

2. Per abilitare le funzionalità della segreteria telefonica, ad esempio la personalizzazione dei messaggi di saluto e della segreteria telefonica visiva nei client Skype for Business, è necessaria la connettività da Microsoft 365 o Office 365 alla cassetta postale del server Exchange tramite servizi Web Exchange. Per abilitare questa connettività, è necessario configurare il nuovo protocollo di autenticazione Oauth di Exchange descritto in Configurare l'autenticazione [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)tra le organizzazioni di Exchange e Exchange Online oppure eseguire la procedura guidata ibrida di Exchange da Exchange 2013 CU5 o versione successiva. È inoltre necessario configurare l'integrazione e Oauth tra Skype for Business Online e il server Exchange descritto in Configurare l'integrazione e [OAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)tra Skype for Business Online e Exchange Server .

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Configurare le Cloud Voicemail per Skype for Business Server utenti

Per configurare Skype for Business utenti del server per Cloud Voicemail, vedere Pianificare Cloud Voicemail per gli utenti [locali.](/skypeforbusiness/hybrid/plan-cloud-voicemail)

## <a name="enabling-protected-voicemail-in-your-organization"></a>Abilitazione della segreteria telefonica protetta nell'organizzazione

Quando un utente lascia un messaggio della segreteria telefonica per un utente dell'organizzazione, la segreteria telefonica viene recapitata alla cassetta postale dell'utente come allegato di un messaggio di posta elettronica. Usando le regole del flusso di posta elettronica per applicare la crittografia dei messaggi, è possibile impedire l'inoltro di tali messaggi della segreteria telefonica ad altri destinatari. Quando si abilita la segreteria telefonica protetta, gli utenti possono ascoltare i messaggi della segreteria telefonica protetti chiamando nella propria cassetta postale o aprendo il messaggio in Outlook, Outlook sul web o in Outlook per Android o iOS. I messaggi della segreteria telefonica protetta non possono essere aperti in Skype for Business o Microsoft Teams.

Per altre informazioni sulla crittografia dei messaggi, vedere [Crittografia della posta elettronica](/microsoft-365/compliance/email-encryption).

> [!NOTE]
> La crittografia viene applicata alla segreteria telefonica solo quando la chiamata viene da un utente interno. Se la chiamata viene da un utente esterno, la segreteria telefonica non verrà crittografata.

Per configurare la segreteria telefonica protetta, eseguire le operazioni seguenti:

1. Passare a <https://admin.microsoft.com> e accedere con un account con autorizzazioni di amministratore globale.
2. Selezionare **Mostra tutto** e quindi passare a Interfaccia di **amministrazione**  >  **Exchange**.
3. Nell'Exchange di amministrazione selezionare **Regole flusso di**  >  **posta**.
4. Selezionare Aggiungi e quindi selezionare Applica Office 365 Message Encryption **+** protezione dei diritti **ai messaggi**.
5. Specificare un nome per la nuova regola del flusso di posta e quindi in Applica questa regola **se** selezionare Le proprietà del messaggio Includono il tipo di messaggio  >   \> **Segreteria telefonica.** Scegliere **OK**.
6. In **Eseguire le operazioni seguenti** selezionare Applica Office 365 Message Encryption e protezione dei **diritti** al messaggio con e quindi selezionare **Seleziona uno**. In **Modello RMS** selezionare Non **inoltrare**. Selezionare **OK** e quindi **Salva**.

    > [!NOTE]
    > Se **l'elenco dei** modelli RMS è vuoto, è necessario configurare Crittografia messaggi. Per altre informazioni sulla configurazione di Message Encryption, vedere gli articoli seguenti:
    >
    > - [Configurare nuove funzionalità di Crittografia messaggi](/microsoft-365/compliance/set-up-new-message-encryption-capabilities)
    > - [Configurazione e gestione di modelli per Azure Information Protection](/information-protection/deploy-use/configure-policy-templates)
    > - [Opzione Non inoltrare per i messaggi di posta elettronica](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

    > [!NOTE]
    > È necessario impostare la chiave del Registro di sistema seguente per gli utenti, le aziende e le organizzazioni che vogliono visualizzare il modulo segreteria telefonica: [HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Outlook\Addins] "AllowVoicemailForm"=dword:00000001

## <a name="help-your-users-learn-teams-voicemail-features"></a>Aiutare gli utenti a imparare a Teams della segreteria telefonica

Per gli utenti sono disponibili le informazioni seguenti sulla gestione delle impostazioni della segreteria telefonica e su altre funzionalità per le chiamate in Teams:

- [Gestisci le impostazioni della chiamata in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f). Questo articolo spiega come gestire tutte le funzionalità per le chiamate Teams per gli utenti finali.

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Aiutare gli utenti a imparare le funzioni della segreteria telefonica Skype for Business

Abbiamo informazioni e articoli di formazione per aiutare gli utenti a usare con successo la segreteria telefonica Skype for Business. Questi sono gli articoli che gli utenti vorranno consultare:

- [Controllare le opzioni e la segreteria telefonica di Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Questo articolo illustra come ascoltare i messaggi vocali in Skype for Business e ascoltare i messaggi vocali a velocità diverse.

- [Formazione per Skype for Business 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Argomenti correlati

[Configurare Skype for Business online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Vantaggi offerti dal Sistema telefonico](here-s-what-you-get-with-phone-system.md)

[Pianificare la migrazione per Skype for Business Server ed Exchange Server](/SkypeForBusiness/hybrid/plan-um-migration)
