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
ms.openlocfilehash: f448ba79c2451383c0ca85916309bdfab3b69a96
ms.sourcegitcommit: 279ab5236431961c5181e2c01a69e5aa4290d381
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2021
ms.locfileid: "60462370"
---
# <a name="set-up-cloud-voicemail"></a>Configurare Cloud Voicemail

Questo articolo è per l'amministratore Microsoft 365 o Office 365, come descritto [in](/microsoft-365/admin/add-users/about-admin-roles) Informazioni sui ruoli di amministratore che vogliono configurare la caratteristica Cloud Voicemail per tutti gli utenti dell'azienda. Cloud Voicemail richiede Exchange cassette postali per gli utenti in cui deposita i messaggi della segreteria telefonica. Non supporta sistemi di posta elettronica di terze parti.

## <a name="cloud-voicemail-for-teams-users"></a>Cloud Voicemail per Teams utenti

Per Teams utenti, Cloud Voicemail viene configurato ed eseguito automaticamente il provisioning. Per Microsoft Teams Telefono non è necessaria una licenza Cloud Voicemail.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Aiutare gli utenti a imparare a Teams della segreteria telefonica

Per gli utenti sono disponibili le informazioni seguenti sull'uso e la gestione della segreteria telefonica in Teams:

- [Controlla la segreteria telefonica in Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Gestire le impostazioni delle chiamate in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

## <a name="setting-up-cloud-voicemail-to-work-with-on-premises-users"></a>Configurazione di Cloud Voicemail per l'utilizzo con utenti locali

È possibile usare Cloud Voicemail per fornire funzionalità di segreteria telefonica agli utenti che dispongono di cassette postali nei server Exchange o agli utenti che usano Skype for Business Server. Questa sezione fornisce informazioni per questi scenari. 

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurare le Cloud Voicemail per gli utenti Exchange Server cassette postali

Le informazioni seguenti riguardano la configurazione Cloud Voicemail per l'utilizzo con Microsoft Teams Telefono utenti che hanno la propria cassetta postale Exchange Server.

1. I messaggi della segreteria telefonica vengono recapitati alla cassetta postale Exchange degli utenti tramite SMTP instradati tramite Exchange Online Protection. Per abilitare il recapito corretto di questi messaggi, assicurarsi che i connettori Exchange siano configurati correttamente tra i server Exchange e i Exchange Online Protection; [Usare Connettori per configurare la posta Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

2. Per abilitare le funzionalità della segreteria telefonica, come la personalizzazione dei messaggi di saluto e la segreteria telefonica visiva nei client Skype for Business, è necessaria la connettività da Microsoft 365 o Office 365 alla cassetta postale del server Exchange tramite servizi Web Exchange. Per abilitare questa connettività, è necessario configurare il nuovo protocollo di autenticazione Oauth di Exchange descritto in Configurare l'autenticazione [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)tra organizzazioni di Exchange e Exchange Online oppure eseguire la procedura guidata ibrida di Exchange da Exchange 2013 CU5 o versione successiva. È inoltre necessario configurare l'integrazione e Oauth tra Skype for Business Online e il server Exchange descritto in Configurare l'integrazione e [OAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)tra Skype for Business Online e Exchange Server .

### <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Configurare le Cloud Voicemail per Skype for Business Server utenti

Per configurare Skype for Business server per Cloud Voicemail, vedere Pianificare Cloud Voicemail servizio per gli [utenti locali.](/skypeforbusiness/hybrid/plan-cloud-voicemail)

## <a name="enabling-protected-voicemail-in-your-organization"></a>Abilitazione della segreteria telefonica protetta nell'organizzazione

Quando un utente lascia un messaggio della segreteria telefonica per un utente dell'organizzazione, la segreteria telefonica viene recapitata alla cassetta postale dell'utente come allegato di un messaggio di posta elettronica. Usando le regole del flusso di posta elettronica per applicare la crittografia dei messaggi, è possibile impedire l'inoltro di tali messaggi della segreteria telefonica ad altri destinatari. Quando si abilita la segreteria telefonica protetta, gli utenti possono ascoltare i messaggi della segreteria telefonica protetti chiamando nella propria cassetta postale o aprendo il messaggio in Outlook, Outlook sul web o in Outlook per Android o iOS. I messaggi della segreteria telefonica protetta non possono essere aperti in Skype for Business o Microsoft Teams.

Per altre informazioni sulla crittografia dei messaggi, vedere [Definire le regole del flusso di posta per crittografare i messaggi di posta elettronica.](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)
