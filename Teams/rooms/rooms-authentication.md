---
title: Autenticazione nelle chat room di Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-collaboration
description: Informazioni su come configurare l'autenticazione moderna per Microsoft Teams Rooms
ms.openlocfilehash: 93577c74005c8ad266739da0991f31e384a57ba6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117484"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Autenticazione nelle chat room di Microsoft Teams

La gestione degli account per i dispositivi Microsoft Teams Rooms viene gestita a livello di applicazione. L'applicazione si connette a Microsoft Teams, Skype for Business ed Exchange per ottenere risorse per l'account della sala per abilitare le esperienze di chiamata e riunione. Il dispositivo viene mantenuto indipendente dall'account per consentire funzionalità sempre disponibili, scenari di chiamata (per i dispositivi configurati con un piano di chiamata) e meccanismi di blocco personalizzati implementati in questi dispositivi. Questo significa che l'autenticazione per questi dispositivi avviene in modo diverso rispetto ai dispositivi degli utenti finali.  

L'autenticazione moderna è consigliata per tutti i clienti che usano dispositivi Microsoft Teams Rooms con Microsoft 365 o Office 365. Se si ha una distribuzione locale di Exchange Server o [](/office365/enterprise/hybrid-modern-auth-overview) Skype for Business server, configurare l'autenticazione moderna ibrida con Azure Active Directory (Azure AD) per abilitare l'uso dell'autenticazione moderna.

L'autenticazione moderna è supportata in Microsoft Teams Rooms versione 4.4.25.0 e successive.

## <a name="modern-authentication"></a>Autenticazione moderna

Quando si usa l'autenticazione moderna con l'applicazione Microsoft Teams Rooms, la libreria di autenticazione active directory (ADAL) viene usata per connettersi a Microsoft Teams, Exchange e Skype for Business. Un dispositivo Microsoft Teams Rooms è un dispositivo condiviso ed esegue un riavvio notturno per garantire un funzionamento fluido e ottenere aggiornamenti critici del sistema operativo, del driver, del firmware o delle applicazioni. Il meccanismo di autenticazione moderno usa il tipo di concessione di autorizzazione [password](/azure/active-directory/develop/v2-oauth-ropc) del proprietario della risorsa in OAuth 2.0, che non richiede l'intervento dell'utente. Questa è una delle principali differenze tra il funzionamento dell'autenticazione moderna per gli account utente e gli account delle risorse usati dall'applicazione Microsoft Teams Rooms. Per questo, gli account delle risorse di Microsoft Teams Rooms non devono essere configurati per l'uso dell'autenticazione a più fattori (MFA), dell'autenticazione con smart card o dell'autenticazione basata su certificati client (tutti disponibili per gli utenti finali).

L'altra differenza fondamentale tra il funzionamento dell'autenticazione moderna nei dispositivi Microsoft Teams Rooms e nei dispositivi degli utenti finali consiste nel fatto che non è possibile usare un account delle risorse per applicare criteri di accesso condizionale a livello di dispositivo in Azure Active Directory ed Endpoint Manager perché le informazioni sul dispositivo non vengono passate quando si usa questo tipo di concessione. È invece possibile registrare un dispositivo in Microsoft Endpoint Manager e applicare criteri di conformità usando le indicazioni fornite in Gestione delle sale riunioni di [Teams con Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Abilitare l'autenticazione moderna in un dispositivo Microsoft Teams Rooms

Per consentire alle chat room di Microsoft Teams di usare l'autenticazione moderna con Skype for Business ed Exchange, abilitare l'impostazione lato client per l'autenticazione moderna nel dispositivo Microsoft Teams Rooms. È possibile eseguire questa operazione nelle impostazioni del dispositivo o nel file di configurazione XML.

> [!NOTE]
> Prima di abilitare l'impostazione lato client per l'autenticazione moderna, assicurarsi che l'ambiente sia configurato correttamente per l'uso dell'autenticazione moderna.

### <a name="using-device-settings"></a>Uso delle impostazioni del dispositivo

1. Nel dispositivo Microsoft Team Rooms passare a **Altro** (**...**).
    
2. Selezionare **Impostazioni** e quindi immettere il nome utente e la password dell'amministratore del dispositivo.
3. Passare alla scheda **Account,** attivare Autenticazione **moderna** e quindi selezionare **Salva e chiudi.**

### <a name="using-the-xml-config-file"></a>Uso del file di configurazione XML

Nel file SkypeSettings.xml impostare l'elemento XML di autenticazione moderna su **True**, come indicato di seguito.

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Per applicare l'impostazione, vedere Gestire le impostazioni della console di [Microsoft Teams Rooms in remoto con un file di configurazione XML.](xml-config-file.md)

## <a name="prepare-your-environment-for-modern-authentication"></a>Preparare l'ambiente per l'autenticazione moderna

Prima di iniziare, assicurarsi di comprendere i modelli di identità da usare con Office 365 e Azure AD. Per altre informazioni, vedere Modelli di identità di [Office 365](/Office365/Enterprise/about-office-365-identity) e Azure Active Directory e Sincronizzazione ibrida di identità e directory per [Microsoft 365 o Office 365.](/Office365/Enterprise/plan-for-directory-synchronization)

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Abilitare l'autenticazione moderna in Microsoft 365 o Office 365

Per attivare l'autenticazione moderna per Exchange Online, vedere [Abilitare l'autenticazione moderna in Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) Se usi Skype for Business online, assicurati anche che l'autenticazione moderna sia attivata per Skype for Business online. Per altre informazioni, vedere [Skype for Business online: Abilitare il tenant per l'autenticazione moderna.](https://aka.ms/SkypeModernAuth)

È consigliabile non rimuovere i criteri di autenticazione di base per Exchange Online o disabilitare l'autenticazione di base per il tenant finché non si è verificato che i dispositivi Microsoft Teams Rooms possono accedere correttamente con Exchange Online, Teams e Skype for Business online.

Per altre informazioni sulla disabilitazione dell'autenticazione di base in Exchange Online, vedere [Disabilitare l'autenticazione di base in Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)

