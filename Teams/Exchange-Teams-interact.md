---
title: Interazione tra Exchange e Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Informazioni sulle funzionalità che coinvolgono Microsoft Teams e le diverse configurazioni di Exchange, ad esempio la creazione e l'aggiunta di team, la creazione di canali e altro ancora.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01335cce21a4550158f3c87da12c8a23166a39de
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624808"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Interazione tra Exchange e Microsoft Teams

> [!Tip]
> Per informazioni sull’interazione tra Teams e Azure Active Directory (AAD), i Gruppi di Microsoft 365, Exchange, SharePoint e OneDrive for Business, vedere la sessione: [Nozioni di base di Microsoft Teams](https://aka.ms/teams-foundations)

Per usufruire dell'esperienza completa di Teams, è necessario che ogni utente sia abilitato per la creazione di Gruppi di Microsoft 365, Exchange Online e SharePoint Online.

Le cassette postali di Exchange degli utenti possono essere ospitate online o in locale.

Gli utenti ospitati in Exchange Online o Exchange Dedicated vNext possono usare tutte le funzionalità di Teams. Possono creare e partecipare a team e canali, creare e visualizzare riunioni, chiamare e chattare, modificare le immagini del profilo, se i criteri delle cassette postali di Outlook sul web lo consentono, e aggiungere e configurare connettori, schede e bot. Per un elenco più completo delle funzionalità disponibili, vedere la tabella seguente.

Gli utenti ospitati in Exchange Online Dedicated (legacy) devono essere sincronizzati con Azure Active Directory in Microsoft 365 o Office 365. Possono creare e partecipare a team e canali, aggiungere e configurare schede e bot e usare le funzionalità di chat e chiamata. Tuttavia, non possono modificare le immagini del profilo, gestire le riunioni, accedere ai contatti di Outlook o gestire i connettori.

> [!IMPORTANT]
> Per l’integrazione con l’ambiente locale, si consiglia di disporre di una distribuzione ibrida classica completa di Exchange con Exchange Server 2016 o versioni successive. Il supporto ibrido moderno è limitato alla disponibilità e, ad esempio, non offre l’integrazione del calendario da Teams alle cassette postali locali. Per ulteriori informazioni sulla configurazione di una distribuzione ibrida, vedere [Distribuzioni ibride di Exchange Server](/exchange/exchange-hybrid).

Gli utenti con cassette postali ospitate in locale devono essere sincronizzati con Azure Active Directory. Possono usare tutte le funzionalità dello scenario precedente e, in aggiunta, possono anche gestire le riunioni se sono soddisfatti i requisiti elencati nella sezione [Requisiti per le cassette postali ospitate in locale](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises).

La tabella seguente costituisce un riferimento utile e rapido sulla disponibilità delle funzionalità in base all’ambiente di Exchange.

**Azioni supportate:**

| La cassetta postale dell'utente è ospitata in:                                       | eDiscovery         | Blocco&nbsp;a fini giudiziari    | Conservazione        | Gestione di team e canali | Creare e visualizzare riunioni in Teams | Modificare l’immagine del profilo | Cronologia delle chiamate | Gestire i contatti | Accedere ai contatti di Outlook | Messaggi vocali        | Aggiungere e configurare connettori | Aggiungere e configurare schede | Aggiungere e configurare bot |
|--------------------------------------------------------------------|--------------------|--------------------|------------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                | Sì <sup>1</sup>   | Sì <sup>1</sup>   | Sì              | Sì                   | Sì                               | Sì<sup>7</sup>             | Sì          | Sì             | Sì <sup>6</sup>        | Sì              | Sì                          | Sì                    | Sì                    |
| **Exchange Online Dedicated vNext**                                | Sì <sup>1</sup>   | Sì <sup>1</sup>   | Sì              | Sì                   | Sì                               | Sì<sup>7</sup>             | Sì          | Sì             | Sì <sup>6</sup>        | Sì              | Sì                          | Sì                    | Sì                    |
| **Exchange Online Dedicated – legacy** (sincronizzazione con Azure AD obbligatoria) | Sì <sup>1</sup>   | Sì <sup>1,2</sup> | Sì <sup>3</sup> | Sì                   | No                                | No                          | Sì          | Sì             | No                      | Sì <sup>4</sup> | Sì <sup>5</sup>             | Sì                    | Sì                    |
| **Exchange locale** (sincronizzazione con Azure AD)                        | Sì <sup>1,9</sup> | Sì <sup>1</sup>   | Sì <sup>3</sup> | Sì                   | Sì <sup>8</sup>                  | Sì<sup>10</sup>            | Sì          | Sì             | No                      | Sì <sup>4</sup> | Sì <sup>5</sup>             | Sì                    | Sì                    |

<sup>1</sup> eDiscovery e Blocco a fini giudiziari per la conformità nei messaggi di canale sono supportati per tutte le opzioni di hosting.

<sup>2</sup> I messaggi delle chat private di Teams non supportano ancora Blocco a fini giudiziari con questa opzione di hosting.

<sup>3</sup> La conservazione userà una cassetta postale shadow per consentire all’utente online di archiviare i messaggi.

<sup>4</sup> Gli utenti di Teams con una cassetta postale di Exchange locale possono usare i messaggi vocali con Teams e ricevere messaggi vocali in Outlook, ma questi non saranno disponibili per la visualizzazione o la riproduzione nel client di Teams.

<sup>5</sup> Se uno dei proprietari di un team può aggiungere connettori, anche tutti gli altri membri del team potranno farlo, anche se le loro cassette postali sono ospitate in locale.

<sup>6</sup> Solo i contatti nella cartella dei contatti predefinita. L'accesso ad altre cartelle o sottocartelle dei contatti non è supportato.

<sup>7</sup> Teams rispetta l'impostazione del [criterio per la cassetta postale di Outlook sul web](/powershell/module/exchange/client-access/set-owamailboxpolicy), che è configurata dagli amministratori del tenant per controllare se gli utenti possono modificare la propria immagine del profilo. Se l'impostazione **-SetPhotoEnabled** è disattivata nei criteri, gli utenti non possono aggiungere, modificare o rimuovere l'immagine del profilo, quindi l'immagine del profilo non verrà sincronizzata con i team se l'amministratore modifica la foto.

<sup>8</sup> È necessario soddisfare i requisiti elencati nella sezione [Requisiti per creare e visualizzare riunioni per le cassette postali ospitate in locale](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises).

<sup>9</sup> È necessario almeno una licenza Exchange Online piano 1. Per altre informazioni, vedere [Cercare Teams di chat per gli utenti locali.](/microsoft-365/compliance/search-cloud-based-mailboxes-for-on-premises-users)

<sup>10</sup> Gli utenti locali possono usare Teams per aggiornare l'immagine del profilo anche se il Outlook sul criterio cassetta postale `SetPhotoEnabled` Web è impostato su `false` .

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Requisiti per sfruttare al meglio Microsoft Teams

Microsoft Teams è compatibile con diversi servizi Microsoft 365 e Office 365 per offrire agli utenti un’esperienza completa. Per supportare l’esperienza, è necessario abilitare determinate funzionalità o servizi e assegnare le licenze.

- Gli utenti devono possedere una licenza di Exchange Online.

- SharePoint Online è necessario per condividere e archiviare file nelle conversazioni del team. Microsoft Teams non supporta le versioni locali di SharePoint.

- Gli utenti devono possedere una licenza di SharePoint Online se vogliono condividere file nelle chat. Se gli utenti non vengono assegnati e abilitati tramite licenze di SharePoint Online, non possono sfruttare l'archiviazione OneDrive for Business in Microsoft 365 o Office 365. La condivisone di file continuerà a funzionare nei canali, ma gli utenti non possono condividere i file nelle chat senza avere a disposizione l'archiviazione OneDrive for Business in Microsoft 365 o Office 365.

- Per creare team in Microsoft Teams, gli utenti devono essere abilitati per la creazione di gruppi di Microsoft 365.

  > [!IMPORTANT]
  > Se si disinstalla il client di Skype for Business dopo aver spostato un utente in modalità **Solo Teams**, l’icona di presenza potrebbe smettere di funzionare in Outlook e in altre app di Office. L’icona di presenza funziona bene in Teams. Per risolvere il problema, selezionare l’immagine del profilo nell'angolo in alto a destra di Microsoft Teams e quindi selezionare **Impostazioni**. Nella scheda **Generali** in **Applicazione**, selezionare **Registra Teams come l'applicazione di chat per Office (richiede il riavvio delle applicazioni di Office)**. Dopo aver selezionato questa opzione, chiudere e riaprire tutte le app di Office, incluso Outlook. Dopo l’apertura di Outlook, le informazioni sulla presenza saranno disponibili.

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>Requisiti per creare e visualizzare riunioni per le cassette postali ospitate in locale

Se le cassette postali sono ospitate in locale, per creare e visualizzare riunioni devono essere soddisfatti i requisiti seguenti:

- La licenza di Teams necessaria deve essere assegnata all’utente sincronizzato di Azure Active Directory.

- Gli utenti devono essere sincronizzati con Azure Active Directory. Per informazioni su come utilizzare Azure AD Connect per la sincronizzazione con Azure Active Directory, vedere [Documentazione sull'identità ibrida](/azure/active-directory/hybrid/).

- Le cassette postali sono ospitate nell'aggiornamento cumulativo 3 di Exchange Server 2016 o versioni successive.

- Individuazione automatica e Servizi Web Exchange vengono pubblicati esternamente.

- L’autenticazione OAuth è configurata preferibilmente tramite la procedura guidata di configurazione ibrida di Exchange che esegue una configurazione ibrida completa, classica o moderna. Se non si riesce a usare la procedura guidata di configurazione ibrida, configurare OAuth come descritto in [Configurare l’autenticazione OAuth tra le organizzazioni di Exchange ed Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

  > [!NOTE]
  > Exchange ritiene attendibile il token OAuth del servizio di Teams, denominato EvoSTS. Il passaggio 1 dovrebbe essere sufficiente, ma solo per EvoSTS. Per la ricerca della disponibilità nel calendario viene usato il servizio di controllo di accesso.

- La casella di controllo relativa alla funzionalità di distribuzione ibrida di Exchange in Azure AD Connect è selezionata. Per altre informazioni, vedere Exchange [writeback ibrido.](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized#exchange-hybrid-writeback)

- Per il supporto dell’app calendario e il componente aggiuntivo per Outlook di Teams per Mac, gli URL dei servizi Web di Exchange devono essere configurati come nomi SPN nel tenant Azure AD per l’entità servizio di Exchange. Questo passaggio viene eseguito con la procedura guidata di configurazione ibrida o seguendo i [passaggi manuali per l’autenticazione moderna ibrida](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad).

Per abilitare la delega del calendario per questi utenti:

- È anche necessario completare i passaggi come descritto in [Configurare l'integrazione e OAuth tra Skype for Business Online e Exchange Server;](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises) questi passaggi forniranno all'Teams di pianificazione le autorizzazioni necessarie per confermare le autorizzazioni delegato.
 
  > [!NOTE]
  > Il passaggio 2 include l'assegnazione del ruolo ArchiveApplication, che non è obbligatorio per la delega.

- Il Teams pianificazione per Outlook richiede Exchange 2013 CU19 o versione successiva quando si pianifica una riunione per conto di un altro utente. Questo permette di supportare l’individuazione non autenticata della cassetta postale da parte del servizio per controllare le autorizzazioni di delega rispetto alla cassetta postale del delegante. La posizione del delegato e del delegante può essere Exchange 2013 o versioni successive oppure Exchange Online, ma l'individuazione automatica deve risolversi in Exchange 2013 CU19 o versioni successive.

## <a name="additional-considerations"></a>Considerazioni aggiuntive

Di seguito sono riportate alcune considerazioni aggiuntive su come implementare Microsoft Teams nell'organizzazione.

- In Microsoft Teams funzionalità di sicurezza e conformità come eDiscovery, Ricerca contenuto, l’archiviazione e il blocco a fini giudiziari offrono risultati migliori negli ambienti di Exchange Online e SharePoint Online. Per le conversazioni di canale, i messaggi vengono inseriti nel journal nella cassetta postale di gruppo di Exchange Online, dove sono disponibili per eDiscovery. Se SharePoint Online e OneDrive for Business (con account aziendale o dell’istituto di istruzione) sono abilitati per l'intera organizzazione e per tutti gli utenti, queste funzionalità di conformità sono disponibili anche per tutti i file all’interno di Teams.

- Controllare e proteggere la configurazione dei criteri di conformità in Teams ed Exchange con l’accesso condizionale. Per ulteriori informazioni, vedere [Come funzionano i criteri di accesso condizionale per Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)

- Se l’organizzazione possiede dei requisiti di conformità per garantire che tutte le discussioni delle riunioni siano individuabili, è consigliabile disabilitare le riunioni private se l’organizzatore dispone di una cassetta postale di Exchange locale. Per ulteriori informazioni, vedere [Consentire la pianificazione di riunioni private](./meeting-policies-in-teams-general.md#allow-scheduling-private-meetings).

- In una distribuzione ibrida di Exchange, il contenuto dei messaggi di chat è disponibile per la ricerca, indipendentemente dal fatto che i partecipanti alla chat abbiano una cassetta postale basata sul cloud o una cassetta postale locale. Per ulteriori informazioni, consultare [Ricerca in cassette postali basate sul cloud per gli utenti locali](/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Per informazioni sulla ricerca di contenuto in Teams, consultare [Ricerca contenuto nel Centro conformità di Microsoft 365](/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

- Per lo stato presenza, Microsoft Teams deve verificare se la cassetta postale è ospitata in Exchange Online o in locale. Il servizio stabilisce quindi il percorso di accesso alla cassetta postale. Per abilitare il servizio Teams per controllare il percorso della cassetta postale attraverso la chiamata API REST al servizio Exchange Online, è necessario implementare un ambiente ibrido di Exchange eseguendo la configurazione ibrida guidata di Exchange, come descritto in [Creare una distribuzione ibrida con la procedura guidata di configurazione ibrida](/exchange/hybrid-deployment/deploy-hybrid).

## <a name="troubleshooting"></a>Risoluzione dei problemi

Per una guida completa alla risoluzione dei problemi sull’argomento, vedere [Risolvere i problemi di interazione tra Microsoft Teams ed Exchange Server](/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue).
