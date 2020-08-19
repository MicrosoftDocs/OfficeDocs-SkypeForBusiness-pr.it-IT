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
ms.openlocfilehash: 52f40e9eacc75c15720d5d908709c5840d9474b3
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803788"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Interazione tra Exchange e Microsoft Teams

> [!Tip]
> Per informazioni su come interagire con i team con Azure Active Directory (AAD), Microsoft 365 groups, Exchange, SharePoint e OneDrive for business, vedere la sessione seguente: [fondazioni di Microsoft teams](https://aka.ms/teams-foundations)

Per l'esperienza completa in teams, ogni utente deve essere abilitato per la creazione di gruppi di Exchange Online, SharePoint Online e Microsoft 365.

Le cassette postali di Exchange degli utenti possono essere ospitate online o in locale. Per l'integrazione con locale, è consigliabile disporre di una distribuzione ibrida classica di Exchange completa. Per altre informazioni sulla configurazione di una distribuzione ibrida, vedere [distribuzioni ibride di Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid).

Gli utenti ospitati in Exchange Online o Exchange dedicato a vNext possono usare tutte le funzionalità di teams. Possono creare e partecipare a team e canali, creare e visualizzare riunioni, chiamare e chattare, modificare le immagini del profilo utente (se il criterio della cassetta postale di Outlook sul Web lo consente) e aggiungere e configurare connettori, schede e bot. Per un elenco più completo delle funzionalità disponibili, vedere la tabella seguente.

Gli utenti ospitati in Exchange Online dedicato (legacy) devono essere sincronizzati con Azure Active Directory in Microsoft 365 o Office 365. Possono creare e partecipare a team e canali, aggiungere e configurare schede e bot e usare le funzionalità di chat e chiamate. Tuttavia, non possono modificare le immagini del profilo, gestire le riunioni, accedere ai contatti di Outlook o gestire i connettori.

Gli utenti con cassette postali ospitate in locale devono essere sincronizzati con Azure Active Directory. Possono usare tutte le funzionalità dello scenario precedente, ma possono anche gestire le riunioni, fornendo Exchange Server 2016 (aggiornamento cumulativo 3) o versioni successive, in locale con OAuth configurato (preferibilmente tramite la configurazione guidata ibrida di Exchange), come descritto in [configurare l'autenticazione OAuth tra le organizzazioni di Exchange e Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help). Per abilitare la delega del calendario per questi utenti, è anche necessario completare i passaggi 2-3 come descritto in [configurare l'integrazione e il protocollo OAuth tra Skype for business online ed Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises); Questa procedura fornirà all'applicazione per la pianificazione dei team le autorizzazioni necessarie per confermare le autorizzazioni di delega.

La tabella seguente fornisce un utile riferimento rapido per la disponibilità delle caratteristiche in base all'ambiente Exchange.

**Azioni supportate:**

| La cassetta postale dell'utente è ospitata in:                                        | eDiscovery       | &nbsp;Blocco legale    | Conservazione  | MGMT per team e canali | Creare e visualizzare riunioni in teams | Modificare l'immagine del profilo utente | Cronologia chiamate | Gestire i contatti | Accedere ai contatti di Outlook | Segreteria telefonica  | Aggiungere e configurare connettori | Aggiungere e configurare le schede | Aggiungere e configurare i bot |
|---------------------------------------------------------------------|------------------|--------------------|------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                 | Sì <sup>1</sup> | Sì <sup>1</sup>   | Sì        | Sì                   | Sì                               | Sì<sup>7</sup>             | Sì          | Sì             | Sì <sup>6</sup>        | Sì        | Sì                          | Sì                    | Sì                    |
| **VNext dedicato a Exchange Online**                                 | Sì <sup>1</sup> | Sì <sup>1</sup>   | Sì        | Sì                   | Sì                               | Sì<sup>7</sup>             | Sì          | Sì             | Sì <sup>6</sup>        | Sì        | Sì                          | Sì                    | Sì                    |
| **Exchange Online dedicato-legacy** (obbligatorio per la sincronizzazione con Azure ad)  | Sì <sup>1</sup> | Sì <sup>1, 2</sup> | Sì <sup> 3 | Sì                   | No                                | No                          | Sì          | Sì             | No                      | Sì <sup> 4 | Sì <sup> 5                   | Sì                    | Sì                    |
| **Exchange locale** (è necessario eseguire la sincronizzazione con Azure ad & OAuth config) | Sì <sup>1</sup> | Sì <sup>1</sup>   | Sì <sup> 3 | Sì                   | Sì (Exchange 2016 CU3 +)          | No                          | Sì          | Sì             | No                      | Sì <sup> 4 | Sì <sup> 5                   | Sì                    | Sì                    |

<sup>1</sup> eDiscovery e Legal detiene per la conformità ai messaggi di canale è supportato per tutte le opzioni di hosting.

<sup>2</sup> i messaggi di chat privati di teams non sono ancora supportati per il blocco legale per l'opzione di hosting.

<sup>3</sup> la conservazione userà una cassetta postale ombreggiata per l'utente online per archiviare i messaggi.

<sup>4</sup> gli utenti di teams con cassetta postale di Exchange locale possono usare la segreteria telefonica con teams e ricevere messaggi vocali in Outlook, ma i messaggi vocali non saranno disponibili per la visualizzazione o la riproduzione all'interno del client teams.

<sup>5</sup> se uno dei proprietari di un team può aggiungere connettori, tutti gli altri membri del team potranno farlo, anche se le cassette postali vengono ospitate in locale.

<sup>6</sup> solo contatti nella cartella Contatti predefinita. L'accesso ad altri contatti o cartelle secondarie non è supportato.

<sup>7</sup> teams onora l'impostazione di [Outlook sul criterio delle cassette postali Web](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) configurata dagli amministratori del tenant per controllare se gli utenti possono modificare l'immagine del profilo. Se l'impostazione **-SetPhotoEnabled** è disattivata nel criterio, gli utenti non possono aggiungere, modificare o rimuovere l'immagine del profilo. Ad esempio, se un utente carica un'immagine del profilo approvata dal reparto IT o HR dell'organizzazione, non è necessaria alcuna azione. Tuttavia, se un utente carica un'immagine non appropriata, cambia l'immagine in base ai criteri interni dell'organizzazione.

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Requisiti per ottenere il massimo da Microsoft Teams

Microsoft teams funziona con diversi servizi Microsoft 365 e Office 365 per consentire agli utenti un'esperienza avanzata. Per supportare questa esperienza, è necessario abilitare determinate funzionalità o servizi e assegnare licenze.

- SharePoint Online è necessario per condividere e archiviare i file nelle conversazioni del team. Microsoft teams non supporta SharePoint locale.

- Gli utenti devono essere assegnati a una licenza di SharePoint Online se vogliono condividere file in chat. Se gli utenti non sono assegnati e abilitati con le licenze di SharePoint Online, non hanno lo spazio di archiviazione di OneDrive for business in Microsoft 365 o Office 365. La condivisione dei file continuerà a funzionare nei canali, ma gli utenti non potranno condividere file in chat senza spazio di archiviazione di OneDrive for business in Microsoft 365 o Office 365.

- Gli utenti devono essere abilitati per la creazione di gruppi di Microsoft 365 per creare team in Microsoft teams.

- Per consentire a Microsoft teams di lavorare con Exchange locale, è necessario configurare il nuovo protocollo di autenticazione di Exchange OAuth, preferibilmente eseguendo la procedura guidata ibrida di Exchange, come descritto in [configurare l'autenticazione OAuth tra le organizzazioni Exchange e Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help). Per consentire l'accesso al calendario per le cassette postali locali, è necessario che i team accedano all'organizzazione locale di Exchange sia per l'individuazione automatica che per EWS e che le cassette postali siano situate in Exchange 2016 CU3 o versioni successive. Per consentire agli utenti con cassette postali di Exchange locali di pianificare riunioni di team per conto di un altro utente, è necessario completare anche i passaggi 2 e 3 descritti in [configurare Integration e OAuth tra Skype for business online ed Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).

> [!NOTE]
> Il componente aggiuntivo Outlook teams può essere usato per pianificare una riunione di team per le cassette postali ospitate in Exchange locale. Tuttavia, la pianificazione di una riunione di team per conto di un altro utente con Exchange locale richiede Exchange 2016 CU3 e versioni successive e il nuovo protocollo di autenticazione di Exchange OAuth. Sia il delegato che il delegante devono avere una cassetta postale in Exchange locale.

> [!NOTE]
> Per l'integrazione di Exchange locale e teams, è necessario assegnare la licenza necessaria per l'utente sincronizzato di AAD.

> [!IMPORTANT]
> Se si disinstalla il client Skype for business dopo aver spostato un utente in modalità **solo teams** , la presenza potrebbe smettere di funzionare in Outlook e in altre app di Office. L’icona di presenza funziona bene in Teams. Per risolvere il problema, selezionare l'immagine del profilo nell'angolo in alto a destra di Microsoft teams e quindi selezionare **Impostazioni**. Nella scheda **generale** in **applicazione**Selezionare **registra teams come app di chat per Office (è necessario riavviare le applicazioni di Office)**. Dopo aver selezionato questa opzione, chiudere e riaprire tutte le app di Office, incluso Outlook. Dopo l'apertura di Outlook, le informazioni sulla presenza saranno disponibili.

## <a name="additional-considerations"></a>Considerazioni aggiuntive

Ecco alcuni aspetti aggiuntivi da considerare quando implementi Microsoft teams nell'organizzazione.

- In Microsoft teams, funzionalità per la sicurezza e la conformità come eDiscovery, ricerca contenuto, archiviazione e blocco legale migliorano il lavoro in ambienti Exchange Online e SharePoint Online. Per le conversazioni di canale, i messaggi vengono inseriti nel journal nella cassetta postale del gruppo in Exchange Online, dove sono disponibili per eDiscovery. Se SharePoint Online e OneDrive for business (con l'account aziendale o dell'Istituto di istruzione) sono abilitati nell'organizzazione e per gli utenti, queste caratteristiche di conformità sono disponibili anche per tutti i file all'interno di teams.

- Controllare e proteggere la configurazione dei criteri di conformità in teams e Exchange con l'accesso condizionale. Per altre informazioni [, vedere come funzionano i criteri di accesso condizionale per i team?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams) .

- Se l'organizzazione ha requisiti di conformità per verificare che tutte le discussioni delle riunioni siano individuabili, è consigliabile disabilitare le riunioni private se l'organizzatore ha una cassetta postale di Exchange locale.

- In una distribuzione ibrida di Exchange, il contenuto dei messaggi di chat è ricercabile indipendentemente dal fatto che i partecipanti alla chat abbiano una cassetta postale basata sul cloud o una cassetta postale locale. Per altre informazioni, vedere [ricerca di cassette postali basate su cloud per gli utenti locali](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Per informazioni su come cercare contenuto in teams, leggere [Ricerca contenuto nel centro conformità Microsoft 365](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

> [!TIP]
> Per informazioni su come usare Azure AD Connect per la sincronizzazione con Azure Active Directory, vedere [integrazione delle identità locali con Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=854600).

## <a name="requirements-for-on-premises-exchange-mailbox-user"></a>Requisiti per l'utente di cassette postali di Exchange locale

Se gli utenti desiderano pianificare una riunione di teams tramite Exchange, è necessario verificare quanto segue:

- Sia il delegato che il delegante devono avere una cassetta postale nel server Exchange.

- L'opzione individuazione automatica (autod) V2 è necessaria per consentire al servizio teams di eseguire un'individuazione non autenticata della cassetta postale dell'utente. Autod V2 è supportato in Exchange 2016 CU3 +.

- Il server di Exchange deve essere configurato con il server auth per EVOSTS. Questa operazione viene configurata automaticamente come parte della creazione guidata ibrida per Exchange (HWA).

    Se non si vuole eseguire HWA, è possibile creare manualmente il server auth per EVO STS sul server Exchange seguendo queste istruzioni [configurare l'autenticazione OAuth tra le organizzazioni Exchange e Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help). Tuttavia, ti consigliamo di usare HWA.

- Il server di Exchange deve avere un'applicazione partner configurata con un ID applicazione di **Skype for business online, 00000004-0000-0FF1-CE00-000000000000**. L'ID viene usato dal servizio pianificazione teams e da un account utente collegato con le proprietà seguenti:

  - Nascosto nella Rubrica di Exchange. È consigliabile nasconderla dalla Rubrica perché si tratta di un account utente disabilitato.

  - Assegnazione del ruolo di gestione di Exchange di **UserApplication**.

Per completare l'integrazione, seguire i passaggi 1-3 in [che modo è possibile configurare l'autenticazione OAuth tra le organizzazioni di Exchange e Exchange Online locale?](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help#how-do-you-configure-oauth-authentication-between-your-on-premises-exchange-and-exchange-online-organizations) Tieni presente che il passaggio 2 include l'assegnazione di ruolo per ArchiveApplication, che non è necessaria per la delega, ma è per l'archiviazione della chat online di SfB in una cassetta postale di Exchange.


## <a name="troubleshooting"></a>Risoluzione dei problemi

Per una guida alla risoluzione dei problemi completa nell'argomento, vedere risolvere i problemi di [interazione tra Microsoft teams ed Exchange Server](https://docs.microsoft.com/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue).
