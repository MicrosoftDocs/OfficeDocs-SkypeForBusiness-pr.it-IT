---
title: Pianificare Microsoft 365 Government-distribuzioni di GCC-Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Linee guida per i professionisti IT per guidare le distribuzioni di Office 365 in entità che gestiscono i dati soggetti alla regolamentazione del governo degli Stati Uniti
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a167c8a6df85b5d3d861f42ce40f67e845709a77
ms.sourcegitcommit: 332817f49ec1e6767334fdd4c2ec3f791020a26c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2019
ms.locfileid: "36767124"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Pianificare le distribuzioni di Microsoft 365 Government-GCC

Questa guida è per i professionisti IT che guidano le distribuzioni di Office 365 in Stati Uniti, enti governativi federali, statali, locali, tribali o territoriali o altre entità che gestiscono i dati soggetti alle normative governative e ai requisiti, dove l'uso di Microsoft 365 Government-GCC è appropriato per soddisfare questi requisiti.

> [!NOTE]
> Se l'organizzazione ha già incontrato i requisiti di ammissibilità per il governo di Microsoft 365 e per i quali è stata accettata l'applicazione, è possibile ignorare i passaggi 1 e 2 e passare direttamente al passaggio 3. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Passaggio 1. Determinare se l'organizzazione ha bisogno di Microsoft 365 Government-GCC e soddisfa i requisiti di ammissibilità. 

L'ambiente Government-GCC Microsoft 365 offre la conformità con i requisiti del governo degli Stati Uniti per i servizi cloud, tra cui FedRAMP moderati e i requisiti per la giustizia penale e i sistemi di informazione federale delle imposte (CJI e FTI).

Oltre a sfruttare le caratteristiche e le funzionalità di Office 365, le organizzazioni traggono vantaggio dalle caratteristiche seguenti che sono univoche per Microsoft 365 Government-GCC:

-   Il contenuto del cliente dell'organizzazione viene separato logicamente dal contenuto dei clienti nei servizi commerciali di Office 365 da Microsoft.
-   Il contenuto del cliente dell'organizzazione è archiviato negli Stati Uniti.
-   L'accesso al contenuto del cliente dell'organizzazione è limitato al personale Microsoft schermato.
-   Microsoft 365 Government-GCC è conforme alle certificazioni e alle accreditazioni necessarie per i clienti del settore pubblico.

Per altre informazioni sull'offerta di Microsoft 365 Government-GCC per i clienti del governo degli Stati Uniti, vedere [piani governativi di Office 365](https://products.office.com/government/compare-office-365-government-plans), inclusi i [requisiti di ammissibilità](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

