---
title: Autenticazione nelle sale di Microsoft Teams
ms.author: v-lanac
author: lanachin
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
description: Informazioni su come configurare l'autenticazione moderna per Microsoft teams rooms
ms.openlocfilehash: 83aff70e43fa578330fe48e814b4e7b216c7f90f
ms.sourcegitcommit: ded1e92348b6c18aa31f7f67e68ced3db525977d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2020
ms.locfileid: "46506181"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Autenticazione nelle sale di Microsoft Teams

Gestione account per i dispositivi Microsoft teams Rooms viene gestito a livello di applicazione. L'applicazione si connette a Microsoft teams, Skype for business e Exchange per ottenere risorse per l'account della sala per abilitare le esperienze di chiamata e riunione. Il dispositivo viene mantenuto indipendente dall'account per consentire funzionalità sempre disponibili, scenari di chiamata (per i dispositivi configurati con un piano per le chiamate) e meccanismi di blocco personalizzati implementati in questi dispositivi. Questo significa che l'autenticazione per questi dispositivi avviene in modo diverso rispetto ai dispositivi per gli utenti finali.  

È consigliabile usare l'autenticazione moderna per tutti i clienti che usano dispositivi Microsoft teams Rooms con Microsoft 365 o Office 365. Se si dispone di una distribuzione locale di Exchange Server o Skype for Business Server, configurare [l'autenticazione moderna ibrida](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) con Azure Active Directory (Azure ad) per consentire l'uso dell'autenticazione moderna.

L'autenticazione moderna è supportata in Microsoft teams Rooms versione 4.4.25.0 e versioni successive.

## <a name="modern-authentication"></a>Autenticazione moderna

Quando si usa l'autenticazione moderna con l'applicazione Microsoft teams rooms, viene usata la libreria di autenticazione di Active Directory (ADAL) per connettersi a Microsoft teams, Exchange e Skype for business. Un dispositivo Microsoft teams Rooms è un dispositivo condiviso ed esegue un riavvio notturno per garantirne il corretto funzionamento e ottenere aggiornamenti critici per il sistema operativo, il driver, il firmware o l'applicazione. Il meccanismo di autenticazione moderna usa il tipo di autorizzazione [credenziali password del proprietario della risorsa](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) in OAuth 2,0, che non richiede alcun intervento da parte dell'utente. Questa è una delle principali differenze tra la modalità di funzionamento dell'autenticazione moderna per gli account utente e gli account delle risorse usati dall'applicazione Microsoft teams rooms. Per questo motivo, gli account delle risorse di Microsoft teams Rooms non devono essere configurati in modo da usare l'autenticazione a più fattori, l'autenticazione tramite smart card o l'autenticazione basata su certificati client (tutti disponibili per gli utenti finali).

L'altra differenza fondamentale tra la modalità di funzionamento dell'autenticazione moderna nei dispositivi Microsoft teams Rooms e i dispositivi finali è che non è possibile usare un account di risorse per applicare criteri di accesso condizionale a livello di dispositivo in Azure Active Directory e Endpoint Manager come informazioni sul dispositivo non vengono passati quando si usa questo tipo di sovvenzione. È invece possibile registrare un dispositivo in Microsoft Endpoint Manager e applicare i criteri di conformità usando le indicazioni fornite nella [gestione delle sale riunioni di teams con Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230).

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Abilitare l'autenticazione moderna in un dispositivo Microsoft teams rooms

Per le sale di Microsoft teams per usare l'autenticazione moderna con Skype for business e Exchange, abilitare l'impostazione lato client per l'autenticazione moderna nel dispositivo Microsoft teams rooms. Questa operazione può essere eseguita nelle impostazioni del dispositivo o nel file di configurazione XML.

> [!NOTE]
> Prima di abilitare l'impostazione lato client per l'autenticazione moderna, verificare che l'ambiente sia configurato correttamente per l'uso dell'autenticazione moderna.

### <a name="using-device-settings"></a>Uso delle impostazioni del dispositivo

1. Nel dispositivo Microsoft Team Rooms passa a **altro** (**...**).
    
2. Selezionare **Impostazioni**e quindi immettere il nome utente e la password dell'amministratore del dispositivo.
3. Accedere alla scheda **account** , attivare **l'autenticazione moderna**e quindi selezionare **Salva ed esci**.

### <a name="using-the-xml-config-file"></a>Uso del file di configurazione XML

Nel file di SkypeSettings.xml impostare l'elemento XML di autenticazione moderno su **true**, come indicato di seguito.

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Per applicare l'impostazione, vedere [gestire le impostazioni della console Microsoft teams rooms in remoto con un file di configurazione XML](xml-config-file.md).

## <a name="prepare-your-environment-for-modern-authentication"></a>Preparare l'ambiente per l'autenticazione moderna

