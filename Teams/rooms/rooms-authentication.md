---
title: Autenticazione in Microsoft Teams Rooms
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-collaboration
description: Informazioni su come configurare l'autenticazione moderna per Microsoft Teams Rooms
ms.openlocfilehash: de1487cce0c8a79d2a6c672f5cb729e247966c50
ms.sourcegitcommit: 0967f725aad0a7b9c430b2e30a37ea333007558a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "65106301"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Autenticazione in Microsoft Teams Rooms

La gestione degli account per Microsoft Teams Rooms viene gestita a livello di applicazione. L'applicazione si connette a Microsoft Teams, Skype for Business e Exchange per ottenere risorse per l'account delle risorse per abilitare le esperienze di chiamata e riunione. Teams Rooms usa un account di risorse dedicato per consentire funzionalità sempre attivate, scenari di chiamata (per i dispositivi configurati con un piano di chiamata) e meccanismi di blocco personalizzati. Ciò significa che l'autenticazione per Teams Rooms avviene in modo diverso rispetto ai dispositivi degli utenti finali.  

L'autenticazione moderna è consigliata a tutti i clienti che usano Microsoft Teams Rooms con Microsoft 365 o Office 365. Se si dispone di una distribuzione locale del server Exchange o del server Skype for Business, configurare [l'autenticazione moderna ibrida](/office365/enterprise/hybrid-modern-auth-overview) con Azure Active Directory (Azure AD) per abilitare l'uso dell'autenticazione moderna.

L'autenticazione moderna è supportata in Microsoft Teams Rooms versione 4.4.25.0 e successive.

## <a name="modern-authentication"></a>Autenticazione moderna

Quando si usa l'autenticazione moderna con l'applicazione Microsoft Teams Rooms, active directory authentication library (ADAL) viene usato per connettersi a Microsoft Teams, Exchange e Skype for Business. Il meccanismo di autenticazione moderna usa il tipo di autorizzazione per [le credenziali della password del proprietario della risorsa](/azure/active-directory/develop/v2-oauth-ropc) in OAuth 2.0, che non richiede alcun intervento da parte dell'utente. Questa è una delle principali differenze tra il funzionamento dell'autenticazione moderna per gli account utente e gli account delle risorse usati da Microsoft Teams Rooms. Per questo motivo, Microsoft Teams Rooms account delle risorse non devono essere configurati per l'uso dell'autenticazione a più fattori (MFA, Multi-Factor Authentication), dell'autenticazione con smart card o dell'autenticazione basata su certificato client (tutti disponibili per gli utenti finali).

L'altra differenza fondamentale tra il funzionamento dell'autenticazione moderna nei dispositivi Microsoft Teams Rooms e degli utenti finali è che non è possibile usare un account delle risorse per applicare criteri di accesso condizionale a livello di dispositivo in Azure Active Directory e Endpoint Manager come le informazioni sul dispositivo non vengono passate quando si usa questo tipo di concessione. È invece possibile registrare un dispositivo in Microsoft Endpoint Manager e applicare i criteri di conformità. Per altre informazioni, vedere [Accesso condizionale e conformità Intune per Microsoft Teams Rooms](conditional-access-and-compliance-for-devices.md).

## <a name="enable-modern-authentication-on-microsoft-teams-rooms"></a>Abilitare l'autenticazione moderna in Microsoft Teams Rooms

Per Microsoft Teams Rooms usare l'autenticazione moderna con Skype for Business e Exchange, abilitare l'impostazione lato client per l'autenticazione moderna in Microsoft Teams Rooms. È possibile eseguire questa operazione nelle impostazioni del dispositivo o nel file di configurazione XML.

> [!NOTE]
> Prima di abilitare l'impostazione lato client per l'autenticazione moderna, verificare che l'ambiente sia configurato correttamente per l'uso dell'autenticazione moderna.

### <a name="using-device-settings"></a>Uso delle impostazioni del dispositivo

1. In Microsoft Teams Rooms passare ad **Altro** (**...**).
    
2. Seleziona **Impostazioni** e quindi immetti il nome utente e la password dell'amministratore del dispositivo.
3. Vai alla scheda **Account** , attiva **Autenticazione moderna** e quindi seleziona **Salva e chiudi**.

### <a name="using-the-xml-config-file"></a>Utilizzo del file di configurazione XML

Nel file di SkypeSettings.xml impostare l'elemento XML di autenticazione moderna su **True**, come indicato di seguito.