La [Descrizione del servizio governativo degli Stati Uniti di Office 365](https://technet.microsoft.com/library/mt774581.aspx) descrive i vantaggi della piattaforma, che sono centrati sui requisiti di conformità delle riunioni negli Stati Uniti.

> [!Tip]
> Potrebbe essere necessario trasferire le tabelle di informazioni nella descrizione del servizio in una cartella di lavoro di Excel e aggiungere due colonne: **rilevanti per la mia organizzazione y/n** e **soddisfano le esigenze dell'organizzazione y/n**. È quindi possibile rivedere questo elenco con i colleghi per verificare che il servizio soddisfi le esigenze dell'organizzazione.

|    |     |
|-----------|------------|
| ![Icona che descrive i punti di decisione](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere se Microsoft 365 Government-GCC è appropriato per l'organizzazione.</li><li>Verificare che l'organizzazione soddisfi i requisiti di ammissibilità.</li></ul> |

> [!Note]
> Microsoft 365 Government-GCC è disponibile solo negli Stati Uniti. I clienti di enti pubblici non-americani possono scegliere tra diversi [piani governativi di Office 365](https://products.office.com/en/government/compare-office-365-government-plans).


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Passaggio 2. Richiedi Microsoft 365 Government-GCC

Dopo aver deciso che il servizio è appropriato per l'organizzazione, avviare il processo di [applicazione di questo servizio](https://products.office.com/government/eligibility-validation).

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Passaggio 3. Informazioni sulle impostazioni di sicurezza predefinite di Microsoft 365-GCC.

È consigliabile richiedere tempo per esaminare attentamente le impostazioni di [amministratore e sicurezza](enable-features-office-365.md) prima di modificarle e prendere in considerazione gli impatti sulla conformità prima di apportare modifiche alle impostazioni di sicurezza predefinite.

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto decisionale|<ul><li>Decidere se modificare le impostazioni di sicurezza di Microsoft 365 Government-GCC predefinite, risolvendo in primo luogo l'impatto delle eventuali modifiche apportate.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Passaggio 4. Informazioni sulle funzionalità attualmente non disponibili o disabilitate per impostazione predefinita. 

Per soddisfare le esigenze dei clienti del cloud governativo, esistono alcune differenze tra i piani di Microsoft 365 Government-GCC e Enterprise. Fare riferimento alla tabella seguente per vedere quali funzionalità sono disponibili.

|                             | Funzionalità                     | GCC            |
|-----------------------------|-----------------------------|----------------|
| Base | Accesso | Disponibili |
| | Presenza | Disponibili |
| | Presenza unificata (Skype for business e teams Unified) | Disponibili |
| Attività | Feed | Disponibili |
|  | Attività personali | Disponibili |
| Chat | Conversazione | Disponibili |
| | File | Disponibili |
| | Organigramma | Disponibili |
| | Attività | Disponibili |
| | Interoperabilità (1:1 Teams-chat Skype for business) | Disponibili |
| Squadre | Messaggio di canale | Disponibili |
| | File di canale | Disponibili |
| | Scheda OneNote | Nell'arretrato governativo |
| | Inviare un canale tramite posta elettronica | Non disponibile |
| | Aggiungi membro | Disponibili |
| | Accesso Guest | Disponibili |
|  Riunioni | Pianificare una riunione | Disponibili |
| | Partecipare a una riunione | Disponibili |
| | Riunione VoIP | Disponibili |
| | Condivisione desktop | Disponibili |
| | Dare e prendere il controllo della condivisione | Disponibili |
| | Connettersi da una sala riunioni | Disponibili |
| | Join anonimo | Disponibili |
| | Registrazione cloud | Disponibili |
| | Note riunione | Disponibili |
| | Eventi dinamici | Disponibili |
| | Riunioni federate | Disponibili |
| | Supporto per Surface Hub | Non disponibile |
| Chiamate | Contatti | Disponibili |
| | Storia | Disponibili |
| | Casella vocale | Disponibili |
| | Chiamata VoIP | Disponibili |
| | Skype for business-teams Calling | Disponibili |
| | Piani per chiamate | Disponibili |
| | Servizi di audioconferenza (per consentire ai partecipanti alla riunione di partecipare tramite PSTN) | Disponibili |
| | Routing diretto di Microsoft Phone System | Disponibili |
| | Sala di attesa per i chiamanti PSTN | Disponibili |
| | Coda di chiamata | Disponibili |
| | Supporto di boss e delegati | Disponibili |
| | Trasferimento consultivo e sicuro | Disponibili |
| | Non disturbare l'innovazione | Disponibili |
| | Anello distintivo | Disponibili |
| | 1:1 per raggruppare le escalation delle chiamate con team, Skype for business e partecipanti PSTN | Disponibili |
| | Inoltra al gruppo | Disponibili |
| | Trasferimento a chiamata PSTN | Disponibili |
| | Piani per chiamate di emergenza | Disponibili |
| | Supporto per i telefoni SIP certificati esistenti | Disponibili |
| | USB HID | Disponibili |
| | eDiscovery per le chiamate e le riunioni | Disponibili |
| | Operatore automatico organizzazione | Disponibili |
| | Supporto per Skype consumer-teams Call | Disponibili |
| File | Recente | Disponibili |
| | Microsoft Teams | Disponibili |
| Negozio | App Store | Nell'arretrato governativo |
| Ricerca | Messaggi | Disponibili |
| | Persone | Disponibili |
| | File | Disponibili |
| | Comandi barra | Disponibili |
| Conformità | Ricerca di contenuto di conformità | Disponibili |
| | Conservazione | Disponibili |
| | Ricerca nel log di controllo | Disponibili |
| | Blocco legale | Disponibili |
| | eDiscovery | Disponibili |

> [!Note]

> Una volta che altri carichi di lavoro saranno completamente disponibili nel cloud GCC, questi saranno resi disponibili in teams quando verrà completato il completamento di tutte le operazioni di integrazione.


|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto decisionale|<ul><li>Decidere se il set di funzionalità teams soddisfa le esigenze dell'organizzazione.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Passaggio 5. Pianificare la governance

Determinare i requisiti per la governance e il modo in cui è possibile conoscerli. Per altre informazioni, vedere [pianificare la governance in teams](plan-teams-governance.md) .

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto decisionale|<ul><li>Determinare e documentare i requisiti di governance seguendo le linee guida in [piano per la governance in teams](plan-teams-governance.md).</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Passaggio 6. Distribuire teams per la collaborazione

Dopo aver eseguito l'accesso a Microsoft 365 Government-GCC, seguire il percorso di distribuzione consigliato descritto in [come implementare Microsoft teams](How-to-roll-out-teams.md). Assicurati di interagire con il team di gestione di adozioni e cambiamenti.

È anche possibile collaborare con [FastTrack](https://www.microsoft.com/fasttrack) o con il partner scelto per l'onboard del servizio.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Passaggio 7. Distribuire Team per riunioni e voci

Questo è anche il momento ideale per usare team con il gruppo di stakeholder più ampio per iniziare a pianificare le riunioni e le [funzionalità di cloud Voice](cloud-voice-deployment.md).

