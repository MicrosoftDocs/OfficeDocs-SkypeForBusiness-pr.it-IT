---
title: Gestire le impostazioni per l'organizzazione
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ritikag
search.appverid: MET150
description: Informazioni su come attivare o disattivare le impostazioni di Microsoft Teams a livello di organizzazione, tra cui le app, l'accesso esterno, l'accesso guest, le impostazioni di Teams e le preferenze di aggiornamento di Teams.
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.teamssettings.targetingintro
- ms.teamsadmincenter.teamssettings.overview
- NewAdminCenter_Update
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a57c54fcd90787048cc357a71296f942cacdef43
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583445"
---
# <a name="manage-microsoft-teams-settings-for-your-organization"></a>Gestire le impostazioni di Microsoft Teams per l'organizzazione

## <a name="teams-apps-settings-in-the-microsoft-teams-admin-center"></a>Impostazioni delle app di Teams nell'interfaccia di amministrazione di Microsoft Teams

È possibile gestire le app per l'organizzazione nella sezione **App di Teams** dell'[interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com). Ad esempio, è possibile impostare criteri per controllare quali app sono disponibili per l'intera organizzazione o per specifici utenti di Teams, oltre che personalizzare Teams bloccando in alto le app più importanti per gli utenti.

Per altre informazioni, vedere [Impostazioni di amministrazione per le app in Teams](admin-settings.md).  

## <a name="teams-org-wide-settings-in-the-microsoft-teams-admin-center"></a>Impostazioni di Teams a livello di organizzazione nell'interfaccia di amministrazione di Microsoft Teams

Nell'interfaccia di amministrazione di Microsoft Teams è possibile controllare le impostazioni degli utenti a livello di organizzazione. Per modificare le impostazioni a livello di organizzazione, passare all'interfaccia di amministrazione di Microsoft Teams e selezionare **Impostazioni organizzazione**. È possibile configurare le impostazioni seguenti.

### <a name="external-access"></a>Accesso esterno

L'**accesso esterno** consente agli utenti di Teams e Skype for Business di comunicare con utenti esterni all'organizzazione o al dominio. Per configurare l'accesso esterno, passare alla sezione su come [consentire agli utenti di Teams di chattare e comunicare con gli utenti di un'altra organizzazione di Teams](let-your-teams-users-communicate-with-other-people.md).

Per aggiungere o bloccare un dominio:

1. Selezionare **Aggiungi un dominio**.
2. Nel riquadro Aggiungi un dominio immettere il nome del dominio e fare clic sulla barra spaziatrice per salvare il nome.
3. Selezionare **Consentito** o **Bloccato**.
4. Selezionare **Fine** per salvare le modifiche. 

### <a name="guest-access"></a>Accesso guest

L'**accesso guest** in Microsoft Teams consente ai team dell'organizzazione di collaborare con persone esterne all'organizzazione concedendo loro l'accesso a team e canali. Chiunque abbia un account di posta elettronica aziendale o personale, come Outlook, Gmail o altri, può partecipare come guest in Teams e avere accesso completo a chat, riunioni e file del team. Per altre informazioni, vedere [Accesso guest in Microsoft Teams](guest-access.md).

### <a name="teams-settings"></a>Impostazioni di Teams

Nelle **Impostazioni di Teams** è possibile configurare le funzionalità per i team, tra cui notifiche e feed, integrazione e-mail, opzioni di archiviazione nel cloud e dispositivi.

#### <a name="notifications-and-feeds"></a>Notifiche e feed

Qui è possibile controllare se i feed suggeriti vengono visualizzati nel feed attività dell'utente in Teams. Per altre informazioni sul feed attività, vedere [Esplorare il feed Attività in Teams](https://support.office.com/article/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56).

#### <a name="tagging"></a>Aggiunta di tag

I tag consentono agli utenti di comunicare con un sottoinsieme di persone in un team. I tag possono essere aggiunti a uno o più membri del team. Dopo l'aggiunta di un tag, questo può essere usato all'interno di @menzioni da qualsiasi persona del team in un post del canale per comunicare solo con le persone a cui è assegnato il tag. Usare queste impostazioni per controllare chi può aggiungere tag e il modo in cui i tag vengono usati nell'organizzazione. Per altre informazioni, vedere [Gestire i tag in Teams](manage-tags.md).

#### <a name="email-integration"></a>Integrazione di e-mail

Attivare questa funzionalità per consentire agli utenti di inviare messaggi di posta elettronica a un canale in Teams usando l'indirizzo e-mail del canale. Gli utenti possono eseguire questa operazione per qualsiasi canale appartenente a un team di cui sono proprietari. Gli utenti possono anche inviare e-mail a qualsiasi canale in un team in cui è attivata l'aggiunta di connettori per i membri del team. Per attivare l'integrazione e-mail, assicurarsi che l'opzione **Consenti agli utenti di inviare e-mail a un indirizzo e-mail del canale** sia **Attivata**.

#### <a name="files"></a>File

Qui è possibile attivare o disattivare la condivisione di file e le opzioni di archiviazione di file nel cloud.

