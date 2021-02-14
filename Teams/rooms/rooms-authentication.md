---
title: Autenticazione nelle sale di Microsoft Teams
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
description: Informazioni su come configurare l'autenticazione moderna per le sale di Microsoft Teams
ms.openlocfilehash: 41a65743e5da851dd8e0197e9382deaf696cd9ec
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662581"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Autenticazione nelle sale di Microsoft Teams

La gestione degli account per i dispositivi di Sale di Microsoft Teams viene gestita a livello di applicazione. L'applicazione si connette a Microsoft Teams, Skype for Business ed Exchange per ottenere risorse per l'account della sala e consentire le chiamate e le riunioni. Il dispositivo viene mantenuto agnostico per consentire funzionalità sempre in funzione, scenari di chiamata (per i dispositivi configurati con un Piano per chiamate) e meccanismi di blocco personalizzati implementati su questi dispositivi. Questo significa che l'autenticazione per questi dispositivi avviene in modo diverso rispetto ai dispositivi degli utenti finali.  

L'autenticazione moderna è consigliata per tutti i clienti che usano dispositivi Microsoft Teams Room con Microsoft 365 o Office 365. Se si ha una distribuzione locale di Exchange Server o [](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) Skype for Business Server, configurare l'autenticazione moderna ibrida con Azure Active Directory (Azure AD) per abilitare l'uso dell'autenticazione moderna.

L'autenticazione moderna è supportata in Microsoft Teams Rooms versione 4.4.25.0 e successive.

## <a name="modern-authentication"></a>Autenticazione moderna

Quando si usa l'autenticazione moderna con l'applicazione Sale di Microsoft Teams, viene usato Active Directory Authentication Library (ADAL) per connettersi a Microsoft Teams, Exchange e Skype for Business. Un dispositivo Microsoft Teams Rooms è un dispositivo condiviso che esegue un riavvio sereno per garantire un funzionamento fluido e per ottenere aggiornamenti critici del sistema operativo, del driver, del firmware o delle applicazioni. Il meccanismo di autenticazione moderno usa il tipo di autorizzazione di autorizzazione per le [credenziali](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) del proprietario della risorsa in OAuth 2.0, che non richiede l'intervento dell'utente. Questa è una delle principali differenze tra il funzionamento dell'autenticazione moderna per gli account utente e gli account delle risorse usati dall'applicazione Sale di Microsoft Teams. Per questo, gli account delle risorse di Microsoft Teams Room non devono essere configurati per l'uso dell'autenticazione a più fattori (MFA), dell'autenticazione con smart card o dell'autenticazione basata su certificato client (tutti disponibili per gli utenti finali).

L'altra differenza fondamentale tra il funzionamento dell'autenticazione moderna nei dispositivi Room di Microsoft Teams e nei dispositivi degli utenti finali è che non è possibile usare un account delle risorse per applicare criteri di accesso condizionale a livello di dispositivo in Azure Active Directory ed Endpoint Manager perché le informazioni sul dispositivo non vengono passate quando si usa questo tipo di concessione. È invece possibile registrare un dispositivo in Microsoft Endpoint Manager e applicare criteri di conformità usando le indicazioni fornite nella gestione delle sale riunioni di [Teams con Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Abilitare l'autenticazione moderna in un dispositivo Microsoft Teams Rooms

Per usare l'autenticazione moderna nelle sale di Microsoft Teams con Skype for Business ed Exchange, abilitare l'impostazione lato client per l'autenticazione moderna nel dispositivo Sale di Microsoft Teams. A questo scopo, usare le impostazioni del dispositivo o il file di configurazione XML.

> [!NOTE]
> Prima di abilitare l'impostazione lato client per l'autenticazione moderna, verificare che l'ambiente sia configurato correttamente per l'uso dell'autenticazione moderna.

### <a name="using-device-settings"></a>Uso delle impostazioni del dispositivo

1. Nel dispositivo Microsoft Team Rooms passare ad **Altro** (**...**).
    
2. Selezionare **Impostazioni,** quindi immettere il nome utente e la password di amministratore del dispositivo.
3. Passare alla scheda **Account,** attivare **l'autenticazione** moderna e quindi selezionare **Salva e esci.**

### <a name="using-the-xml-config-file"></a>Uso del file di configurazione XML

Nel file SkypeSettings.xml, impostare l'elemento XML di autenticazione moderna su **True,** come indicato di seguito.

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Per applicare l'impostazione, vedere Gestire le impostazioni della console di Microsoft Teams Room in [remoto con un file di configurazione XML.](xml-config-file.md)

## <a name="prepare-your-environment-for-modern-authentication"></a>Preparare l'ambiente per l'autenticazione moderna

Prima di iniziare, assicurarsi di conoscere i modelli di identità da usare con Office 365 e Azure AD. Per altre informazioni, vedere i modelli di identità di [Office 365](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) e Azure Active Directory e la sincronizzazione ibrida di identità e directory per [Microsoft 365 o Office 365.](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization)

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Abilitare l'autenticazione moderna in Microsoft 365 o Office 365

Per attivare l'autenticazione moderna per Exchange Online, vedere [Abilitare l'autenticazione moderna in Exchange Online.](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) Se si usa Skype for Business online, assicurarsi anche che l'autenticazione moderna sia attivata per Skype for Business online. Per ulteriori informazioni, consulta [Skype for Business online: Abilitare il tenant per l'autenticazione moderna.](https://aka.ms/SkypeModernAuth)

È consigliabile non rimuovere i criteri di autenticazione di base per Exchange Online o disabilitare l'autenticazione di base per il tenant finché non si è verificato che i dispositivi Microsoft Teams Room possano accedere con Exchange Online, Teams e Skype for Business online.

Per altre informazioni sulla disabilitazione dell'autenticazione di base in Exchange Online, vedere [Disabilitare l'autenticazione di base in Exchange Online.](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)

