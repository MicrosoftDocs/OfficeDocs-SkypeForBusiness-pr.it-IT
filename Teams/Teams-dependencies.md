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
ms.reviewer: rafarhi
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: Gestire le funzionalità dell'accesso guest di Microsoft Teams tramite quattro diversi livelli di autorizzazione.
ms.openlocfilehash: 1040d548140d0fbb781e9cc9296be3d374b7b314
ms.sourcegitcommit: 20f881285edf699ebf36320664166c95ccd6df35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2020
ms.locfileid: "48918988"
---
# <a name="authorize-guest-access-in-microsoft-teams"></a>Autorizzare l'accesso guest in Microsoft Teams

Per soddisfare i requisiti della propria organizzazione, è possibile gestire le funzionalità e le funzionalità di accesso Guest dei team tramite quattro diversi livelli di autorizzazione. Tutti i livelli di autorizzazione si applicano all'organizzazione Microsoft 365. Ogni livello di autorizzazione controlla l'esperienza degli utenti guest come illustrato di seguito:

- **Azure Active Directory** : l'accesso guest in teams si basa sulla piattaforma di Azure ad business-to-business (B2B). Questo livello di autorizzazione controlla l'esperienza degli utenti guest a livello di directory, tenant e applicazione.
- **Teams** : controlla l'esperienza Guest in teams only.
- **Microsoft 365 groups** : controlla l'esperienza Guest in gruppi e team di Microsoft 365.
- **SharePoint e OneDrive** : controlla l'esperienza Guest in SharePoint, OneDrive, Microsoft 365 Groups e teams.

Questi diversi livelli di autorizzazione forniscono la massima flessibilità per la configurazione dell'accesso guest per l'organizzazione. Ad esempio, se non si vuole consentire agli utenti guest in teams ma si vuole consentire l'accesso globale all'organizzazione, è sufficiente disattivare gli accessi guest in teams. Un altro esempio: è possibile abilitare l'accesso Guest ai livelli di Azure AD, teams e groups, ma [disabilitare l'aggiunta di utenti guest in team selezionati che corrispondono a uno o più criteri, ad esempio la classificazione dei dati è uguale a Confidential](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites). SharePoint e OneDrive hanno le proprie impostazioni di accesso guest che non si basano sui gruppi di Microsoft 365.

Per le istruzioni di configurazione dell'accesso Guest end-to-end, vedere [collaborare con gli utenti in un team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).

> [!NOTE]
> Gli utenti guest sono soggetti ai limiti dei servizi descritti in [Descrizione dei servizi di Office 365 e Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=282347) e [Limitazioni di Collaborazione B2B di Azure AD](https://docs.microsoft.com/azure/active-directory/external-identities/current-limitations). 

Il diagramma seguente mostra il modo in cui la dipendenza dalle autorizzazioni di accesso guest viene concessa e integrata tra Azure Active Directory, teams e Microsoft 365.

> [!div class="mx-imgBorder"]
> ![Diagramma delle dipendenze di autorizzazione per l'accesso guest](media/teams_dependencies_image1.png)

Il diagramma successivo mostra, a un livello generale, come funziona l'esperienza utente con il modello di autorizzazione tramite un flusso tipico di invito e riscatto dell'accesso guest.

> [!div class="mx-imgBorder"]
> ![Diagramma dei flussi di invito e riscatto](media/authorize-guest-image1.png)

È importante notare che le app, i bot e i connettori potrebbero richiedere un set di autorizzazioni personalizzato e/o un consenso specifico per l'account utente. Potrebbe essere necessario concederli separatamente. Allo stesso modo, SharePoint potrebbe imporre limiti di condivisione aggiuntivi esterni per uno specifico utente, gruppi di utenti o persino a livello del sito.

I due diagrammi precedenti sono disponibili anche in [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true).

## <a name="control-guest-access-in-azure-active-directory"></a>Controllare l'accesso guest in Azure Active Directory

Usare Azure AD per determinare se i collaboratori esterni possono essere invitati al tenant come utenti guest e in quali modi. Per altre informazioni sull'accesso guest di Azure B2B, consultare [Che cos'è l'accesso utente guest in Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b). Per informazioni sui ruoli di Azure AD, consultare [Concedere autorizzazioni agli utenti di organizzazioni partner nel tenant di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role).

Le impostazioni per gli inviti si applicano a livello di organizzazione e controllano l'esperienza Guest a livello di directory e di applicazione. Queste impostazioni possono essere configurate in [impostazioni di collaborazione esterna](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings).

Azure AD include le seguenti impostazioni per la configurazione degli utenti esterni:

- [Restrizioni di accesso degli utenti Guest](https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-restrict-guest-permissions)

- **Amministratori e utenti nel ruolo mittente dell'invito guest possono invitare** : **Sì** significa che gli amministratori e gli utenti nel ruolo mittente invito possono invitare guest nel tenant. **No** significa che gli amministratori e gli utenti non possono invitare guest nel tenant.
- **I membri possono invitare** : per consentire ai membri non amministratori della directory di invitare utenti guest, impostare questo criterio su **Yes** (scelta consigliata). Se si preferisce che solo gli amministratori siano autorizzati ad aggiungere utenti guest, è possibile impostare questo criterio su **No**. Tenere presente che l'opzione **No** limiterà l'esperienza guest per i proprietari di team non amministratori, che potranno aggiungere in Teams solo utenti guest già aggiunti in Azure AD dall'amministratore.
- **I guest possono invitare** : **Sì** significa che gli utenti guest della directory possono invitare altri guest a collaborare sulle risorse protette di Azure AD, come i siti SharePoint o le risorse di Azure. **No** significa che gli utenti guest non possono invitare altri guest a collaborare con l'organizzazione. Anche se impostato su **Sì** , l'ospite non può invitare altri ospiti in teams.
 
Per altre informazioni su come controllare chi può invitare gli ospiti, vedere [abilitare la collaborazione esterna B2B e gestire chi può invitare Guest](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).

> [!NOTE]
> È possibile gestire anche i domini che possono essere invitati nel tenant come utenti guest. Vedere [consentire o bloccare gli inviti agli utenti B2B di organizzazioni specifiche](https://docs.microsoft.com/azure/active-directory/external-identities/allow-deny-list).

Non è necessario aggiungere l'account utente guest manualmente in Azure AD B2B in quanto l'account verrà aggiunto automaticamente alla directory quando il guest viene aggiunto a Teams.

### <a name="licensing-for-guest-access"></a>Licenze per l'accesso guest

Le licenze di accesso Guest usano i prezzi delle identità esterne di Azure AD e si basano su clienti attivi mensili. Per informazioni dettagliate, vedere [modello di fatturazione per le identità esterne di Azure ad](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) .

> [!NOTE]
> Gli utenti dell'organizzazione che hanno solo piani di abbonamento a Office 365 autonomi, ad esempio Exchange Online piano 2, non possono essere invitati come utenti guest nell'organizzazione, perché Teams li considera come appartenenti alla stessa organizzazione. Affinché questi utenti possano usare Teams, è necessario assegnare loro un abbonamento a Microsoft 365 Business Standard, Office 365 Enterprise o Office 365 Education. 

## <a name="external-access-federation-vs-guest-access"></a>Accesso esterno (federazione) e accesso guest

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a>Argomenti correlati

- [Riferimento alle impostazioni di condivisione guest di Microsoft 365](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)

[Configurare la collaborazione sicura con Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)
