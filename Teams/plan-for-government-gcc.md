---
title: Microsoft 365 Government - Distribuzioni GCC
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Indicazioni per i professionisti IT per guidare le distribuzioni di Microsoft 365 in entità che gestiscono i dati soggetti alle normative del governo degli Stati Uniti
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: e40f511aedfed2423e04ece74a9c2c7f370acb74
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085610"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Pianificare le distribuzioni di Microsoft 365 Government - GCC

Queste indicazioni sono per i professionisti IT che guidano le distribuzioni di Microsoft 365 in entità federali, statali, locali, locali o territoriali o di enti governativi o di altre entità che gestiscono i dati soggetti a normative e requisiti governativi, dove l'uso di Microsoft 365 Government - GCC è appropriato per soddisfare questi requisiti. Nuovo 26 marzo 2020: non perderti la nostra guida introduttiva scaricabile [per GCC.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)

> [!IMPORTANT]
> Microsoft Teams sta riscontrando un picco incredibile nelle chiamate online e nelle audioconferenze/videoconferenze a causa del pandemico coronavirus (COVID-19).<br/>
> 
>In risposta all'aumento continuo delle chiamate e per garantire continuità e disponibilità, Microsoft consente ai server audio/video GCC di Microsoft Teams di sfruttare la capacità di elaborazione sia nei data center commerciali che nei data center governativi.<br/>
> 
>Questi server audio/video si trovano nei server di confine per l'accredito Microsoft Azure FedRAMP High negli Stati Uniti e non archiviano contenuti dei clienti. Tuttavia, questi server elaborano audio e video per chiamate e conferenze e operano nel personale commerciale durante questo periodo provvisorio.<br/>
> 
>Il personale qualificato e esaminato controlla questi server per ottenere un potenziale accesso ai dati dei clienti esaminando eventuali accessi interattivi a questi server. Il personale qualificato soddisfa i requisiti GCC per l'accesso al contenuto del cliente. Per informazioni dettagliate sui requisiti di selezione, vedere la [descrizione del servizio GCC.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)<br/>
> 
>Grazie per il supporto durante l'applicazione delle misure necessarie per garantire che i nostri servizi rimangano disponibili e affidabili in questi tempi straordinari.<br/>


> [!NOTE]
> Se l'organizzazione ha già soddisfatto i requisiti di idoneità per Microsoft 365 Government - GCC e l'ha applicata e accettata nel programma, è possibile ignorare i passaggi 1 e 2 e andare direttamente al passaggio 3. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Passaggio 1. Determinare se l'organizzazione ha bisogno di Microsoft 365 Government - GCC e soddisfa i requisiti di idoneità. 

L'ambiente Microsoft 365 Government - GCC fornisce la conformità ai requisiti del governo degli Stati Uniti per i servizi cloud, tra cui FedRAMP Moderate e i requisiti per il sistema penale e i sistemi federali di informazioni fiscali (tipi di dati CJI e FTI).

Oltre a usufruire delle caratteristiche e funzionalità di Microsoft 365, le organizzazioni beneficiano delle caratteristiche seguenti, specifiche di Microsoft 365 Government - GCC:

-   Il contenuto dei clienti dell'organizzazione è logicamente isolato dal contenuto dei clienti nei servizi commerciali di Microsoft 365 da Microsoft.
-   Il contenuto dei clienti della tua organizzazione è archiviato negli Stati Uniti.
-   L'accesso al contenuto dei clienti dell'organizzazione è limitato al personale Microsoft schermato.
-   Microsoft 365 Government - GCC è conforme alle certificazioni e ai crediti richiesti per i clienti del settore pubblico degli Stati Uniti.

Nei piani Microsoft 365 Government sono disponibili altre informazioni sull'offerta di Microsoft 365 Government - GCC per i clienti dei piani [Microsoft 365 Government,](https://products.office.com/government/compare-office-365-government-plans)inclusi i requisiti [di idoneità.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)

La descrizione del servizio [Microsoft 365 US Government](https://technet.microsoft.com/library/mt774581.aspx) descrive i vantaggi della piattaforma, che sono centrati rispetto ai requisiti di conformità all'interno degli Stati Uniti.

> [!Tip]
> È possibile trasferire le tabelle delle informazioni della descrizione del servizio in una cartella di lavoro di Excel e aggiungere due colonne: Pertinente per l'organizzazione **Y/N** e soddisfa le esigenze **dell'organizzazione Y/N.** È quindi possibile rivedere l'elenco con i colleghi per verificare che questo servizio soddisfi le esigenze dell'organizzazione.

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere se Microsoft 365 Government - GCC è appropriato per l'organizzazione.</li><li>Verificare che l'organizzazione soddisfi i requisiti di idoneità.</li></ul> |

> [!Note]
> Microsoft 365 Government - GCC è disponibile solo negli Stati Uniti. I clienti non statunitensi del governo degli Stati Uniti possono scegliere tra diversi piani [di Microsoft 365 Government.](https://products.office.com/en/government/compare-office-365-government-plans)


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Passaggio 2. Richiedere Microsoft 365 Government - GCC

Dopo aver stabilito che questo servizio è la scelta giusta per la tua organizzazione, avvia qui il processo di richiesta [per questo servizio.](https://products.office.com/government/eligibility-validation)

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Passaggio 3. Informazioni su Microsoft 365 Government : impostazioni di sicurezza predefinite per GCC.

È consigliabile rivedere attentamente le [](enable-features-office-365.md) impostazioni di sicurezza e di amministrazione prima di modificarle e valutare l'impatto sulla conformità prima di apportare modifiche alle impostazioni di sicurezza predefinite.

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto di decisione|<ul><li>Decidere se modificare una delle impostazioni di sicurezza predefinite di Microsoft 365 Government - GCC, risolvendo prima di tutto l'impatto di eventuali modifiche apportate.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Passaggio 4. Informazioni sulle funzionalità attualmente non disponibili o disabilitate per impostazione predefinita.

Per soddisfare i requisiti dei clienti cloud governativi, esistono alcune differenze tra i piani Microsoft 365 Government - GCC ed Enterprise. Fare riferimento alla tabella seguente per informazioni sulle caratteristiche disponibili.

[Descrizione del servizio Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> Una volta che altri carichi di lavoro saranno completamente disponibili nel cloud GCC, diventeranno disponibili in Teams al completamento di tutte le attività di integrazione aggiuntive.


|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto di decisione|<ul><li>Decidere se il set di funzionalità di Teams soddisfa le esigenze dell'organizzazione.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Passaggio 5. Pianificare la governance

Determinare i requisiti per la governance e come soddisfarli. Per altre [informazioni, vedere Pianificare la governance in Teams.](plan-teams-governance.md)

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto di decisione|<ul><li>Determinare e documentare i requisiti di governance, seguendo le linee guida del [Piano per la governance in Teams.](plan-teams-governance.md)</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Passaggio 6. Distribuire Teams per la collaborazione

Dopo aver eseguito l'onboarded a Microsoft 365 Government - GCC, segui il percorso di distribuzione consigliato descritto in [Come implementare Microsoft Teams.](How-to-roll-out-teams.md) Assicurarsi di coinvolgere il team di adozione e gestione delle modifiche e gli campioni di Teams.

È anche possibile usare [FastTrack](https://www.microsoft.com/fasttrack) o il partner scelto per eseguire l'onboarding del servizio.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Passaggio 7. Distribuire Teams per riunioni e voce

È anche il momento giusto per usare Teams con il gruppo degli stakeholder più ampio per iniziare a pianificare l'implementazione di riunioni e [funzionalità vocali nel cloud.](cloud-voice-deployment.md)

