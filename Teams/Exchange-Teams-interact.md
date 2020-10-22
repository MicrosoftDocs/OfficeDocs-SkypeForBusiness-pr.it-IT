---
title: Interazione tra Exchange e Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Informazioni sulle funzionalità esistenti tra Microsoft teams e le varie configurazioni di Exchange, ad esempio la creazione e l'aggiunta di Team, la creazione di canali e altro ancora.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae03611a684f7f596c185873585c844e30d4330b
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650879"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Interazione tra Exchange e Microsoft Teams

> [!Tip]
> Per informazioni su come interagire con i team con Azure Active Directory (AAD), Microsoft 365 groups, Exchange, SharePoint e OneDrive for business, vedere la sessione seguente: [fondazioni di Microsoft teams](https://aka.ms/teams-foundations)

Per l'esperienza completa in teams, ogni utente deve essere abilitato per la creazione di gruppi di Exchange Online, SharePoint Online e Microsoft 365.

Le cassette postali di Exchange degli utenti possono essere ospitate online o in locale.

Gli utenti ospitati in Exchange Online o Exchange dedicato a vNext possono usare tutte le funzionalità di teams. Possono creare e partecipare a team e canali, creare e visualizzare riunioni, chiamare e chattare, modificare le immagini del profilo utente (se il criterio della cassetta postale di Outlook sul Web lo consente) e aggiungere e configurare connettori, schede e bot. Per un elenco più completo delle funzionalità disponibili, vedere la tabella seguente.

Gli utenti ospitati in Exchange Online dedicato (legacy) devono essere sincronizzati con Azure Active Directory in Microsoft 365 o Office 365. Possono creare e partecipare a team e canali, aggiungere e configurare schede e bot e usare le funzionalità di chat e chiamate. Tuttavia, non possono modificare le immagini del profilo, gestire le riunioni, accedere ai contatti di Outlook o gestire i connettori.

> [!IMPORTANT]
> Per l'integrazione con locale, è consigliabile disporre di una distribuzione ibrida di Exchange completa classica con Exchange Server 2016 o versione successiva. Il supporto ibrido moderno è limitato alla disponibilità e non fornirà l'integrazione del calendario dai team alle cassette postali locali, ad esempio. Per altre informazioni sulla configurazione di una distribuzione ibrida, vedere [distribuzioni ibride di Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid).

Gli utenti con cassette postali ospitate in locale devono essere sincronizzati con Azure Active Directory. Possono usare tutte le funzionalità dello scenario precedente, ma possono anche gestire le riunioni se sono soddisfatte le condizioni elencate nei [requisiti per le cassette postali ospitate](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) nella sezione locale.

La tabella seguente fornisce un utile riferimento rapido per la disponibilità delle caratteristiche in base all'ambiente Exchange.

**Azioni supportate:**

| La cassetta postale dell'utente è ospitata in:                                        | eDiscovery       | &nbsp;Blocco legale    | Conservazione  | MGMT per team e canali | Creare e visualizzare riunioni in teams | Modificare l'immagine del profilo utente | Cronologia chiamate | Gestire i contatti | Accedere ai contatti di Outlook | Segreteria telefonica  | Aggiungere e configurare connettori | Aggiungere e configurare le schede | Aggiungere e configurare i bot |
|---------------------------------------------------------------------|------------------|--------------------|------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                 | Sì <sup>1</sup> | Sì <sup>1</sup>   | Sì        | Sì                   | Sì                               | Sì<sup>7</sup>             | Sì          | Sì             | Sì <sup>6</sup>        | Sì        | Sì                          | Sì                    | Sì                    |
| **VNext dedicato a Exchange Online**                                 | Sì <sup>1</sup> | Sì <sup>1</sup>   | Sì        | Sì                   | Sì                               | Sì<sup>7</sup>             | Sì          | Sì             | Sì <sup>6</sup>        | Sì        | Sì                          | Sì                    | Sì                    |
| **Exchange Online dedicato-legacy** (obbligatorio per la sincronizzazione con Azure ad)  | Sì <sup>1</sup> | Sì <sup>1, 2</sup> | Sì <sup>3</sup> | Sì                   | No                                | No                          | Sì          | Sì             | No                      | Sì <sup>4</sup> | Sì <sup>5</sup>                   | Sì                    | Sì                    |
| **Exchange locale** (sincronizzazione con Azure ad) | Sì <sup>1</sup> | Sì <sup>1</sup>   | Sì <sup>3</sup> | Sì                   | Sì <sup>8</sup>         | No                          | Sì          | Sì             | No                      | Sì <sup>4</sup> | Sì <sup>5</sup>                   | Sì                    | Sì                    |

<sup>1</sup> eDiscovery e Legal detiene per la conformità ai messaggi di canale è supportato per tutte le opzioni di hosting.

<sup>2</sup> i messaggi di chat privati di teams non sono ancora supportati per il blocco legale per l'opzione di hosting.

<sup>3</sup> la conservazione userà una cassetta postale ombreggiata per l'utente online per archiviare i messaggi.

<sup>4</sup> gli utenti di teams con cassetta postale di Exchange locale possono usare la segreteria telefonica con teams e ricevere messaggi vocali in Outlook, ma i messaggi vocali non saranno disponibili per la visualizzazione o la riproduzione all'interno del client teams.

<sup>5</sup> se uno dei proprietari di un team può aggiungere connettori, tutti gli altri membri del team potranno farlo, anche se le cassette postali vengono ospitate in locale.

<sup>6</sup> solo contatti nella cartella Contatti predefinita. L'accesso ad altri contatti o cartelle secondarie non è supportato.

<sup>7</sup> teams onora l'impostazione di [Outlook sul criterio delle cassette postali Web](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) configurata dagli amministratori del tenant per controllare se gli utenti possono modificare l'immagine del profilo. Se l'impostazione **-SetPhotoEnabled** è disattivata nel criterio, gli utenti non possono aggiungere, modificare o rimuovere l'immagine del profilo. Ad esempio, se un utente carica un'immagine del profilo approvata dal reparto IT o HR dell'organizzazione, non è necessaria alcuna azione. Tuttavia, se un utente carica un'immagine non appropriata, modificarla in base ai criteri interni dell'organizzazione.

<sup>8</sup> è necessario soddisfare i requisiti elencati nei [requisiti per creare e visualizzare le riunioni per le cassette postali ospitate](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) nella sezione locale.

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Requisiti per ottenere il massimo da Microsoft Teams

Microsoft teams funziona con diversi servizi Microsoft 365 e Office 365 per consentire agli utenti un'esperienza avanzata. Per supportare questa esperienza, è necessario abilitare determinate funzionalità o servizi e assegnare licenze.

- Agli utenti deve essere assegnata una licenza di Exchange Online.

- SharePoint Online è necessario per condividere e archiviare i file nelle conversazioni del team. Microsoft teams non supporta SharePoint locale.

- Gli utenti devono essere assegnati a una licenza di SharePoint Online se vogliono condividere file in chat. Se gli utenti non sono assegnati e abilitati con le licenze di SharePoint Online, non hanno lo spazio di archiviazione di OneDrive for business in Microsoft 365 o Office 365. La condivisione dei file continuerà a funzionare nei canali, ma gli utenti non potranno condividere file in chat senza spazio di archiviazione di OneDrive for business in Microsoft 365 o Office 365.

- Gli utenti devono essere abilitati per la creazione di gruppi di Microsoft 365 per creare team in Microsoft teams.

  > [!IMPORTANT]
  > Se si disinstalla il client Skype for business dopo aver spostato un utente in modalità **solo teams** , la presenza potrebbe smettere di funzionare in Outlook e in altre app di Office. L’icona di presenza funziona bene in Teams. Per risolvere il problema, selezionare l'immagine del profilo nell'angolo in alto a destra di Microsoft teams e quindi selezionare **Impostazioni**. Nella scheda **generale** in **applicazione**Selezionare **registra teams come app di chat per Office (è necessario riavviare le applicazioni di Office)**. Dopo aver selezionato questa opzione, chiudere e riaprire tutte le app di Office, incluso Outlook. Dopo l'apertura di Outlook, le informazioni sulla presenza saranno disponibili.

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>Requisiti per creare e visualizzare riunioni per le cassette postali ospitate in locale

Se le cassette postali sono ospitate localmente, per creare e visualizzare le riunioni è necessario soddisfare i requisiti seguenti:

- La licenza necessaria per i team deve essere assegnata per l'utente sincronizzato di Azure Active Directory.

- Gli utenti devono essere sincronizzati con Azure Active Directory. Per informazioni su come usare Azure AD Connect per la sincronizzazione con Azure Active Directory, vedere [documentazione sull'identità ibrida](https://docs.microsoft.com/azure/active-directory/hybrid/).

- Le cassette postali sono ospitate in Exchange Server 2016 aggiornamento cumulativo 3 o versione successiva.

- L'individuazione automatica e i servizi Web di Exchange vengono pubblicati esternamente.

- L'autenticazione OAuth è configurata preferibilmente tramite la configurazione guidata ibrida di Exchange in cui è in corso una configurazione ibrida completa (classica o moderna). Se non si riesce a usare la configurazione guidata ibrida, configurare OAuth come descritto in [configurare l'autenticazione OAuth tra le organizzazioni Exchange e Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

  > [!NOTE]
  > Exchange Trusts OAuth token dal servizio teams, noto come EvoSTS. Il passaggio 1 dovrebbe essere sufficiente, ma solo EvoSTS; ACS viene usato per la ricerca di disponibilità nel calendario.

- Viene impostata la casella di controllo per la caratteristica di distribuzione ibrida di Exchange in Azure AD Connect.

- Per il supporto dell'app calendario e i team di Outlook Add-In per Mac, gli URL del servizio Web di Exchange devono essere configurati come nomi SPN in tenant Azure AD per l'entità servizio di Exchange. Questo passaggio viene eseguito con la configurazione guidata ibrida o seguendo [i passaggi manuali per l'autenticazione moderna ibrida](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad).

Per abilitare la delega del calendario per questi utenti:

- È inoltre necessario completare i passaggi 2-3 come descritto in [configurare Integration e OAuth tra Skype for business online ed Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises); Questa procedura fornirà all'applicazione per la pianificazione dei team le autorizzazioni necessarie per confermare le autorizzazioni di delega.
 
  > [!NOTE]
  > Il passaggio 2 include l'assegnazione di ruolo per ArchiveApplication, che non è necessaria per la delega.

- Il componente aggiuntivo pianificazione teams per Outlook durante la pianificazione di una riunione per conto di un utente richiede Exchange 2013 CU19 o versione successiva. Questo per supportare l'individuazione non autenticata della cassetta postale da parte del servizio per verificare le autorizzazioni di delega per la cassetta postale del delegante. Il percorso delegato e delegante può essere Exchange 2013 o versione successiva oppure Exchange Online, ma l'individuazione automatica deve essere risolta in Exchange 2013 CU19 o versione successiva.

## <a name="additional-considerations"></a>Considerazioni aggiuntive

Ecco alcuni aspetti aggiuntivi da considerare quando implementi Microsoft teams nell'organizzazione.

- In Microsoft teams, funzionalità per la sicurezza e la conformità come eDiscovery, ricerca contenuto, archiviazione e blocco legale migliorano il lavoro in ambienti Exchange Online e SharePoint Online. Per le conversazioni di canale, i messaggi vengono inseriti nel journal nella cassetta postale del gruppo in Exchange Online, dove sono disponibili per eDiscovery. Se SharePoint Online e OneDrive for business (con l'account aziendale o dell'Istituto di istruzione) sono abilitati nell'organizzazione e per gli utenti, queste caratteristiche di conformità sono disponibili anche per tutti i file all'interno di teams.

- Controllare e proteggere la configurazione dei criteri di conformità in teams e Exchange con l'accesso condizionale. Per altre informazioni [, vedere come funzionano i criteri di accesso condizionale per i team?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)

- Se l'organizzazione ha requisiti di conformità per verificare che tutte le discussioni delle riunioni siano individuabili, è consigliabile disabilitare le riunioni private se l'organizzatore ha una cassetta postale di Exchange locale. Per altre informazioni, vedere [consentire la pianificazione di riunioni private](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-scheduling-private-meetings).

- In una distribuzione ibrida di Exchange, il contenuto dei messaggi di chat è ricercabile indipendentemente dal fatto che i partecipanti alla chat abbiano una cassetta postale basata sul cloud o una cassetta postale locale. Per altre informazioni, vedere [ricerca di cassette postali basate su cloud per gli utenti locali](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Per informazioni su come cercare contenuto in teams, leggere [Ricerca contenuto nel centro conformità Microsoft 365](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

## <a name="troubleshooting"></a>Risoluzione dei problemi

Per una guida alla risoluzione dei problemi completa nell'argomento, vedere risolvere i problemi di [interazione tra Microsoft teams ed Exchange Server](https://docs.microsoft.com/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue).