Gli utenti possono caricare e condividere file dai servizi di archiviazione cloud in canali e chat di Teams. Le opzioni di archiviazione cloud di Teams attualmente includono Dropbox, Box, ShareFile, Google Drive e Egnyte (presto disponibile). Attivare l'opzione per i provider di archiviazione cloud che l'organizzazione vuole usare.

#### <a name="organization"></a>Organizzazione

Qui è possibile attivare la scheda **Organizzazione**, che mostra l'organigramma dettagliato per l'organizzazione dell'utente. Per altre informazioni, vedere [Usare la scheda Organizzazione in Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).

#### <a name="devices"></a>Dispositivi

Queste impostazioni controllano il comportamento dell'account di risorsa per i dispositivi Surface Hub che partecipano alle riunioni di Microsoft Teams. Usare queste impostazioni per configurare i requisiti di autenticazione, richiedere un PIN contenuto e attivare gli account di risorsa Surface Hub per inviare messaggi.

- **Richiedi una forma di autenticazione secondaria per accedere ai contenuti della riunione** - Selezionare il livello di accesso che gli utenti hanno quando immettono il PIN contenuto.
- **Imposta il PIN contenuto** - Richiedere agli utenti di immettere il PIN per impedire l'accesso non autorizzato ai documenti. Questo impedisce a un utente non autorizzato di partecipare alle riunioni in programma e di esplorare gli allegati.
- **Gli account delle risorse possono inviare messaggi** - **Attivare** questa impostazione per consentire l'invio dei messaggi dall'account di risorsa Surface Hub.

#### <a name="search-by-name"></a>Cerca per nome

La ricerca nella directory con ambito di Microsoft Teams usa i criteri rubrica di Exchange per consentire alle organizzazioni di creare confini virtuali che controllano il modo in cui gli utenti possono trovare e comunicare con altri utenti dell'organizzazione. Può essere utile usare la ricerca nella directory con ambito in situazioni come queste:

- L'organizzazione ha più società all'interno del tenant che si vogliono mantenere separate. 
- L'istituto di istruzione vuole limitare le chat tra docenti e studenti. 

**Attivare** questa impostazione per abilitare le ricerche nella directory con ambito.

### <a name="teams-upgrade"></a>Aggiornamento di Teams

È possibile usare queste impostazioni per configurare il modo in cui gli utenti verranno aggiornati da Skype for Business a Microsoft Teams. 

#### <a name="coexistence-mode"></a>Modalità di coesistenza
È possibile specificare una modalità di coesistenza: 

- **Solo Teams**
- **Isole** - Teams e Skype for Business coesisteranno
- **Solo Skype for Business**
- **Skype for Business con la collaborazione di Teams** - Gli utenti ricevono chiamate, messaggi di chat e pianificano riunioni in Skype for Business, ma usano Teams per la collaborazione di gruppo.
- **Skype for Business con le riunioni e la collaborazione di Teams** - Gli utenti ricevono chiamate e messaggi di chat in Skype for Business, ma usano Teams per la collaborazione di gruppo e per pianificare riunioni.

La modalità di coesistenza scelta determina l'instradamento  delle chiamate e delle chat in arrivo e l'app impiegata dall'utente per avviare chat e chiamate o per pianificare riunioni. Per altre informazioni sulle modalità di coesistenza, passare a [Informazioni sulla coesistenza e l'interoperabilità di Microsoft Teams e Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="app-preferences"></a>Preferenze app

Qui è possibile scegliere l'app che gli utenti useranno per partecipare alle riunioni di Skype for Business (Skype for Business o [App Riunioni Skype](https://support.office.com/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). Questa impostazione non dipende dall'impostazione della modalità di coesistenza.


#### <a name="network-planner"></a>Network Planner

Network Planner consente di determinare e organizzare i requisiti di rete per la connessione degli utenti di Teams nell'organizzazione.  Vedere l'articolo su come [Usare Network Planner per Microsoft Teams](https://docs.microsoft.com/microsoftteams/network-planner).

È anche possibile selezionare l'opzione "Scarica l'app di Teams in background per gli utenti Skype for Business".  Per impostazione predefinita, questa opzione è attivata. Quando l'opzione è attivata, l'app Teams verrà scaricata in background per gli utenti che eseguono l'app Skype for Business in PC Windows. Questo accade si verifica se la modalità di coesistenza dell'utente è Solo Teams o se nell'app Skype for Business è abilitata una notifica di aggiornamento in sospeso.


## <a name="how-can-i-tell-which-features-are-available"></a>Come si fa a determinare quali funzionalità sono disponibili?

Per informazioni sulle nuove funzionalità di Teams, vedere la [Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams). Per altre informazioni sulle funzionalità nuove e imminenti, vedere la pagina [Novità](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) di Teams e il [blog di Microsoft Teams nella Tech Community](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531). 

## <a name="more-information"></a>Altre informazioni

Per informazioni sui ruoli che possono svolgere funzioni amministrative, vedere [Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](using-admin-roles.md).
