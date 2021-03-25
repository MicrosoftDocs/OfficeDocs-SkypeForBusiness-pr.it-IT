---
title: Microsoft 365 Government - Distribuzioni GCC
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Indicazioni per i professionisti IT per guidare le distribuzioni di Microsoft 365 in entità che gestiscono dati soggetti alle normative governative degli Stati Uniti
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
ms.openlocfilehash: 9ecc733c181e268dd6092f169e91d2f9acb4ee47
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117834"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Pianificare le distribuzioni di Microsoft 365 Government - GCC

Queste indicazioni sono per i professionisti IT che stanno guidando le distribuzioni di Microsoft 365 in enti governativi federali, statali, locali, locali, locali o territoriali o altre entità che gestiscono dati soggetti a normative e requisiti governativi, in cui l'uso di Microsoft 365 Government - GCC è appropriato per soddisfare questi requisiti. Nuovo 26 marzo 2020: Non perderti la guida introduttiva [scaricabile per GCC.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)

> [!IMPORTANT]
> Microsoft Teams sta riscontrando un enorme picco nelle chiamate online e nelle conferenze audio/video a causa della pandemia coronavirus (COVID-19).<br/>
> 
>In risposta all'aumento senza precedenti delle chiamate e per garantire la continuità e la disponibilità, Microsoft consente ai server audio/video GCC di Microsoft Teams di sfruttare la capacità di elaborazione nei data center commerciali e nei data center governativi.<br/>
> 
>Questi server audio/video si trovano all'interno dei server di confine di accreditamento FedRAMP High di Microsoft Azure negli Stati Uniti e non archiviano contenuti dei clienti. Tuttavia, questi server elaborano audio e video per chiamate e conferenze e operano sotto il nostro personale commerciale durante questo periodo provvisorio.<br/>
> 
>Personale qualificato e schermato sta monitorando questi server per un potenziale accesso ai dati dei clienti esaminando eventuali accessi interattivi a questi server. Il personale qualificato soddisfa i requisiti GCC per l'accesso al contenuto dei clienti. Per informazioni dettagliate sui requisiti di screening, vedere la [descrizione del servizio GCC.](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)<br/>
> 
>Grazie per il supporto dato che microsoft prende le misure necessarie per garantire che i nostri servizi rimangano disponibili e affidabili in questi tempi straordinari.<br/>


> [!NOTE]
> Se l'organizzazione ha già soddisfatto i requisiti di idoneità di Microsoft 365 Government - GCC e ha applicato e accettato il programma, è possibile ignorare i passaggi 1 e 2 e andare direttamente al passaggio 3. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Passaggio 1. Determinare se l'organizzazione ha bisogno di Microsoft 365 Government - GCC e soddisfa i requisiti di idoneità. 

L'ambiente Microsoft 365 Government - GCC fornisce la conformità ai requisiti governativi degli Stati Uniti per i servizi cloud, tra cui FedRAMP Moderate, e i requisiti per la giustizia penale e i sistemi di informazioni fiscali federali (tipi di dati CJI e FTI).

Oltre a usufruire delle funzionalità e delle funzionalità di Microsoft 365, le organizzazioni traggono vantaggio dalle caratteristiche seguenti specifiche di Microsoft 365 Government - GCC:

-   I contenuti dei clienti dell'organizzazione sono logicamente separati dal contenuto dei clienti nei servizi commerciali microsoft 365 da Microsoft.
-   Il contenuto dei clienti dell'organizzazione è archiviato negli Stati Uniti.
-   L'accesso al contenuto dei clienti dell'organizzazione è limitato al personale Microsoft schermato.
-   Microsoft 365 Government - GCC è conforme alle certificazioni e accreditamenti necessari per i clienti del settore pubblico degli Stati Uniti.

Per altre informazioni sull'offerta Microsoft 365 Government - GCC per i clienti di enti pubblici degli Stati Uniti, vedere i piani [Microsoft 365 Government,](https://products.office.com/government/compare-office-365-government-plans)inclusi i [requisiti di idoneità.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)