```XML
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Per applicare l'impostazione, vedere [Gestire in remoto le impostazioni di una console Microsoft Teams Rooms con un file di configurazione XML](xml-config-file.md).

## <a name="prepare-your-environment-for-modern-authentication"></a>Preparare l'ambiente per l'autenticazione moderna

Prima di iniziare, assicurarsi di comprendere i modelli di identità da usare con Office 365 e Azure AD. Per altre informazioni[, vedere modelli di identità Office 365 e Azure Active Directory](/Office365/Enterprise/about-office-365-identity) e [Sincronizzazione ibrida delle identità e della directory per Microsoft 365 o Office 365](/Office365/Enterprise/plan-for-directory-synchronization).

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Abilitare l'autenticazione moderna in Microsoft 365 o Office 365

Per attivare l'autenticazione moderna per Exchange Online, vedere [Abilitare l'autenticazione moderna in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

È consigliabile non rimuovere i criteri di autenticazione di base per Exchange Online o disabilitare l'autenticazione di base per il tenant finché non si convalida che Microsoft Teams Rooms dispositivi possano accedere correttamente con Exchange Online e Teams.

Per altre informazioni sulla disabilitazione dell'autenticazione di base in Exchange Online, vedere [Disabilitare l'autenticazione di base in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online).

## <a name="hybrid-modern-authentication"></a>Autenticazione moderna ibrida

Per eseguire correttamente l'autenticazione nel server Exchange locale e/o nel server Skype for Business, è necessario verificare che l'account delle risorse usato con Microsoft Teams Rooms sia configurato per ottenere l'autorizzazione da Azure AD.

Teams Rooms flussi di autenticazione variano a seconda della configurazione dell'autenticazione. Per i clienti che usano un dominio gestito, Teams Rooms usa [le credenziali della password del proprietario della risorsa di OAuth 2.0](/azure/active-directory/develop/v2-oauth-ropc) con Azure Active Directory. Tuttavia, per i clienti che usano un dominio federato, viene usato [OAuth 2.0 SAML Bearer Assertion Flow](/azure/active-directory/develop/v2-saml-bearer-assertion).

> [!NOTE]
> Il provider di identità potrebbe aver bisogno di configurazioni o impostazioni specifiche per l'integrazione con Azure Active Directory o Office 365. Contattare il provider di identità per assistenza nella configurazione dell'autenticazione con Teams Rooms.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Prerequisiti specifici per Microsoft Teams Rooms

I prerequisiti per abilitare l'autenticazione moderna nella topologia ibrida sono descritti nella [panoramica dell'autenticazione moderna ibrida e nei prerequisiti per usarla con i server Skype for Business e Exchange locali](/office365/enterprise/hybrid-modern-auth-overview). Si applicano tutti i prerequisiti discussi nell'articolo.

Tuttavia, poiché Microsoft Teams Rooms usa l'autorizzazione per [le credenziali della password del proprietario delle risorse](https://tools.ietf.org/html/rfc6749#section-1.3.3) e le API REST sottostanti per l'autenticazione moderna, di seguito sono riportate importanti differenze da tenere presenti, specifiche per Microsoft Teams Rooms.

- È necessario disporre di Exchange Server CU8 2016 o versione successiva oppure di Exchange Server 2019 CU1 o versione successiva.
- È necessario disporre di Skype for Business Server CU5 2015 o versione successiva oppure Skype for Business Server 2019 o versione successiva.
- L'autenticazione a più fattori non è supportata indipendentemente dalla topologia in uso.
- Microsoft Teams Rooms non supporta la mancata corrispondenza con SIP e UPN. Per il funzionamento, è necessario creare un account di Microsoft Teams Rooms con lo stesso UPN e SIP.
- Se usi un provider di autenticazione di terze parti supportato da Azure AD, deve supportare un flusso di autenticazione attivo tramite WS-Trust.
- Non usare criteri di accesso condizionale a livello di dispositivo per un account di risorse configurato con l'applicazione. In questo modo si produranno errori di accesso. Registrare invece un dispositivo in Microsoft Intune e applicare i criteri di conformità. Per altre informazioni, vedere [Accesso condizionale e conformità Intune per Microsoft Teams Rooms](conditional-access-and-compliance-for-devices.md).

### <a name="configure-exchange-server"></a>Configurare Exchange Server

Per abilitare l'autenticazione moderna ibrida in Exchange Server, vedere [Come configurare Exchange Server locale per l'uso dell'autenticazione moderna ibrida](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="configure-skype-for-business-server"></a>Configurare Skype for Business Server

Per abilitare l'autenticazione moderna ibrida con Skype for Business Server, vedere [Come configurare Skype for Business locale per l'uso dell'autenticazione moderna ibrida](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Rimuovere o disabilitare Skype for Business e Exchange

Se la configurazione non consente l'autenticazione moderna ibrida o se è necessario rimuovere o disabilitare l'autenticazione moderna ibrida per Exchange o Skype for Business, vedere [Rimozione o disabilitazione dell'autenticazione moderna ibrida da Skype for Business e Exchange](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha).

### <a name="azure-ad-conditional-access"></a>Azure AD accesso condizionale

È possibile configurare un account delle risorse usato con Microsoft Teams Rooms per l'accesso basato su IP o sulla posizione. Per altre informazioni, vedere [Accesso condizionale: bloccare l'accesso in base alla posizione](/azure/active-directory/conditional-access/howto-conditional-access-policy-location).

Non sono supportati altri criteri di accesso condizionale. Per altre informazioni sulla conformità dei dispositivi, vedere [Accesso condizionale supportato e criteri di conformità Intune per Microsoft Teams Rooms](supported-ca-and-compliance-policies.md).