## <a name="hybrid-modern-authentication"></a>Autenticazione moderna ibrida

Per garantire la corretta autenticazione al server Exchange locale e/o al server Skype for Business, è necessario assicurarsi che l'account delle risorse usato con Microsoft Teams Rooms sia configurato per ottenere l'autorizzazione da Azure AD. 

I flussi di autenticazione di Teams Rooms variano a seconda della configurazione di autenticazione. Per i clienti che usano un dominio gestito, Teams Rooms usa [oAuth 2.0 Resource Owner Password Credentials](/azure/active-directory/develop/v2-oauth-ropc) con Azure Active Directory. Tuttavia, per i clienti che usano un dominio federato, viene usato [OAuth 2.0 SAML Bearer Assertion Flow.](/azure/active-directory/develop/v2-saml-bearer-assertion)

> [!NOTE]
> Il provider di identità potrebbe richiedere configurazioni o impostazioni specifiche per l'integrazione con Azure Active Directory o Office 365. Contattare il provider di identità per assistenza con la configurazione dell'autenticazione con Teams Rooms.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Prerequisiti specifici per Microsoft Teams Rooms

I prerequisiti per abilitare l'autenticazione moderna nella topologia ibrida sono trattati in Panoramica dell'autenticazione moderna ibrida e prerequisiti per usarla con i server Skype for Business ed [Exchange locali.](/office365/enterprise/hybrid-modern-auth-overview) Si applicano tutti i prerequisiti descritti nell'articolo.

Tuttavia, poiché Microsoft Teams Rooms usa l'autorizzazione delle [credenziali della password](https://tools.ietf.org/html/rfc6749#section-1.3.3) del proprietario delle risorse e le API REST sottostanti per l'autenticazione moderna, di seguito sono importanti differenze da tenere presenti specifiche delle chat room di Microsoft Teams.

- È necessario avere Exchange Server 2016 CU8 o versione successiva o Exchange Server 2019 CU1 o versione successiva.
- Devi avere Skype for Business Server 2015 CU5 o versione successiva oppure Skype for Business Server 2019 o versione successiva.
- L'autenticazione a più fattori non è supportata indipendentemente dalla topologia di cui si dispone.
- Microsoft Teams Rooms non supporta la mancata corrispondenza tra SIP e UPN. Per il funzionamento, è necessario creare un account Microsoft Teams Rooms con lo stesso UPN e SIP.
- Se si usa un provider di autenticazione di terze parti supportato da Azure AD, deve supportare un flusso di autenticazione attivo tramite WS-Trust.
- Non usare criteri di accesso condizionale a livello di dispositivo per un account di risorsa configurato con l'applicazione. In questo modo si verificano errori di accesso. È invece possibile registrare un dispositivo in Microsoft Intune e applicare criteri di conformità usando le indicazioni pubblicate in Gestione delle sale riunioni [di Teams con Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

### <a name="configure-exchange-server"></a>Configurare Exchange Server

Per abilitare l'autenticazione moderna ibrida in Exchange Server, vedere Come configurare Exchange Server locale per l'uso dell'autenticazione [moderna ibrida.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="configure-skype-for-business-server"></a>Configurare Skype for Business Server

Per abilitare l'autenticazione moderna ibrida con Skype for Business Server, vedere Come configurare Skype for Business locale per [l'uso dell'autenticazione moderna ibrida.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Rimuovere o disabilitare Skype for Business ed Exchange

Se la configurazione non consente l'autenticazione moderna ibrida o se è necessario rimuovere o disabilitare l'autenticazione moderna ibrida per Exchange o Skype for Business, vedere Rimozione o disabilitazione dell'autenticazione moderna ibrida da Skype for Business ed [Exchange.](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)

### <a name="azure-ad-conditional-access"></a>Accesso condizionale di Azure AD

È possibile configurare un account delle risorse usato con Microsoft Teams Rooms per l'accesso ip/basato sulla posizione. Per altre informazioni, vedere [Accesso condizionale: Bloccare l'accesso in base alla posizione.](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)

Non sono supportati altri criteri di accesso condizionale. Per altre informazioni sulla conformità dei dispositivi, vedere Gestione delle sale [riunioni di Teams con Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)