Prima di iniziare, verificare di aver compreso i modelli di identità da usare con Office 365 e Azure AD. Per altre informazioni, vedere [modelli di identità di Office 365 e Azure Active Directory](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) e [sincronizzazione di directory e identità ibrida per Microsoft 365 o Office 365](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization).

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Abilitare l'autenticazione moderna in Microsoft 365 o Office 365

Per attivare l'autenticazione moderna per Exchange Online, vedere [abilitare l'autenticazione moderna in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online). Se usi Skype for business online, devi anche assicurarti che l'autenticazione moderna sia attivata per Skype for business online. Per altre informazioni, vedere [Skype for business online: abilitare il tenant per l'autenticazione moderna](https://aka.ms/SkypeModernAuth).

È consigliabile non rimuovere i criteri di autenticazione di base per Exchange Online o disabilitare l'autenticazione di base per il tenant finché non si è convalidati che i dispositivi Microsoft teams Rooms possono accedere correttamente con Exchange Online, teams e Skype for business online.

Per altre informazioni sulla disabilitazione dell'autenticazione di base in Exchange Online, vedere [disabilitare l'autenticazione di base in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online).

## <a name="hybrid-modern-authentication"></a>Autenticazione moderna ibrida

Per garantire l'autenticazione corretta per il server di Exchange locale e/o Skype for Business Server, è necessario verificare che l'account delle risorse usato con Microsoft teams rooms sia configurato per ottenere l'autorizzazione da Azure AD. 

Flussi di autenticazione di teams Rooms variano a seconda della configurazione di autenticazione. Per i clienti che usano un dominio gestito, le sale di teams usano le [credenziali di password del proprietario della risorsa OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) con Azure Active Directory. Tuttavia, per i clienti che usano un dominio federato, viene usato il [flusso dell'asserzione del portatore SAML di OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/v2-saml-bearer-assertion) .

> [!NOTE]
> Il provider di identità può avere bisogno di configurazioni o impostazioni specifiche per l'integrazione con Azure Active Directory o Office 365. Contattare il provider di identità se serve aiuto per configurare l'autenticazione con le sale di teams.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Prerequisiti specifici di Microsoft teams rooms

I prerequisiti per abilitare l'autenticazione moderna nella topologia ibrida sono coperti da una [Panoramica di autenticazione moderna ibrida e prerequisiti per l'uso con i server Skype for business e Exchange locale](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview). Tutti i prerequisiti descritti nell'articolo si applicano.

Tuttavia, poiché le sale di Microsoft teams usano l'autorizzazione per le [credenziali di password del proprietario delle risorse](https://tools.ietf.org/html/rfc6749#section-1.3.3) e le API REST sottostanti per l'autenticazione moderna, le differenze seguenti sono importanti da tenere presenti nelle sale di Microsoft teams.

- È necessario avere Exchange Server 2016 CU8 o versione successiva oppure Exchange Server 2019 CU1 o versione successiva.
- È necessario avere Skype for Business Server 2015 CU5 o versione successiva oppure Skype for Business Server 2019 o versioni successive.
- L'AMF non è supportata indipendentemente dalla topologia.
- Se si usa un provider di autenticazione di terze parti supportato da Azure AD, deve supportare un flusso di autenticazione attiva tramite WS-Trust.
- Non usare criteri di accesso condizionale a livello di dispositivo per un account di risorse configurato con l'applicazione. In questo modo si verificheranno errori di accesso. È invece possibile registrare un dispositivo in Microsoft Intune e applicare i criteri di conformità usando le linee guida pubblicate nella [gestione delle sale riunioni di teams con Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230).

### <a name="configure-exchange-server"></a>Configurare Exchange Server

Per abilitare l'autenticazione moderna ibrida in Exchange Server, vedere [come configurare Exchange Server locale per l'uso dell'autenticazione moderna ibrida](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="configure-skype-for-business-server"></a>Configurare Skype for Business Server

Per abilitare l'autenticazione moderna ibrida con Skype for Business Server, vedere [come configurare Skype for business locale per l'uso dell'autenticazione moderna ibrida](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Rimuovere o disabilitare Skype for business e Exchange

Se la configurazione non è consentita per l'autenticazione moderna ibrida o è necessario rimuovere o disabilitare l'autenticazione moderna ibrida per Exchange o Skype for business, vedere [rimozione o disabilitazione dell'autenticazione moderna ibrida da Skype for business e Exchange](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha).

### <a name="azure-ad-conditional-access"></a>Accesso condizionale di Azure AD

Puoi configurare un account delle risorse usato con le sale di Microsoft teams per l'accesso basato su IP/posizione. Per altre informazioni, vedere [accesso condizionale: bloccare l'accesso in base alla posizione](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location).

Nessun altro criterio di accesso condizionale è supportato. Per altre informazioni sulla conformità dei dispositivi, vedere [gestione delle sale riunioni di teams con Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230).  
