---
title: Autorizzare l'accesso guest in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- SPO_Content
- m365initiative-externalcollab
ms.reviewer: rafarhi
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: Gestire le funzionalità dell'accesso guest di Microsoft Teams tramite quattro diversi livelli di autorizzazione.
ms.openlocfilehash: d52fdeb1f9867ac1faa0f8cf77023109155a8967
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094468"
---
# <a name="authorize-guest-access-in-microsoft-teams"></a>Autorizzare l'accesso guest in Microsoft Teams

Per soddisfare i requisiti dell'organizzazione, è possibile gestire le funzionalità di accesso guest di Teams tramite quattro diversi livelli di autorizzazione. Tutti i livelli di autorizzazione si applicano all’organizzazione di Microsoft 365. Ogni livello di autorizzazione controlla l'esperienza degli utenti guest come illustrato di seguito:

- **Azure Active Directory**: l'accesso guest in Teams si basa sulla piattaforma business-to-business (B2B) di Azure AD. Questo livello di autorizzazione controlla l'esperienza degli utenti guest a livello di directory, tenant e applicazione.
- **Teams**: controlla l'esperienza degli utenti guest solo in Teams.
- **Gruppi di Microsoft 365**: controlla l'esperienza degli utenti guest in Gruppi di Microsoft 365 e Teams.
- **SharePoint Online e OneDrive**: controlla l'esperienza degli utenti guest in SharePoint, OneDrive, Gruppi di Microsoft 365 e Teams.

Questi diversi livelli di autorizzazione forniscono la massima flessibilità per la configurazione dell'accesso guest per l'organizzazione. Ad esempio, se non si vuole fornire agli utenti guest l'accesso in Teams ma si vuole consentire l'accesso globale nell'organizzazione, basta disattivare l'accesso guest in Teams. Un altro esempio: è possibile abilitare l'accesso guest a livello di Azure AD, Teams e Gruppi, ma bisogna [disabilitare l'aggiunta degli utenti guest a determinati team che soddisfano uno o più criteri come una classificazione dati di tipo riservato](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites). SharePoint e OneDrive hanno le proprie impostazioni per l'accesso guest che non si basano su Gruppi di Microsoft 365.

Per le istruzioni di configurazione sull'accesso guest end-to-end, vedere [Collaborare con gli utenti guest in un team](/microsoft-365/solutions/collaborate-as-team).

> [!NOTE]
> Gli utenti guest sono soggetti ai limiti dei servizi descritti in [Descrizione dei servizi di Office 365 e Microsoft 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) e [Limitazioni di Collaborazione B2B di Azure AD](/azure/active-directory/external-identities/current-limitations). 

Il diagramma seguente mostra in che modo la dipendenza di autorizzazione per l'accesso guest viene concessa e integrata tra Azure Active Directory, Teams e Microsoft 365.