## <a name="hybrid-modern-authentication"></a>Autenticazione moderna ibrida

Per assicurare la corretta autenticazione al server Exchange locale e/o a Skype for Business Server, è necessario assicurarsi che l'account delle risorse usato con Sale di Microsoft Teams sia configurato per ottenere l'autorizzazione da Azure AD. 

I flussi di autenticazione delle chat room di Teams variano a seconda della configurazione di autenticazione. Per i clienti che usano un dominio gestito, Teams Room usa le credenziali password del proprietario delle risorse [OAuth 2.0](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) con Azure Active Directory. Tuttavia, per i clienti che usano un dominio federato, viene usato il flusso di asserzione saml [bearer OAuth 2.0.](https://docs.microsoft.com/azure/active-directory/develop/v2-saml-bearer-assertion)

> [!NOTE]
> Il provider di identità potrebbe richiedere configurazioni o impostazioni specifiche per l'integrazione con Azure Active Directory o Office 365. Contattare il provider di identità per assistenza con la configurazione dell'autenticazione con Teams Room.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Prerequisiti specifici delle sale di Microsoft Teams

I prerequisiti per abilitare l'autenticazione moderna nella topologia ibrida sono coperti nella panoramica e nei prerequisiti per l'uso con i server locali [Skype for Business ed Exchange.](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) Sono applicabili tutti i prerequisiti descritti nell'articolo.

Tuttavia, poiché Microsoft Teams Room usa l'autorizzazione [delle password](https://tools.ietf.org/html/rfc6749#section-1.3.3) del proprietario delle risorse e le API REST sottostanti per l'autenticazione moderna, di seguito sono importanti differenze da tenere presenti specifiche per Le sale di Microsoft Teams.

- È necessario avere Exchange Server CU8 2016 o versione successiva oppure Exchange Server 2019 CU1 o versione successiva.
- È necessario Skype for Business Server 2015 CU5 o versione successiva oppure Skype for Business Server 2019 o versione successiva.
- L'autenticazione a più fattori non è supportata indipendentemente dalla topologia di cui si dispone.
- La funzionalità Sale di Microsoft Teams non supporta la mancata corrispondenza di SIP e UPN. Per il funzionamento è necessario creare un account Microsoft Teams Rooms con gli stessi UPN e SIP.
- Se si usa un provider di autenticazione di terze parti supportato da Azure AD, deve supportare un flusso di autenticazione attivo tramite WS-Trust.
- Non usare criteri di accesso condizionale a livello di dispositivo per un account delle risorse configurato con l'applicazione. In questo modo si verificano errori di accesso. È invece possibile registrare un dispositivo in Microsoft Intune e applicare criteri di conformità usando le indicazioni pubblicate nella gestione delle sale riunioni [di Teams con Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

### <a name="configure-exchange-server"></a>Configurare Exchange Server

Per abilitare l'autenticazione moderna ibrida in Exchange Server, vedere come configurare Exchange Server locale per l'uso [dell'autenticazione moderna ibrida.](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="configure-skype-for-business-server"></a>Configurare Skype for Business Server

Per abilitare l'autenticazione moderna ibrida con Skype for Business Server, vedere Come configurare Skype for Business locale per l'uso [dell'autenticazione moderna ibrida.](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Rimuovere o disabilitare Skype for Business ed Exchange

Se la configurazione non consente l'autenticazione moderna ibrida o se è necessario rimuovere o disabilitare l'autenticazione moderna ibrida per Exchange o Skype for Business, vedere Come rimuovere o disabilitare l'autenticazione moderna ibrida da Skype for Business ed [Exchange.](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)

### <a name="azure-ad-conditional-access"></a>Accesso condizionale di Azure AD

È possibile configurare un account delle risorse usato con Microsoft Teams Room per l'accesso basato sulla posizione o SU IP. Per altre informazioni, vedere [Accesso condizionale: bloccare l'accesso in base alla posizione.](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location)

Non sono supportati altri criteri di accesso condizionale. Per altre informazioni sulla conformità dei dispositivi, vedere Gestione delle sale [riunioni di Teams con Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)  
