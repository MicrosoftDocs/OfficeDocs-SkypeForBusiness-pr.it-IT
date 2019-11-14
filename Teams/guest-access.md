---
title: Accesso guest in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: L'accesso guest in Microsoft Teams consente ai team dell'organizzazione di collaborare con persone esterne all'organizzazione concedendo loro l'accesso a team e canali.
localization_priority: Priority
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad8b75e244efa0d28709d6c5ff225f1e6676200a
ms.sourcegitcommit: ed7439d03e37c9c0184daf5215a68c5492932a83
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "38290856"
---
<a name="guest-access-in-microsoft-teams"></a>Accesso guest in Microsoft Teams
======================================

L'accesso guest consente di aggiungere singoli utenti esterni all'organizzazione ai team e ai canali in Microsoft Teams. 

Per confrontare l'accesso esterno (federazione) con l'accesso guest e decidere quale usare, leggere [Comunicare con utenti di altre organizzazioni in Teams](communicate-with-users-from-other-organizations.md).

Se si vuole attivare l'accesso guest nell'organizzazione, iniziare con l'[Elenco di controllo dell’accesso guest](guest-access-checklist.md).

## <a name="guest-access-overview"></a>Panoramica dell'accesso guest

L'accesso guest consente ai team dell'organizzazione di collaborare con persone esterne all'organizzazione concedendo loro l'accesso a team esistenti e canali in Teams. Chiunque abbia un account di posta elettronica aziendale o personale, come Outlook, Gmail o altri, può partecipare come guest in Teams e avere accesso completo a chat, riunioni e file del team. L'amministratore di Teams controlla le funzionalità che gli utenti guest possono (e non possono) usare in Teams, vedere [Gestire l'accesso guest](manage-guests.md) per altre informazioni.

L'accesso guest è un'impostazione a livello di organizzazione in Teams ed è disattivato per impostazione predefinita. L'accesso guest è soggetto ai limiti di servizio di Azure AD e Office 365.


> [!IMPORTANT]
> Gli utenti guest sono inclusi nelle impostazioni a livello di organizzazione di Teams per la modalità di aggiornamento della coesistenza. Questa impostazione non può essere modificata.

## <a name="licensing-for-guest-access"></a>Licenze per l'accesso guest

L'accesso guest è incluso in tutti gli abbonamenti di Office 365 Business Premium, Office 365 Enterprise e Office 365 Education. Non sono necessarie altre licenze di Office 365. Teams non impone un numero limite di utenti guest che è possibile aggiungere. Tuttavia, il numero totale di utenti guest che possono essere aggiunti al tenant dipende dal limite imposto dalla licenza di Azure AD, che in genere è di 5 guest per ogni utente con licenza. Per altre informazioni, vedere [Licenze di collaborazione B2B di Azure AD](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).


> [!NOTE]
> Gli utenti dell'organizzazione che hanno solo piani di abbonamento a Office 365 autonomi, ad esempio Exchange Online piano 2, non possono essere invitati come utenti guest nell'organizzazione, perché Teams li considera come appartenenti alla stessa organizzazione. Affinché questi utenti possano usare Teams, è necessario assegnare loro un abbonamento a Office 365 Business Premium, Office 365 Enterprise o Office 365 Education. 

## <a name="who-is-a-guest"></a>Chi è un guest?

Un guest è una persona che non è né un dipendente, né uno studente, né un membro dell'organizzazione e che non ha un account aziendale o dell'istituto di istruzione presso l'organizzazione. Ad esempio, gli utenti guest possono includere partner, fornitori o consulenti. Chiunque non faccia parte dell'organizzazione può essere aggiunto come guest in Teams. Questo significa che chiunque abbia un account aziendale, ossia un account Azure Active Directory, o un account di posta elettronica personale, con Outlook.com, Gmail.com o altri, può partecipare come guest in Teams, con accesso completo ai team e ai canali.

Per altre informazioni su ciò che un guest può o non può fare, leggere [Autorizzare l'accesso guest in Microsoft Teams](teams-dependencies.md). In alternativa, vedere la tabella di [confronto tra le funzionalità dei membri del team e degli utenti guest](guest-experience.md#comparison-of-team-member-and-guest-capabilities). 

Infine, tutti gli utenti guest in Teams sono coperti dalla stessa protezione di conformità e controllo del resto di Office 365 e possono essere gestiti in modo sicuro all'interno di Azure AD.

## <a name="why-use-guest-access"></a>Perché usare l'accesso guest?

Con l’accesso guest, le organizzazioni che usano Teams possono consentire l'accesso a team, documenti nei canali, risorse, chat e applicazioni ai propri partner, pur mantenendo il totale controllo dei propri dati aziendali. Tutti gli utenti guest in Teams sono coperti dalla stessa protezione di conformità e controllo del resto di Office 365, e possono essere gestiti in modo sicuro all'interno di Azure AD.  

## <a name="understand-the-limitations-for-guests"></a>Comprendere le limitazioni per gli utenti guest

L'esperienza degli utenti guest presenta limitazioni nel design. È importante assicurarsi di comprendere l'esperienza utente guest, in modo da evitare di provare a risolvere qualcosa che non è un problema. Ad esempio, ecco un elenco di alcune funzionalità che non sono disponibili per gli utenti guest in Microsoft Teams:

- OneDrive for Business
- Ricerca utenti all'esterno di Teams
- Calendario, Riunioni pianificate o Dettagli riunione
- PSTN
- Organigramma
- Creare o aggiornare un team
- Sfogliare i team
- Caricare file in una chat tra due persone
- Gli utenti potranno comunque cercare e trovare altri utenti (all'esterno del team), se conoscono l'ID di posta elettronica completo dell'utente. Per evitare questo problema, gli amministratori IT possono usare modelli come [ricerca nella directory con ambito](teams-scoped-directory-search.md), che permettono di limitare gli utenti guest al proprio elenco indirizzi globale virtuale.
- Attualmente, Teams supporta solo i tipi di utenti guest Stato1 e Stato 2 [come definiti da Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)

Per un elenco completo delle funzionalità di un utente guest in Teams, vedere la tabella di [confronto tra le funzionalità dei membri del team e degli utenti guest](guest-experience.md#comparison-of-team-member-and-guest-capabilities). Per altre informazioni sull'accesso guest a livello di Office 365, vedere [Aggiunta di utenti guest ai Gruppi di Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).

## <a name="how-does-external-access-federation-compare-to-guest-access"></a>Cosa distingue l'accesso esterno (federazione) dall'accesso guest?

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>Altre informazioni

[Contattare il supporto di Office 365 per le aziende - Guida per gli amministratori](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
[Accesso guest ai Gruppi di Office 365](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
