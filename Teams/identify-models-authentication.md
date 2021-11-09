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
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Informazioni sui diversi modelli di identità per Microsoft Teams, ad esempio solo cloud e ibridi. Informazioni anche sull'autenticazione a più fattori.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c12e7242241c8c6d7ac03bc3c66804198acd746e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836064"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>Modelli di identità e autenticazione per Microsoft Teams

Microsoft Teams supporta tutti i modelli di identità disponibili con Microsoft 365 e Office 365, che includono:

- **Solo cloud:** gli account utente vengono creati e gestiti in Microsoft 365 o Office 365 e archiviati in Azure Active Directory (Azure AD). Le credenziali di accesso dell'utente (nome account e password) vengono convalidate Azure AD.

- **Ibrido:** gli account utente vengono in genere gestiti in una foresta di Servizi di dominio Active Directory locale. A seconda della configurazione, la convalida delle credenziali può essere eseguita da un Azure AD, da Servizi di dominio Active Directory o da un provider di identità federate. Questo modello usa la sincronizzazione della directory da Servizi di dominio Active Directory Azure AD con Azure AD Connessione.

Per altre informazioni, vedere modelli [di Microsoft 365 e Azure AD](/microsoft-365/enterprise/about-microsoft-365-identity).

## <a name="configurations"></a>Configurazioni

A seconda delle decisioni dell'organizzazione relative al modello di identità e alla configurazione in uso, i passaggi di implementazione possono variare.

Se non è ancora stato distribuito Microsoft 365 o Office 365 un modello di identità, usare questa tabella. 

|Modello di identità |Elenco di controllo per la distribuzione  |Informazioni aggiuntive  |
|---------|---------|---------|
|All     |<ol type="1"><li>Confrontare Microsoft 365 e Office 365 piano e ottenere un abbonamento e un tenant.</li><li>Creare un'Microsoft 365 o Office 365 per il tenant.</li><li>Acquistare Microsoft 365 o Office 365 licenze per il tenant</li><li>Configurare domini e account utente di amministratore.</li></ol>  |<ul><li>[Office 365 piano](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</li><li>[Confronto tra Microsoft 365 per le aziende](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Acquistare o rimuovere licenze di abbonamento](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Aggiungere licenze a un abbonamento](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Configurare Microsoft 365 per le aziende](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Aggiungere un dominio con la configurazione guidata](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) è disponibile per aiutarti.  |
|Identità cloud     |<ul><li>Creare account utente con il interfaccia di amministrazione di Microsoft 365</li></ul> |<ul><li>[Aggiungere utenti e assegnare licenze](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|Identità ibrida     |<ol type="1"><li>Installare Azure AD Connessione.</li><li>Configurare la sincronizzazione della directory.</li><li>Gestire utenti e gruppi con gli strumenti di Servizi di dominio Active Directory.</li></ol> |<ul><li>[Configurare la sincronizzazione della directory](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|Identità ibrida con autenticazione federata    |<ol type="1"><li>Installare e configurare un provider di identità federate, ad esempio AD FS.</li><li>Installare Azure AD Connessione e configurare la sincronizzazione della directory e l'autenticazione federata.</li><li>Gestire utenti e gruppi con gli strumenti di Servizi di dominio Active Directory.</li></ol> |<ul><li>[Pianificare la distribuzione di AD FS](/previous-versions/azure/azure-services/dn151324(v=azure.100))</li><li>[Elenco di controllo: Distribuire la server farm federativa](/previous-versions/azure/azure-services/dn528856(v=azure.100))</li><li>[Configurare l'accesso Extranet per AD FS](/previous-versions/azure/azure-services/dn528859(v=azure.100))</li><li>[Configurare un trust tra ADFS e Azure AD](/previous-versions/azure/azure-services/jj205461(v=azure.100))</li><li>[Verificare e gestire Single Sign-On con ADFS](/previous-versions/azure/azure-services/jj151809(v=azure.100))</li><li>[Configurare la sincronizzazione della directory](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>Autenticazione a più fattori

Le password sono il metodo di autenticazione più comune per l'accesso a un computer o a un servizio online, ma sono anche le più vulnerabili. Gli utenti possono scegliere password semplici e usare le stesse password per più account di accesso a computer e servizi diversi. 

Per fornire un ulteriore livello di sicurezza per gli account di accesso, usare l'autenticazione a più fattori(MFA), che richiede sia una password che un metodo di verifica aggiuntivo, ad esempio:

- Un SMS inviato a un telefono che richiede all'utente di digitare un codice di verifica.
- Una telefonata.
- L Microsoft Authenticator per smartphone.
- Altri metodi disponibili con l'identità ibrida e l'autenticazione federata.

MFA è supportato con qualsiasi piano Microsoft 365 o Office 365 che include Microsoft Teams. È consigliabile richiedere almeno l'autenticazione a più fattori per gli account a cui sono assegnati ruoli di [amministratore,](/microsoft-365/admin/add-users/about-admin-roles)ad esempio un amministratore Teams servizio.

È consigliabile anche implementare MFA agli utenti. Dopo aver registrato gli utenti per L'autenticazione a più fattori, al successivo accesso, gli utenti riceveranno un messaggio che chiede di configurare il metodo di verifica aggiuntivo. 

Per altre informazioni, vedere [Autenticazione a più fattori per Microsoft 365](/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365).