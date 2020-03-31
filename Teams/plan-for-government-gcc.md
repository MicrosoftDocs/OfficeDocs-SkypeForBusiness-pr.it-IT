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
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb36e9decf7fba80250dce1035187b94198bc86d
ms.sourcegitcommit: f96d66d08a9d6993edbb9554738dc8236d901933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2020
ms.locfileid: "43053609"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Pianificare le distribuzioni di Microsoft 365 Government-GCC

Questa guida è per i professionisti IT che guidano le distribuzioni di Office 365 in Stati Uniti, enti governativi federali, statali, locali, tribali o territoriali o altre entità che gestiscono i dati soggetti alle normative governative e ai requisiti, dove l'uso di Microsoft 365 Government-GCC è appropriato per soddisfare questi requisiti. Nuovo 26 marzo 2020: non perdere la Guida introduttiva scaricabile [per GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).

> [!IMPORTANT]
> Microsoft teams sta vivendo un enorme picco nelle chiamate online e nelle conferenze audio/video a causa della pandemia di coronavirus (COVID-19).<br/>
> 
>In risposta all'aumento senza precedenti delle chiamate e per garantirne la continuità e la disponibilità, Microsoft consente a Microsoft teams GCC audio/video server di sfruttare la capacità di elaborazione nei nostri datacenter commerciali, oltre che nei datacenter di stato.<br/>
> 
>Questi server audio/video si trovano all'interno dei server Microsoft Azure FedRAMP High Accreditation Boundary negli Stati Uniti e non archiviano il contenuto del cliente. Tuttavia, questi server elaborano audio e video per le chiamate e le conferenze e operano sotto il nostro personale commerciale durante questo periodo di interim.<br/>
> 
>Il personale qualificato e schermato sta monitorando questi server per un potenziale accesso ai dati dei clienti, rivedendo eventuali log-ons interattivi in questi server. Il personale qualificato soddisfa i requisiti di GCC per accedere al contenuto del cliente. Per informazioni dettagliate sui requisiti di selezione, vedere la [Descrizione del servizio GCC](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).<br/>
> 
>Grazie per il tuo supporto mentre procediamo per garantire che i nostri servizi rimangano disponibili e affidabili in questi tempi straordinari.<br/>


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
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere se Microsoft 365 Government-GCC è appropriato per l'organizzazione.</li><li>Verificare che l'organizzazione soddisfi i requisiti di ammissibilità.</li></ul> |

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
| Base | Accesso | Disponibile |
| | Icone di presenza | Disponibile |
| | Presenza unificata (Skype for business e teams Unified) | Disponibile |
| Attività | Feed | Disponibile |
|  | Attività personali | Disponibile |
| Chat | Conversazione | Disponibile |
| | File | Disponibile |
| | Organigramma | Disponibile |
| | Attività | Disponibile |
| | Interoperabilità (1:1 Teams-chat Skype for business) | Disponibile |
| Teams | Messaggio di canale | Disponibile |
| | File di canale | Disponibile |
| | Scheda OneNote | Nell'arretrato governativo |
| | Inviare un canale tramite posta elettronica | Non disponibile |
| | Aggiungi membro | Disponibile |
| | Accesso guest | Disponibile |
| Riunioni | Pianificare una riunione | Disponibile |
| | Partecipare a una riunione | Disponibile |
| | Riunione VoIP | Disponibile |
| | Condivisione desktop | Disponibile |
| | Dare e prendere il controllo della condivisione | Disponibile |
| | Connettersi da una sala riunioni | Disponibile |
| | Join anonimo | Disponibile |
| | Registrazione cloud | Disponibile |
| | Note riunione | Disponibile |
| | Eventi dinamici | Disponibile |
| | Riunioni federate | Disponibile |
| | Supporto per Surface Hub | Disponibile |
| Chiamate | Contatti | Disponibile |
| | Storia | Disponibile |
| | Segreteria telefonica | Disponibile |
| | Chiamata VoIP | Disponibile |
| | Skype for business-teams Calling | Disponibile |
| | Piani di chiamata | Disponibile |
| | Servizi di audioconferenza (per consentire ai partecipanti alla riunione di partecipare tramite PSTN) | Disponibile |
| | Routing diretto di Microsoft Phone System | Disponibile |
| | Sala di attesa per i chiamanti PSTN | Disponibile |
| | Coda di chiamata | Disponibile |
| | Supporto di boss e delegati | Disponibile |
| | Trasferimento consultivo e sicuro | Disponibile |
| | Non disturbare l'innovazione | Disponibile |
| | Anello distintivo | Disponibile |
| | 1:1 per raggruppare le escalation delle chiamate con team, Skype for business e partecipanti PSTN | Disponibile |
| | Inoltra al gruppo | Disponibile |
| | Trasferimento a chiamata PSTN | Disponibile |
| | Piani per chiamate di emergenza | Disponibile |
| | Supporto per i telefoni SIP certificati esistenti | Disponibile |
| | USB HID | Disponibile |
| | eDiscovery per le chiamate e le riunioni | Disponibile |
| | Operatore automatico organizzazione | Disponibile |
| | Supporto per Skype consumer-teams Call | Disponibile |
| File | Recente | Disponibile |
| | Microsoft Teams | Disponibile |
| Store | App Store | Disponibile |
| Ricerca | Messaggi | Disponibile |
| | Persone | Disponibile |
| | File | Disponibile |
| | Comandi barra | Disponibile |
| Conformità | Ricerca di contenuto di conformità | Disponibile |
| | Conservazione | Disponibile |
| | Ricerca nel log di controllo | Disponibile |
| | Blocco legale | Disponibile |
| | eDiscovery | Disponibile |

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

