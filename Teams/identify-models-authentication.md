---
title: Modelli di identità e autenticazione
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Informazioni sui diversi modelli di identità in Microsoft teams, ad esempio cloud, Synchronized e federate. Scopri anche l'autenticazione a più fattori.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a58dcdae704be7ccdaefe1e2bca3b4978f4a10f9
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139295"
---
<a name="identity-models-and-authentication-in-microsoft-teams"></a>Modelli di identità e autenticazione in Microsoft Teams
==========================================

Microsoft teams supporta tutti i modelli di identità disponibili in Office 365. I modelli di identità supportati includono:

-   **Identità cloud**: in questo modello un utente viene creato e gestito in Office 365 e archiviato in Azure Active Directory e la password viene verificata da Azure Active Directory.

-   **Identità sincronizzata**: in questo modello l'identità utente viene gestita in un server locale e gli hash di account e password vengono sincronizzati con il cloud. L'utente immette la stessa password locale come nel cloud e in accesso la password viene verificata da Azure Active Directory. Questo modello usa lo strumento Microsoft Azure Active Directory Connect.

-   **Identità federata**: questo modello richiede un'identità sincronizzata con la password dell'utente viene verificata dal provider di identità locale. Con questo modello, l'hash della password non deve essere sincronizzato con Azure AD e Active Directory Federation Services (ADFS) o un provider di identità di terze parti viene usato per autenticare gli utenti in Active Directory locale.

<a name="configurations"></a>Configurazioni
--------------

A seconda delle decisioni dell'organizzazione relative al modello di identità da implementare e usare, i requisiti di implementazione possono variare. Vedere la tabella requisiti seguente per verificare che la distribuzione soddisfi questi prerequisiti. Se si è già distribuito Office 365 e si è già implementato il metodo di autenticazione e identità, è possibile che questi passaggi non vengano ignorati.


|Modello di identità |Elenco di controllo della distribuzione  |Ulteriori informazioni  |
|---------|---------|---------|
|All     |<ol type="1"><li>Confrontare le opzioni di piano di Office 365 e ottenere un abbonamento</li><li>Creare un tenant di Office 365</li><li>Assegnare licenze di Office 365 al tenant</li><li>Configurare i domini e gli utenti amministratori</li><li>Seguire le istruzioni specifiche del modello di identità</li></ol>          |<ul style="list-style-type:none"><li>[Opzioni di piano di Office 365](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Confrontare i piani aziendali di Office 365](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Acquistare licenze per l'abbonamento a Office 365 for business](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Aggiungere licenze a un abbonamento](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Configurare Office 365 per le aziende](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Aggiungere utenti e domini con la configurazione guidata](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li><li>Nota: se hai bisogno di assistenza, [il team Microsoft FastTrack per Office 365](https://go.microsoft.com/fwlink/?linkid=854618) è disponibile per assisterti.</li></ul>          |
|Identità cloud     |<ol type="1"><li>Creare utenti con il portale di amministrazione di Office 365</li></ol>           |<ul style="list-style-type:none"><li>[Aggiungere utenti singolarmente o in blocco a Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul>         |
|Identità sincronizzata     |<ol type="1"><li>Installare Azure AD Connect</li><li>Configurare la sincronizzazione della directory</li><li>Creare utenti con strumenti di gestione Active Directory locali</li></ol>         |<ul style="list-style-type:none"><li>[Configurare la sincronizzazione della directory per Office 365](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>Nota: gli hash delle password devono essere sincronizzati per Office 365 per eseguire l'autenticazione.</li></ul>         |
|Identità federata    |<ol type="1"><li>Installare Azure AD Connect</li><li>Configurare la sincronizzazione della directory</li><li>Installare e configurare un provider di identità federata (consigliato ADFS)</li><li>Creare utenti con strumenti di gestione Active Directory locali</li></ol>           |<ul style="list-style-type:none"><li>[Configurare la sincronizzazione della directory per Office 365](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>[Pianificare la distribuzione di ADFS](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[Elenco di controllo: distribuire la farm server federativo](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Configurare l'accesso Extranet per ADFS](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[Configurare un trust tra ADFS ed Azure AD](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[Verificare e gestire Single Sign-on con ADFS](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Elenco compatibilità federativo AD Azure AD](https://go.microsoft.com/fwlink/?linkid=854625)</li><li>Nota: gli hash delle password non devono essere sincronizzati con Azure Active Directory.</li></ul>         |

Per ulteriori informazioni, vedere [scelta di un modello di accesso per office 365](https://go.microsoft.com/fwlink/?linkid=854626) e informazioni sulle guide di [Office 365 Identity e Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) .

<a name="multi-factor-authentication"></a>Autenticazione a più fattori
----------------------------

I piani di Office 365 supportano l'autenticazione a più fattori (AMF) che aumenta la sicurezza degli accessi degli utenti ai servizi di Office 365. Con l'AMF per Office 365, gli utenti sono tenuti a riconoscere una telefonata, un SMS o una notifica per l'app nello smartphone dopo aver inserito correttamente la password. Solo dopo aver soddisfatto il secondo fattore di autenticazione, è possibile accedere a un utente.

L'autenticazione a più fattori è supportata con qualsiasi piano di Office 365 che include Microsoft teams. I piani di abbonamento a Office 365 che includono Microsoft teams sono discussi più avanti nella sezione Licensing seguente.

Una volta registrati gli utenti per l'AMF, la volta successiva che un utente accede verrà visualizzato un messaggio che chiede di configurare il secondo fattore di autenticazione. I metodi di autenticazione supportati sono:


|Tipo di tenant  |Opzioni di secondo fattore AMF disponibili  |Note  |
|---------|---------|---------|
|**Solo cloud**     |AMF per Office 365 <ul><li>Chiamata telefonica</li><li>Messaggio di testo</li><li>Notifica di app per dispositivi mobili</li><li>Codice di verifica dell'app per dispositivi mobili</li></ul>        |[Pianificare l'autenticazione a più fattori per le distribuzioni di Office 365](https://support.office.com/article/Plan-for-multi-factor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)         |
|**Configurazione ibrida (modello di identità sincronizzato o federato)**     |<ul><li>AMF per Office 365</li><li>Modulo AMF di Azure (ADFS Integrated)</li><li>Smart Card fisica o virtuale (ADFS Integrated)</li></ul>         |Nota: sono disponibili altre soluzioni AMF con i [documenti di compatibilità dei provider di Azure ad Identity](https://www.microsoft.com/download/details.aspx?id=56843)         |
