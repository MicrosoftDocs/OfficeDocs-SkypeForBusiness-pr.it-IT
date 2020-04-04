---
title: Configurare gli eventi dinamici in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Configurare Live per gli eventi in teams, inclusa la configurazione della rete, l'assegnazione di licenze, l'abilitazione delle caratteristiche degli eventi dinamici e la pianificazione e la distribuzione di soluzioni video.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ae30fdb824c62027d1a704435e80df2a9abf1f85
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140565"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Configurare gli eventi dinamici in Microsoft Teams

Quando si sta configurando per gli eventi dinamici, è necessario eseguire diversi passaggi.

## <a name="step-1-set-up-your-network-for-live-events-in-teams"></a>Passaggio 1: configurare la rete per gli eventi dinamici in teams
Gli eventi dinamici prodotti in teams richiedono [la preparazione della rete dell'organizzazione per i team](https://docs.microsoft.com/microsoftteams/prepare-network).  

## <a name="step-2-get-and-assign-licenses"></a>Passo 2: Ottenere e assegnare licenze
Assicurati di avere le assegnazioni di licenze corrette per [chi può creare e pianificare eventi live](plan-for-teams-live-events.md#who-can-create-and-schedule-live-events) e [chi può guardare gli eventi live](plan-for-teams-live-events.md#who-can-watch-live-events).

## <a name="step-3-set-up-live-events-policies"></a>Passaggio 3: configurare i criteri degli eventi dinamici
I criteri per gli eventi dinamici vengono usati per controllare chi nell'organizzazione può contenere eventi dinamici e le caratteristiche disponibili negli eventi creati. È possibile usare i criteri predefiniti o creare uno o più criteri personalizzati per eventi live. Dopo aver creato un criterio personalizzato, assegnarlo a un utente o a un gruppo di utenti dell'organizzazione.

> [!NOTE]
> Gli utenti dell'organizzazione otterranno i criteri globali a meno che non si creino e si assegnano criteri personalizzati. Per impostazione predefinita, nel criterio globale la pianificazione degli eventi dinamici è abilitata per gli utenti di Team, le didascalie e i sottotitoli in tempo reale (trascrizione) è disattivato, tutti gli membri dell'organizzazione possono partecipare agli eventi dinamici e l'impostazione di registrazione è impostata su registra sempre. 

### <a name="create-or-edit-a-live-events-policy"></a>Creare o modificare un criterio eventi dinamici
<a name="bkcreatepolicy"> </a>

**![Icona che mostra il logo](../media/teams-logo-30x30.png) di Microsoft teams con l'interfaccia di amministrazione di Microsoft Teams**

1. Nella barra di spostamento sinistra, vai a **riunioni** > **Live Events Policy**. 
2. Esegui una delle operazioni seguenti:
- Se si vogliono modificare i criteri predefiniti esistenti, scegliere **globale (impostazione predefinita a livello di organizzazione)**. 
- Se si vuole creare un nuovo criterio personalizzato, scegliere **nuovo criterio**. 
- Se si vuole modificare un criterio personalizzato, selezionare il criterio e quindi scegliere **modifica**. 

    Ecco le impostazioni che è possibile modificare per adattarsi alle esigenze dell'organizzazione.

    ![Schermata delle impostazioni dei criteri di eventi dinamici](../media/teams-live-events-policies.png "Screenshot delle impostazioni dei criteri di eventi dinamici nell'interfaccia di amministrazione di Microsoft Teams") 

|Impostazione  |Descrizione  |
|---------|---------|
|**Titolo**     |Questo è il titolo del criterio visualizzato nella pagina Criteri eventi dinamici. Non può essere maggiore di 64 caratteri o avere caratteri speciali.          |
|**Descrizione**    |Usare questa caratteristica per aggiungere una descrizione amichevole per il criterio.         |
|**Consenti pianificazione**     |Questa operazione consente agli utenti dell'organizzazione di creare e pianificare eventi dinamici in teams. È importante sapere che se si vuole che gli utenti programmino un evento dinamico prodotto con un'app o un dispositivo esterno, è necessario eseguire ulteriori operazioni. Per altre informazioni, vedere [consentire agli utenti di pianificare gli eventi prodotti con un'app o un dispositivo esterno](#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).     |
|**Consentire la trascrizione per i partecipanti** |Questa impostazione può essere applicata solo agli eventi prodotti in teams. Questa operazione consente ai partecipanti agli eventi live di visualizzare le didascalie e i sottotitoli dinamici durante l'evento.         |
|**Chi può partecipare a eventi live pianificati**    |Scegliere una delle opzioni seguenti.<br><br>**Tutti gli utenti** Gli utenti possono creare eventi dinamici che tutti, incluse le persone esterne all'organizzazione, possono partecipare. Questa impostazione Abilita il tipo di autorizzazione **pubblica** in teams quando un utente pianifica un evento dinamico.<br> **Tutti gli utenti dell'organizzazione** Gli utenti possono creare eventi dinamici che gli utenti dell'organizzazione, inclusi quelli [Guest](../add-guests.md) aggiunti alla propria organizzazione, possono partecipare. Gli utenti non possono creare eventi dinamici frequentati da utenti anonimi. Questa impostazione Abilita il tipo di autorizzazione a **livello di organizzazione** in teams quando un utente pianifica un evento dinamico.<br> **Utenti o gruppi specifici** Gli utenti possono creare eventi dinamici che possono essere presenti solo in utenti o gruppi specifici dell'organizzazione. Gli utenti non possono creare eventi dinamici a cui partecipano tutti gli utenti dell'organizzazione o di persone anonime. Questa impostazione Abilita il tipo di autorizzazione **utenti e gruppi** in teams quando un utente pianifica un evento dinamico.       |
|**Impostazione di registrazione**  <br>     | Questa impostazione può essere applicata solo agli eventi prodotti in teams. Scegliere una delle opzioni seguenti. <br><br> **Registrare sempre** Gli eventi dinamici creati dagli utenti vengono sempre registrati. Al termine dell'evento, i membri del team di eventi possono scaricare la registrazione e i partecipanti possono guardare l'evento. <br> **Non registrare mai** Gli eventi dinamici creati dagli utenti non vengono mai registrati. <br>L' **organizzatore può registrare o meno** Gli utenti possono decidere se registrare l'evento Live. Se è registrata, dopo che l'evento è terminato, i membri del team di eventi possono scaricare la registrazione e i partecipanti possono guardare l'evento.      

Puoi eseguire questa operazione anche usando Windows PowerShell. Per altre informazioni, vedere [usare PowerShell per impostare i criteri degli eventi dinamici in teams](set-teams-live-events-policies-using-powershell.md). 

### <a name="assign-a-live-events-policy-to-users"></a>Assegnare un criterio eventi dinamici agli utenti 

Se è stato creato un criterio eventi dinamici personalizzati, assegnarlo agli utenti affinché il criterio sia attivo. 

![Icona che mostra il logo di Microsoft Teams](../media/teams-logo-30x30.png) Uso dell'interfaccia di amministrazione di Microsoft Teams

1. Nella barra di spostamento sinistra passa a **utenti**e quindi seleziona l'utente.
2. Accanto a **criteri assegnati**scegliere **modifica**. 
3. Selezionare il criterio eventi attivi che si desidera assegnare e quindi scegliere **Salva**. 

È anche possibile assegnare un criterio eventi dinamici a uno o più utenti, come indicato di seguito:

![Icona che mostra il logo di Microsoft Teams](../media/teams-logo-30x30.png) Uso dell'interfaccia di amministrazione di Microsoft Teams

1. Accedere ai **Meetings** > **criteri eventi live**riunioni.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio.
3. Scegliere **Gestisci utenti**.
4. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
5. Al termine dell'aggiunta di utenti, selezionare **Salva**.
 

### <a name="enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device"></a>Consentire agli utenti di pianificare gli eventi prodotti con un'app o un dispositivo esterno

Per consentire agli utenti di pianificare gli eventi prodotti con un'app o un dispositivo esterno, è necessario eseguire anche le operazioni seguenti:

1. Abilitare Microsoft Stream per gli utenti dell'organizzazione. Stream è disponibile come parte delle sottoscrizioni di Office 365 idonee o come servizio autonomo. Stream non è incluso nei piani Business Essentials o Business Premium. Per altre informazioni, Vedi [Panoramica sulle licenze di Stream](https://docs.microsoft.com/stream/license-overview) .

      Leggi altre informazioni su come [assegnare licenze agli utenti in Office 365 in](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) modo che gli utenti possano accedere a Stream. Assicurarsi che Stream non sia bloccato per gli utenti come definito in [questo articolo](https://docs.microsoft.com/stream/disable-user-organization).

2. Assicurarsi che gli utenti abbiano le autorizzazioni di creazione di eventi dinamici in Stream. Per impostazione predefinita, gli amministratori possono creare eventi con un'app o un dispositivo esterno. L'amministratore del flusso può [abilitare altri utenti per la creazione di eventi dinamici](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) in Stream.  

3. Assicurarsi che gli organizzatori di eventi dinamici abbiano acconsentito ai criteri aziendali impostati dall'amministratore del flusso. Se un amministratore del flusso ha [configurato un criterio per le linee guida della società](https://docs.microsoft.com/stream/company-policy-and-consent) e richiede ai dipendenti di accettare questo criterio prima di salvare il contenuto, gli utenti devono farlo prima di creare un evento dinamico (con un'app o un dispositivo esterno) in teams. Prima di implementare la funzionalità eventi dinamici nell'organizzazione, assicurati che gli utenti che vogliono creare questi eventi dinamici abbiano acconsentito al criterio. 

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>Passaggio 4: configurare una soluzione di distribuzione video per eventi dinamici in teams
La riproduzione dei video di eventi dinamici usa il flusso di bitrate adattivo (ABR) ma è uno Stream unicast, che indica che ogni visualizzatore sta ottenendo il proprio flusso video da Internet. Per gli eventi o i video in tempo reale inviati a parti di grandi dimensioni dell'organizzazione, potrebbe essere presente una quantità significativa di larghezza di banda Internet usata dagli utenti. Per le organizzazioni che vogliono ridurre il traffico Internet per gli eventi dinamici, le soluzioni di eventi dinamici sono integrate con i partner di recapito video attendibili di Microsoft che offrono reti SDNs (software defined Networks Delivery Network) o eCDNs. Queste piattaforme SDN/eCDN consentono alle organizzazioni di ottimizzare la larghezza di banda della rete senza sacrificare le esperienze di visualizzazione degli utenti finali. I nostri partner possono aiutare a consentire una distribuzione video più scalabile ed efficiente in tutta la rete aziendale.

**Acquistare e configurare la soluzione all'esterno dei team** Ottieni assistenza per gli esperti con il ridimensionamento del recapito video sfruttando i partner di recapito video attendibili di Microsoft. Prima di consentire l'uso di un provider di recapito video con teams, è necessario acquistare e configurare la soluzione SDN/eCDN esterna e separata da teams.

Le soluzioni SDN/eCDN seguenti sono preintegrate e possono essere configurate per l'uso con Stream.

- **Hive streaming** offre una soluzione semplice e potente per la distribuzione di video aziendali Live e su richiesta. Hive è una soluzione basata sul software che non richiede hardware o larghezza di banda aggiuntivi e offre un modo sicuro per consentire a migliaia di videospettatori simultanei senza impatto sulla rete. Per i clienti che cercano di comprendere il video di impatto che sta avendo sulla loro rete prima di acquistare una soluzione SDN/eCDN, hive streaming offre anche una soluzione di analisi basata su browser per i clienti Microsoft. [Altre informazioni](https://www.hivestreaming.com/partners/integration-partners/microsoft/).
 
- **Kollective** è una piattaforma di distribuzione di peering intelligente basata su cloud che sfrutta l'infrastruttura di rete esistente per distribuire contenuto, in molte forme, (video in streaming live, video su richiesta, aggiornamenti software, patch di sicurezza e così via) più velocemente, in modo più affidabile e con meno larghezza di banda. La nostra piattaforma sicura è considerata attendibile dalle più grandi istituzioni finanziarie del mondo e senza hardware aggiuntivo, la configurazione e la manutenzione sono semplici. [Altre informazioni](https://kollective.com/microsoft-pilot/).
 
- **Ramp OmniCache** offre la distribuzione di rete di nuova generazione e assicura il recapito continuo dei contenuti video in WAN globali, aiutando i produttori di eventi a ottimizzare la larghezza di banda della rete e supportare trasmissioni di eventi live di successo e streaming su richiesta. Il supporto per la rampa OmniCache per gli eventi dinamici prodotti in teams sarà disponibile a breve. [Altre informazioni](http://www.ramp.com). 
 
> [!NOTE] 
> La soluzione scelta di SDN o eCDN è soggetta alle **condizioni di servizio e alla politica di privacy del provider**di terze parti, che disciplinerà l'uso della soluzione del provider. L'uso della soluzione del provider non sarà soggetto alle condizioni di contratto multilicenza Microsoft o ai servizi online. Se non si accettano i termini del **provider di terze parti**, non abilitare la soluzione in teams. 

Dopo aver configurato la soluzione SDN o eCDN, si è pronti per configurare il provider per gli eventi dinamici in teams. 

## <a name="next-steps"></a>Passaggi successivi
Vedere [configurare le impostazioni degli eventi dinamici in teams](configure-teams-live-events.md).

### <a name="related-topics"></a>Argomenti correlati
- [Cosa sono gli eventi live di Teams?](what-are-teams-live-events.md)
- [Pianificare gli eventi live di Teams](plan-for-teams-live-events.md)
- [Configurare le impostazioni degli eventi dinamici in teams](configure-teams-live-events.md)
