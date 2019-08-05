---
title: Interazione tra Exchange e Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dstrome
description: Informazioni sulle funzionalità esistenti tra Microsoft teams e le varie configurazioni di Exchange, ad esempio la creazione e l'aggiunta di Team, la creazione di canali e altro ancora.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bedaee766005787bb7b532f4f5561faf91dd35d
ms.sourcegitcommit: bd9b29cdaa183b1f5cc2d643a5a2d231a56a2c3f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "36184801"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Interazione tra Exchange e Microsoft Teams

> [!Tip]
> Per informazioni su come interagire con i team con Azure Active Directory (AAD), Office 365 groups, Exchange, SharePoint e OneDrive for business, vedere la sessione seguente: [fondazioni di Microsoft teams](https://aka.ms/teams-foundations)

Per l'esperienza completa in teams, ogni utente deve essere abilitato per la creazione di gruppi di Exchange Online, SharePoint Online e Office 365.

Le cassette postali di Exchange degli utenti possono essere ospitate online o in locale. Gli utenti ospitati in Exchange Online o Exchange dedicato a vNext possono usare tutte le funzionalità di teams. Possono creare e partecipare a team e canali, creare e visualizzare riunioni, chiamare e chattare, modificare le immagini del profilo utente, aggiungere e configurare connettori, schede e bot.

Gli utenti ospitati in Exchange Online dedicato-legacy o Exchange locale devono essere sincronizzati con Azure Active Directory per Office 365. Possono creare e partecipare a team e canali, aggiungere e configurare schede e bot e chattare e chiamare. Tuttavia, non possono modificare le immagini del profilo utente o aggiungere e configurare i connettori. Possono ricevere messaggi da connettori configurati da altri utenti. Per la creazione e la visualizzazione delle riunioni, è un miscuglio: la creazione e la visualizzazione delle riunioni è supportata per l'aggiornamento cumulativo 3 (CU3) di Exchange 2016 e versioni successive, ma non per le versione precedenti a Exchange 2016 CU3.

La tabella seguente fornisce informazioni per gli utenti con Exchange Online ospitati in diversi ambienti.

**Azioni supportate:**

| La cassetta postale dell'utente è ospitata in: | eDiscovery| Blocco&nbsp;legale | Conservazione| MGMT per team e canali |Creare e visualizzare le riunioni| Modificare l'immagine del profilo utente | Cronologia chiamate | Gestire i contatti | Accedere ai contatti di Outlook | Casella vocale |Aggiungere e configurare connettori|Aggiungere e configurare le schede|Aggiungere e configurare i bot| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Sì <sup>2</sup>|Sì <sup>2</sup>|Sì|Supporto per più paesi|Supporto per più paesi|Supporto per più paesi|Supporto per più paesi|Supporto per più paesi|Supporto per più paesi|Supporto per più paesi|Supporto per più paesi|Supporto per più paesi|Supporto per più paesi|
|**VNext dedicato a Exchange Online**|Sì <sup>2</sup>|Sì <sup>2</sup>|Sì|Supporto per più paesi|Supporto per più paesi|Supporto per più paesi|Supporto per più paesi|Supporto per più paesi|Supporto per più paesi|Supporto per più paesi|Supporto per più paesi|Supporto per più paesi|Supporto per più paesi|
|**Exchange Online dedicato-legacy** (È necessario eseguire la sincronizzazione con Azure AD)|Sì <sup>2</sup>|Sì <sup>2, 3</sup>|Sì <sup>4|Sì|Supporto per riunioni private con ID conferenza di riunione dinamici|No|Sì|Sì|Supporto per riunioni private con ID conferenza di riunione dinamici|Sì <sup>5|Sì|Supporto per più paesi|Supporto per più paesi|
|**Exchange locale** (È necessario eseguire la sincronizzazione con Azure AD)|Sì <sup>2</sup>| Sì <sup>2, 3</sup> |Sì <sup>4|Sì|Sì (Exchange 2016 CU3 +)|Sì (Exchange 2016 CU3 +)|Sì|Sì|Supporto per riunioni private con ID conferenza di riunione dinamici|Sì <sup>5|Sì|Supporto per più paesi|Supporto per più paesi|

<sup>1</sup> Exchange 2016 CU3 e versioni successive supportate  
<sup>2</sup> eDiscovery e Legal detiene per la conformità ai messaggi di canale è supportato per tutte le opzioni di hosting.  
<sup>3</sup> i messaggi di chat privati di teams non sono ancora supportati per il blocco legale per l'opzione di hosting.

<sup>4</sup> la conservazione userà una cassetta postale ombreggiata per l'utente online per archiviare i messaggi. [Microsoft teams supporta eDiscovery per gli utenti di teams in un ambiente ibrido di Exchange](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009).

<sup>5</sup> gli utenti di teams con la cassetta postale di Exchange locale possono usare la segreteria telefonica con teams e ricevere messaggi vocali in Outlook, ma i messaggi vocali non saranno disponibili per la visualizzazione o la riproduzione all'interno del client teams.

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Requisiti per ottenere il massimo da Microsoft Teams

Microsoft teams funziona con diversi servizi di Office 365 per consentire agli utenti un'esperienza avanzata. Per supportare questa esperienza, è necessario abilitare determinate funzionalità o servizi e assegnare licenze.

- SharePoint Online è necessario per condividere e archiviare i file nelle conversazioni del team. Microsoft teams non supporta SharePoint locale.

- Gli utenti devono essere assegnati a una licenza di SharePoint Online se vogliono condividere file in chat. Se gli utenti non sono assegnati e abilitati con le licenze di SharePoint Online, non hanno spazio di archiviazione di OneDrive for business in Office 365. La condivisione dei file continuerà a funzionare nei canali, ma gli utenti non potranno condividere file in chat senza spazio di archiviazione di OneDrive for business in Office 365.

- Gli utenti devono essere abilitati per la creazione di gruppi di Office 365 per creare team in Microsoft teams.

- Per consentire a Microsoft teams di lavorare con Exchange locale, è necessario configurare il nuovo protocollo di autenticazione di Exchange OAuth come descritto in [configurare l'autenticazione OAuth tra le organizzazioni Exchange e Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

> [!NOTE]
>Per l'integrazione di Exchange locale e teams, è necessario assegnare la licenza necessaria per l'utente sincronizzato di AAD.

## <a name="additional-considerations"></a>Considerazioni aggiuntive

Ecco alcuni aspetti aggiuntivi da considerare quando implementi Microsoft teams nell'organizzazione.

- In Microsoft teams, funzionalità per la sicurezza e la conformità come eDiscovery, ricerca contenuto, archiviazione e blocco legale migliorano il lavoro in ambienti Exchange Online e SharePoint Online. Per le conversazioni di canale, i messaggi vengono inseriti nel journal nella cassetta postale del gruppo in Exchange Online, dove sono disponibili per eDiscovery. Se SharePoint Online e OneDrive for business (con l'account aziendale o dell'Istituto di istruzione) sono abilitati nell'organizzazione e per gli utenti, queste caratteristiche di conformità sono disponibili anche per tutti i file all'interno di teams.

- Controllare e proteggere la configurazione dei criteri di conformità in teams e Exchange con l'accesso condizionale. Per altre informazioni [, vedere come funzionano i criteri di accesso condizionale per i team?](security-compliance-overview.md#how-do-conditional-access-policies-work-for-teams) .

- Se l'organizzazione ha requisiti di conformità per verificare che tutte le discussioni delle riunioni siano individuabili, è consigliabile disabilitare le riunioni private se l'organizzatore ha una cassetta postale di Exchange locale.

- In una distribuzione ibrida di Exchange, il contenuto dei messaggi di chat è ricercabile indipendentemente dal fatto che i partecipanti alla chat abbiano una cassetta postale basata sul cloud o una cassetta postale locale. Per altre informazioni, vedere [ricerca di cassette postali basate su cloud per gli utenti locali in Office 365](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Per informazioni su come cercare contenuto in teams, leggere [Ricerca contenuto nel centro conformità & sicurezza di Office 365](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

> [!TIP]
> Per informazioni su come usare Azure AD Connect per la sincronizzazione con Azure Active Directory, vedere [integrazione delle identità locali con Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=854600).
