---
title: Modelli di identità e autenticazione per Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 09/25/2020
ms.topic: reference
ms.service: msteams
ms.reviewer: anwara
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Informazioni sui diversi modelli di identità per Microsoft teams, ad esempio cloud-only e Hybrid. Scopri anche l'autenticazione a più fattori.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 40a06ce75c3ae7a4f85eb1c93064ba3d80c13fc0
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277116"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>Modelli di identità e autenticazione per Microsoft Teams

Microsoft teams supporta tutti i modelli di identità disponibili in Microsoft 365 e Office 365, che includono:

- **Solo cloud**: gli account utente vengono creati e gestiti in Microsoft 365 o Office 365 e archiviati in Azure Active Directory (Azure ad). Le credenziali di accesso dell'utente (nome account e password) vengono convalidate da Azure AD.

- **Ibrido**: gli account utente vengono in genere gestiti in una foresta di servizi di dominio Active Directory locale (ad DS). A seconda della configurazione, la convalida delle credenziali può essere eseguita da Azure AD, servizi di dominio Active Directory o da un provider di identità federata. Questo modello usa la sincronizzazione della directory da AD DS ad Azure AD con Azure AD Connect.

Per altre informazioni, Vedi [modelli di identità di Microsoft 365 e Azure ad](https://docs.microsoft.com/microsoft-365/enterprise/about-microsoft-365-identity).

## <a name="configurations"></a>Configurazioni

A seconda delle decisioni dell'organizzazione di cui si usa il modello e la configurazione di identità, la procedura di implementazione può variare.

Se non è già stato distribuito Microsoft 365 o Office 365 e un modello di identità, usare questa tabella. 

|Modello di identità |Elenco di controllo della distribuzione  |Altre informazioni  |
|---------|---------|---------|
|All     |<ol type="1"><li>Confrontare le opzioni di piano di Microsoft 365 e Office 365 e ottenere un abbonamento e un tenant.</li><li>Creare un'organizzazione di Microsoft 365 o Office 365 per il tenant.</li><li>Acquistare licenze Microsoft 365 o Office 365 per il tenant</li><li>Configurare i domini e gli account utente di amministratore.</li></ol>  |<ul><li>[Opzioni di piano di Office 365](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Confrontare i piani di Microsoft 365 per le aziende](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Acquistare o rimuovere licenze di abbonamento](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Aggiungere licenze a un abbonamento](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Configurare Microsoft 365 per le aziende](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Aggiungere un dominio con la configurazione guidata](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) è disponibile per assisterti.  |
|Identità cloud     |<ul><li>Creare account utente con l'interfaccia di amministrazione di Microsoft 365</li></ul> |<ul style="list-style-type:none"><li>[Aggiungere utenti e assegnare licenze](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|Identità ibrida     |<ol type="1"><li>Installare Azure AD Connect.</li><li>Configurare la sincronizzazione della directory.</li><li>Gestire utenti e gruppi con gli strumenti di servizi di dominio Active Directory.</li></ol> |<ul style="list-style-type:none"><li>[Configurare la sincronizzazione della directory](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|Identità ibrida con autenticazione federata    |<ol type="1"><li>Installare e configurare un provider di identità federata, ad esempio ADFS.</li><li>Installare Azure AD Connect e configurare la sincronizzazione della directory e l'autenticazione federata.</li><li>Gestire utenti e gruppi con gli strumenti di servizi di dominio Active Directory.</li></ol> |<ul><li>[Pianificare la distribuzione di ADFS](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[Elenco di controllo: distribuire la farm server federativo](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Configurare l'accesso Extranet per ADFS](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[Configurare un trust tra ADFS ed Azure AD](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[Verificare e gestire Single Sign-on con ADFS](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Configurare la sincronizzazione della directory](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>Autenticazione a più fattori

Le password sono il metodo più comune per l'autenticazione per l'accesso a un computer o a un servizio online, ma sono anche le più vulnerabili. Gli utenti possono scegliere password semplici e usare le stesse password per accedere a più accessi a computer e servizi diversi. 

Per specificare un livello aggiuntivo di sicurezza per gli accessi, usare l'autenticazione a più fattori (AMF), che richiede sia una password che un altro metodo di verifica, ad esempio:

- Messaggio di testo inviato a un telefono che richiede all'utente di digitare un codice di verifica.
- Una telefonata.
- App Smart Phone Microsoft Authenticator.
- Altri metodi disponibili con l'identità ibrida e l'autenticazione federata.

L'AMF è supportata con qualsiasi piano Microsoft 365 o Office 365 che include Microsoft teams. È altamente raccomandato che almeno tu abbia bisogno di AMF per gli account a cui sono [assegnati ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide), ad esempio amministratore del servizio teams.

Dovresti anche distribuire l'AMF agli utenti. Una volta registrati gli utenti per l'AMF, la prossima volta che accedono verrà visualizzato un messaggio che chiede di configurare il metodo di verifica aggiuntivo. 

Per altre informazioni, vedere [autenticazione a più fattori per Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365).