La descrizione del servizio Microsoft [365 US Government](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) descrive i vantaggi della piattaforma, che sono centrati sulla conformità dei requisiti all'interno degli Stati Uniti.

> [!Tip]
> È consigliabile trasferire le tabelle di informazioni nella descrizione del servizio in una cartella di lavoro di Excel e aggiungere due colonne: Pertinente per l'organizzazione **Y/N** e Soddisfa le esigenze dell'organizzazione **Y/N.** È quindi possibile rivedere l'elenco con i colleghi per verificare che il servizio soddisfi le esigenze dell'organizzazione.

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere se Microsoft 365 Government - GCC è appropriato per l'organizzazione.</li><li>Verificare che l'organizzazione soddisfi i requisiti di idoneità.</li></ul> |

> [!Note]
> Microsoft 365 Government - GCC è disponibile solo negli Stati Uniti. I clienti non governativi degli Stati Uniti possono scegliere tra diversi piani [di Microsoft 365 Government.](https://products.office.com/en/government/compare-office-365-government-plans)


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Passaggio 2. Applicare per Microsoft 365 Government - GCC

Dopo aver deciso che questo servizio è giusto per l'organizzazione, avviare il processo di richiesta di questo [servizio qui](https://products.office.com/government/eligibility-validation).

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Passaggio 3. Informazioni su Microsoft 365 Government - Impostazioni di sicurezza predefinite di GCC.

È consigliabile prendere tempo per [](enable-features-office-365.md) esaminare attentamente le impostazioni di sicurezza e di amministrazione prima di modificarle e valutare l'impatto sulla conformità prima di apportare modifiche alle impostazioni di sicurezza predefinite.

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto di decisione|<ul><li>Decidere se modificare o meno le impostazioni di sicurezza predefinite di Microsoft 365 Government - GCC, risolvendo in modo da comprendere prima l'impatto di eventuali modifiche apportate.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Passaggio 4. Informazioni sulle funzionalità attualmente non disponibili o disabilitate per impostazione predefinita.

Per soddisfare i requisiti dei clienti cloud governativi, esistono alcune differenze tra i piani Microsoft 365 Government - GCC ed Enterprise. Fare riferimento alla tabella seguente per vedere quali caratteristiche sono disponibili.

[Descrizione del servizio Microsoft Teams](/office365/servicedescriptions/teams-service-description)

> [!Note]
> Una volta che altri carichi di lavoro saranno completamente disponibili nel cloud GCC, saranno disponibili in Teams al termine di tutte le altre attività di integrazione.


|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto di decisione|<ul><li>Decidere se il set di funzionalità di Teams soddisfa le esigenze dell'organizzazione.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Passaggio 5. Pianificare la governance

Determinare i requisiti per la governance e come soddisfarli. Per altre [informazioni, vedere Pianificare la governance in Teams.](plan-teams-governance.md)

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto di decisione|<ul><li>Determinare e documentare i requisiti di governance seguendo le linee guida in [Pianificare la governance in Teams.](plan-teams-governance.md)</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Passaggio 6. Distribuire Teams per la collaborazione

Dopo aver eseguito l'onboarded in Microsoft 365 Government – GCC, seguire il percorso di distribuzione consigliato descritto in [Come implementare Microsoft Teams.](./deploy-overview.md) Assicurarsi di interagire con il team adoption e change management e i campioni di Teams.

È anche possibile collaborare con [FastTrack](https://www.microsoft.com/fasttrack) o con il partner scelto per l'onboarding del servizio.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Passaggio 7. Distribuire Teams per riunioni e voce

Questo è anche il momento ideale per usare Teams con il gruppo di stakeholder più ampio per iniziare a pianificare la distribuzione di riunioni e [funzionalità vocali cloud.](./cloud-voice-landing-page.md)