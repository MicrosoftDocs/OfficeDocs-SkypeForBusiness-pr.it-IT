---
title: Microsoft 365 Government-GCC High Deployments
author: lolajacobsen
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: Linee guida per i professionisti IT per guidare le distribuzioni di Office 365 in entità che gestiscono i dati soggetti alla regolamentazione del governo degli Stati Uniti.
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
ms.openlocfilehash: 0b5111e61f6c545a7311280fa865c762e8498b86
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137812"
---
# <a name="plan-for-microsoft-365-government---gcc-high-deployments"></a>Pianificare le distribuzioni di Microsoft 365 Government-GCC High

Questa guida è destinata ai professionisti IT che guidano le distribuzioni di Office 365 nelle entità governative degli Stati Uniti o in altre entità che gestiscono i dati soggetti alle normative governative e ai requisiti, dove l'uso di Microsoft 365 Government-GCC High è appropriato per soddisfare questi requisiti.

> [!NOTE]
> Se l'organizzazione ha già incontrato il governo Microsoft 365-requisiti per l'ammissibilità di GCC ed è stato accettato nell'applicazione, è possibile ignorare i passaggi 1 e 2 e passare direttamente al passaggio 3.

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-high-and-meets-eligibility-requirements"></a>Passaggio 1. Determinare se l'organizzazione ha bisogno di Microsoft 365 Government-GCC High e soddisfa i requisiti di ammissibilità. 

Microsoft 365 Government-GCC High Environment garantisce la conformità con i requisiti del governo degli Stati Uniti per i servizi cloud. Oltre a sfruttare le caratteristiche e le funzionalità di Office 365, le organizzazioni traggono vantaggio dalle caratteristiche seguenti che sono univoche per Microsoft 365 Government-GCC High:

- Il contenuto del cliente dell'organizzazione viene separato logicamente dal contenuto dei clienti nei servizi commerciali di Office 365 da Microsoft.
- Il contenuto del cliente dell'organizzazione è archiviato negli Stati Uniti.
- L'accesso al contenuto del cliente dell'organizzazione è limitato al personale Microsoft schermato.
- Microsoft 365 Government-GCC High è conforme alle certificazioni e alle accreditazioni necessarie per i clienti del settore pubblico degli Stati Uniti.

Per altre informazioni sul governo Microsoft 365-GCC High offering for US Government Customers in [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), inclusi i [requisiti di ammissibilità](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

La [Descrizione del servizio governativo degli Stati Uniti di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) descrive i vantaggi della piattaforma, che sono centrati sui requisiti di conformità delle riunioni negli Stati Uniti.


> [!Tip]
> Potrebbe essere necessario trasferire le tabelle di informazioni nella descrizione del servizio in una cartella di lavoro di Excel e aggiungere due colonne: **rilevanti per la mia organizzazione y/n** e **soddisfano le esigenze dell'organizzazione y/n**. È quindi possibile rivedere questo elenco con i colleghi per verificare che il servizio soddisfi le esigenze dell'organizzazione.


|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere se Microsoft 365 Government-GCC High è appropriato per l'organizzazione.</li><li>Verificare che l'organizzazione soddisfi i requisiti di ammissibilità.</li></ul> |

> [!Note]
> Microsoft 365 Government-GCC High è disponibile solo negli Stati Uniti. I clienti di enti pubblici non-americani possono scegliere tra diversi [piani governativi di Office 365](https://products.office.com/en/government/compare-office-365-government-plans).

## <a name="step-2-apply-for-microsoft-365-government---gcc-high"></a>Passaggio 2. Richiedi Microsoft 365 Government-GCC High

Dopo aver deciso che il servizio è appropriato per l'organizzazione, avviare il processo di [applicazione per questo servizio](https://products.office.com/government/eligibility-validation).


## <a name="step-3-understand-microsoft-365-government---gcc-high-default-security-settings"></a>Passaggio 3. Informazioni sulle impostazioni di sicurezza predefinite Microsoft 365-GCC High default.

È consigliabile richiedere tempo per esaminare attentamente le impostazioni di [amministratore e sicurezza](enable-features-office-365.md) prima di modificarle e prendere in considerazione gli impatti sulla conformità prima di apportare modifiche alle impostazioni di sicurezza predefinite.

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto decisionale|<ul><li>Decidere se è necessario modificare le impostazioni predefinite di Microsoft 365 Government-GCC High Security, risolvendo in primo luogo l'impatto delle eventuali modifiche che potrebbero apportare.</li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---gcc-high"></a>Passaggio 4. Informazioni sulle funzionalità dei team attualmente disponibili in Microsoft 365 Government-GCC High

Per soddisfare le esigenze dei clienti del cloud governativo, esistono alcune differenze tra i team di Microsoft 365 Government-GCC High e i team nei piani aziendali. Fare riferimento alla tabella seguente per vedere quali funzionalità sono disponibili.

[Descrizione del servizio Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a>Passaggio 5. Pianificare la governance

Determinare i requisiti per la governance e il modo in cui è possibile conoscerli. Per altre informazioni, vedere [pianificare la governance in teams](plan-teams-governance.md) .

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|Punto decisionale |<ul><li>Determinare e documentare i requisiti di governance seguendo le linee guida in [piano per la governance in teams](plan-teams-governance.md). </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a>Passaggio 6. Distribuire teams per la collaborazione

Dopo aver eseguito l'accesso a Microsoft 365 Government-GCC High, seguire il percorso di distribuzione consigliato descritto in [come implementare Microsoft teams](How-to-roll-out-teams.md). Assicurati di interagire con il team di gestione di adozioni e cambiamenti.

È anche possibile collaborare con [FastTrack](https://www.microsoft.com/fasttrack) o con il partner scelto per l'onboard del servizio.

