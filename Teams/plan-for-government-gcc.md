---
title: Microsoft 365 Pubblica amministrazione - GCC distribuzione
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Indicazioni per i professionisti IT per guidare Microsoft 365 distribuzioni in entità che gestiscono dati soggetti alla normativa governativa degli Stati Uniti
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
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Pianificare distribuzioni Microsoft 365 government - GCC

Queste indicazioni sono per i professionisti IT che stanno guidando le distribuzioni di Microsoft 365 in enti governativi federali, statali, locali, locali, locali o territoriali o altre entità che gestiscono dati soggetti a normative e requisiti governativi, in cui l'uso di Microsoft 365 Government - GCC è appropriato per soddisfare questi requisiti. Nuovo 26 marzo 2020: Non perderti la guida introduttiva scaricabile per [GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).

> [!IMPORTANT]
> Microsoft Teams sta riscontrando un enorme picco nelle chiamate online e nelle conferenze audio/video a causa della pandemia del coronavirus (COVID-19).<br/>
> 
>In risposta all'aumento senza precedenti delle chiamate e per garantire continuità e disponibilità, Microsoft consente ai server audio/video di Microsoft Teams GCC di sfruttare la capacità di elaborazione nei data center commerciali e nei data center governativi.<br/>
> 
>Questi server audio/video si trovano all'interno Microsoft Azure fedRAMP High accreditation boundary servers negli Stati Uniti e non archiviano contenuti dei clienti. Tuttavia, questi server elaborano audio e video per chiamate e conferenze e operano sotto il nostro personale commerciale durante questo periodo provvisorio.<br/>
> 
>Personale qualificato e schermato sta monitorando questi server per un potenziale accesso ai dati dei clienti esaminando eventuali accessi interattivi a questi server. Il personale qualificato soddisfa GCC requisiti per l'accesso al contenuto dei clienti. Per informazioni dettagliate sui requisiti di screening, vedere la [GCC del servizio.](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)<br/>
> 
>Grazie per il supporto dato che microsoft prende le misure necessarie per garantire che i nostri servizi rimangano disponibili e affidabili in questi tempi straordinari.<br/>


> [!NOTE]
> Se l'organizzazione ha già soddisfatto i requisiti di idoneità di Microsoft 365 Government - GCC e ha applicato e accettato il programma, è possibile ignorare i passaggi 1 e 2 e andare direttamente al passaggio 3. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Passaggio 1. Determinare se l'organizzazione deve Microsoft 365 government - GCC e soddisfi i requisiti di idoneità. 

L'ambiente Microsoft 365 Government - GCC fornisce la conformità ai requisiti governativi degli Stati Uniti per i servizi cloud, tra cui FedRAMP Moderate, e i requisiti per la giustizia penale e i sistemi di informazioni fiscali federali (tipi di dati CJI e FTI).

Oltre a usufruire delle funzionalità e delle funzionalità di Microsoft 365, le organizzazioni traggono vantaggio dalle caratteristiche seguenti specifiche di Microsoft 365 Government - GCC:

-   Il contenuto dei clienti dell'organizzazione è logicamente segregato dai contenuti dei clienti nei servizi Microsoft 365 commerciali da Microsoft.
-   Il contenuto dei clienti dell'organizzazione è archiviato negli Stati Uniti.
-   L'accesso al contenuto dei clienti dell'organizzazione è limitato al personale Microsoft schermato.
-   Microsoft 365 Enti pubblici: GCC con certificazioni e accreditamenti necessari per i clienti del settore pubblico degli Stati Uniti.

Per altre informazioni sull'offerta Microsoft 365 Government - GCC per i clienti del governo degli Stati Uniti, vedere i piani [Microsoft 365 Government,](https://products.office.com/government/compare-office-365-government-plans)inclusi i requisiti di [idoneità.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)

La [Microsoft 365 del](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) servizio del governo degli Stati Uniti descrive i vantaggi della piattaforma, che sono centrati sulla conformità dei requisiti all'interno degli Stati Uniti.

> [!Tip]
> È consigliabile trasferire le tabelle di informazioni nella descrizione del servizio in una cartella di lavoro di Excel e aggiungere due colonne: Rilevanti per l'organizzazione **Y/N** e Soddisfa le esigenze dell'organizzazione **Y/N.** È quindi possibile rivedere l'elenco con i colleghi per verificare che il servizio soddisfi le esigenze dell'organizzazione.

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere se Microsoft 365 government - GCC è appropriato per l'organizzazione.</li><li>Verificare che l'organizzazione soddisfi i requisiti di idoneità.</li></ul> |

> [!Note]
> Microsoft 365 Government - GCC è disponibile solo negli Stati Uniti. I clienti non governativi degli Stati Uniti possono scegliere tra una serie di Microsoft 365 [per enti pubblici.](https://products.office.com/en/government/compare-office-365-government-plans)


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Passaggio 2. Candidarsi Microsoft 365 governo - GCC

Dopo aver deciso che questo servizio è giusto per l'organizzazione, avviare il processo di richiesta di questo [servizio qui](https://products.office.com/government/eligibility-validation).

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Passaggio 3. Informazioni Microsoft 365 government- GCC di sicurezza predefinite.

È consigliabile prendere tempo per [](enable-features-office-365.md) esaminare attentamente le impostazioni di sicurezza e di amministrazione prima di modificarle e valutare l'impatto sulla conformità prima di apportare modifiche alle impostazioni di sicurezza predefinite.

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto di decisione|<ul><li>Decidere se si modificherà una delle impostazioni di sicurezza Microsoft 365 Government - GCC, risolvendo prima di tutto l'impatto di eventuali modifiche apportate.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Passaggio 4. Informazioni sulle funzionalità attualmente non disponibili o disabilitate per impostazione predefinita.

Per soddisfare i requisiti dei clienti cloud per enti pubblici, esistono alcune differenze tra i piani Microsoft 365 government- GCC e Enterprise government. Fare riferimento alla tabella seguente per vedere quali caratteristiche sono disponibili.

[Microsoft Teams servizio](/office365/servicedescriptions/teams-service-description)

> [!Note]
> Una volta che altri carichi di lavoro saranno completamente disponibili nel cloud GCC, saranno disponibili in Teams al termine di tutte le altre attività di integrazione.


|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto di decisione|<ul><li>Decidere se il set Teams caratteristiche soddisfa le esigenze dell'organizzazione.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Passaggio 5. Pianificare la governance

Determinare i requisiti per la governance e come soddisfarli. Passare a [Pianificare la governance in Teams](plan-teams-governance.md) per altre informazioni.

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto di decisione|<ul><li>Determinare e documentare i requisiti di governance seguendo le linee guida in [Pianificare la governance in Teams](plan-teams-governance.md).</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Passaggio 6. Distribuire Teams per la collaborazione

Dopo aver eseguito l'onboarded a Microsoft 365 Government - GCC, seguire il percorso di distribuzione consigliato descritto [in](./deploy-overview.md)Come implementare Microsoft Teams . Assicurarsi di interagire con il team di adozione e gestione delle modifiche e Teams campioni.

È anche possibile collaborare con [FastTrack](https://www.microsoft.com/fasttrack) o con il partner scelto per l'onboarding del servizio.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Passaggio 7. Distribuire Teams per le riunioni e la voce

Questo è anche il momento ideale per usare Teams con il gruppo di stakeholder più ampio per iniziare a pianificare la distribuzione di riunioni e [funzionalità vocali cloud.](./cloud-voice-landing-page.md)