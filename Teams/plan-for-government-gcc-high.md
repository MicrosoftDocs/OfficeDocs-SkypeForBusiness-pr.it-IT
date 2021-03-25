---
title: Microsoft 365 Government - Distribuzioni GCC High
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: Indicazioni per i professionisti IT per guidare le distribuzioni di Office 365 in entità che gestiscono dati soggetti alle normative governative degli Stati Uniti.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c5533b6d5c2e08cb79ec8dd2052d761d86546b05
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117844"
---
# <a name="plan-for-office-365-government---gcc-high-deployments"></a>Pianificare le distribuzioni di Office 365 Government - GCC High

Queste indicazioni sono per i professionisti IT che guidano le distribuzioni di Office 365 nelle entità del governo federale degli Stati Uniti o in altre entità che gestiscono dati soggetti a normative e requisiti governativi, in cui l'uso di Office 365 Government – GCC High è appropriato per soddisfare questi requisiti.

> [!NOTE]
> Se l'organizzazione ha già soddisfatto i requisiti di idoneità office 365 Government - GCC High e ha applicato e accettato il programma, è possibile saltare i passaggi 1 e 2 e andare direttamente al passaggio 3.

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-high-and-meets-eligibility-requirements"></a>Passaggio 1. Determinare se l'organizzazione ha bisogno di Office 365 Government - GCC High e soddisfa i requisiti di idoneità. 

L'ambiente Office 365 Government - GCC High fornisce la conformità ai requisiti governativi degli Stati Uniti per i servizi cloud. Oltre a usufruire delle caratteristiche e delle funzionalità di Office 365, le organizzazioni traggono vantaggio dalle caratteristiche seguenti specifiche di Office 365 Government – GCC High:

- I contenuti dei clienti dell'organizzazione sono logicamente separati dal contenuto dei clienti nei servizi commerciali di Office 365 da Microsoft.
- Il contenuto dei clienti dell'organizzazione è archiviato negli Stati Uniti.
- L'accesso al contenuto dei clienti dell'organizzazione è limitato al personale Microsoft schermato.
- Office 365 Government : GCC High è conforme alle certificazioni e accreditamenti necessari per i clienti del settore pubblico degli Stati Uniti.

Per altre informazioni sull'offerta Office 365 Government - GCC High per i clienti del governo degli Stati Uniti, vedere Piani [di Office 365 Government,](https://products.office.com/government/compare-office-365-government-plans)inclusi i [requisiti di idoneità.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)

La descrizione del servizio Office [365 US Government](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) descrive i vantaggi della piattaforma, centrati sui requisiti di conformità all'interno degli Stati Uniti.


> [!Tip]
> È consigliabile trasferire le tabelle di informazioni nella descrizione del servizio in una cartella di lavoro di Excel e aggiungere due colonne: Pertinente per l'organizzazione **Y/N** e Soddisfa le esigenze dell'organizzazione **Y/N.** È quindi possibile rivedere l'elenco con i colleghi per verificare che il servizio soddisfi le esigenze dell'organizzazione.


|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere se Office 365 Government - GCC High è appropriato per l'organizzazione.</li><li>Verificare che l'organizzazione soddisfi i requisiti di idoneità.</li></ul> |

> [!Note]
> Office 365 Government - GCC High è disponibile solo negli Stati Uniti. I clienti non governativi degli Stati Uniti possono scegliere tra diversi piani [di Office 365 Government.](https://products.office.com/en/government/compare-office-365-government-plans)

## <a name="step-2-apply-for-office-365-government---gcc-high"></a>Passaggio 2. Applicare per Office 365 Government - GCC High

Dopo aver deciso che questo servizio è giusto per l'organizzazione, avviare il processo di [richiesta di questo servizio.](https://products.office.com/government/eligibility-validation)


## <a name="step-3-understand-office-365-government---gcc-high-default-security-settings"></a>Passaggio 3. Informazioni su Office 365 Government - Impostazioni di sicurezza predefinite di GCC High.

È consigliabile prendere tempo per [](enable-features-office-365.md) esaminare attentamente le impostazioni di sicurezza e di amministrazione prima di modificarle e valutare l'impatto sulla conformità prima di apportare modifiche alle impostazioni di sicurezza predefinite.

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto di decisione|<ul><li>Decidere se è necessario modificare le impostazioni predefinite di Office 365 Government - GCC High security, risolvendo prima di tutto l'impatto di eventuali modifiche.</li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---gcc-high"></a>Passaggio 4. Informazioni sulle funzionalità di Teams attualmente disponibili in Office 365 Government - GCC High

Per soddisfare i requisiti dei clienti cloud governativi, esistono alcune differenze tra Teams in Office 365 Government - GCC High e Teams nei piani Enterprise. Fare riferimento alla tabella seguente per vedere quali caratteristiche sono disponibili.

[Descrizione del servizio Microsoft Teams](/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a>Passaggio 5. Pianificare la governance

Determinare i requisiti per la governance e come soddisfarli. Per altre [informazioni, vedere Pianificare la governance in Teams.](plan-teams-governance.md)

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|Punto di decisione |<ul><li>Determinare e documentare i requisiti di governance seguendo le linee guida in [Pianificare la governance in Teams.](plan-teams-governance.md) </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a>Passaggio 6. Distribuire Teams per la collaborazione

Dopo aver eseguito l'onboarded in Office 365 Government – GCC High, seguire il percorso di distribuzione consigliato descritto in [Come implementare Microsoft Teams.](./deploy-overview.md) Assicurarsi di interagire con il team adoption e change management e i campioni di Teams.

È anche possibile collaborare con [FastTrack](https://www.microsoft.com/fasttrack) o con il partner scelto per l'onboarding del servizio.

> [!NOTE]
> Il client Mac Teams per ambienti GCCH non è ancora supportato.