> [!div class="mx-imgBorder"]
> ![Diagramma delle dipendenze di autorizzazione per l'accesso guest](media/teams_dependencies_image1.png)

Il diagramma successivo mostra, a un livello generale, come funziona l'esperienza utente con il modello di autorizzazione tramite un flusso tipico di invito e riscatto dell'accesso guest.

> [!div class="mx-imgBorder"]
> ![Diagramma dei flussi di invito e riscatto](media/authorize-guest-image1.png)

È importante evidenziare che app, bot e connettori potrebbero richiedere il proprio set di autorizzazioni e/o il consenso specifico per l'account utente. Potrebbe essere necessario concederli separatamente. Allo stesso modo, SharePoint potrebbe imporre limiti di condivisione aggiuntivi esterni per uno specifico utente, gruppi di utenti o persino a livello del sito.

I due diagrammi precedenti sono disponibili anche in [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true).

## <a name="control-guest-access-in-azure-active-directory"></a>Controllare l'accesso guest in Azure Active Directory

Usare Azure AD per determinare se i collaboratori esterni possono essere invitati al tenant come utenti guest e in quali modi. Per altre informazioni sull'accesso guest di Azure B2B, consultare [Che cos'è l'accesso utente guest in Azure Active Directory B2B?](/azure/active-directory/b2b/what-is-b2b). Per informazioni sui ruoli di Azure AD, consultare [Concedere autorizzazioni agli utenti di organizzazioni partner nel tenant di Azure Active Directory](/azure/active-directory/b2b/add-guest-to-role).

Le impostazioni per gli inviti si applicano a livello di organizzazione e controllano l'esperienza degli utenti guest a livello di directory e applicazione. È possibile configurare queste impostazioni in [Impostazioni per la collaborazione esterna](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings).

Azure AD include le seguenti impostazioni per la configurazione degli utenti esterni:

- [Restrizioni di accesso degli utenti guest](/azure/active-directory/users-groups-roles/users-restrict-guest-permissions)

- **Amministratori e utenti nel ruolo mittente dell'invito guest possono invitare**: **Sì** significa che gli amministratori e gli utenti nel ruolo mittente invito possono invitare guest nel tenant. **No** significa che gli amministratori e gli utenti non possono invitare guest nel tenant.
- **I membri possono invitare**: per consentire ai membri non amministratori della directory di invitare utenti guest, impostare questo criterio su **Yes** (scelta consigliata). Se si preferisce che solo gli amministratori siano autorizzati ad aggiungere utenti guest, è possibile impostare questo criterio su **No**. Tenere presente che l'opzione **No** limiterà l'esperienza guest per i proprietari di team non amministratori, che potranno aggiungere in Teams solo utenti guest già aggiunti in Azure AD dall'amministratore.
- **I guest possono invitare**: **Sì** significa che gli utenti guest della directory possono invitare altri guest a collaborare sulle risorse protette di Azure AD, come i siti SharePoint o le risorse di Azure. **No** significa che gli utenti guest non possono invitare altri guest a collaborare con l'organizzazione. Anche se impostata su **Sì**, gli utenti guest non possono invitare altri utenti guest in Teams.
 
Per altre informazioni su come controllare chi può invitare utenti guest, vedere [Abilitare la collaborazione esterna B2B e gestire gli utenti che possono invitare guest](/azure/active-directory/b2b/delegate-invitations).

> [!NOTE]
> È possibile gestire anche i domini che possono essere invitati nel tenant come utenti guest. Vedere [Consentire o bloccare gli inviti agli utenti B2B di specifiche organizzazioni](/azure/active-directory/external-identities/allow-deny-list).

Non è necessario aggiungere l'account utente guest manualmente in Azure AD B2B in quanto l'account verrà aggiunto automaticamente alla directory quando il guest viene aggiunto a Teams.

### <a name="licensing-for-guest-access"></a>Licenze per l'accesso guest

Le licenze di accesso guest usano i prezzi di Azure AD per identità esterne e si basano sui guest attivi mensilmente. Per dettagli vedere [Modello di fatturazione per Azure Active Directory per identità esterne](/azure/active-directory/external-identities/external-identities-pricing).

> [!NOTE]
> Gli utenti dell'organizzazione che hanno solo piani di abbonamento a Office 365 autonomi, ad esempio Exchange Online piano 2, non possono essere invitati come utenti guest nell'organizzazione, perché Teams li considera come appartenenti alla stessa organizzazione. Affinché questi utenti possano usare Teams, è necessario assegnare loro un abbonamento a Microsoft 365 Business Standard, Office 365 Enterprise o Office 365 Education. 

## <a name="external-access-federation-vs-guest-access"></a>Accesso esterno (federazione) e accesso guest

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a>Argomenti correlati

- [Riferimento alle impostazioni di condivisione guest di Microsoft 365](/Office365/Enterprise/microsoft-365-guest-settings)

[Configurare la collaborazione sicura con Microsoft 365](/microsoft-365/solutions/setup-secure-collaboration-with-teams)