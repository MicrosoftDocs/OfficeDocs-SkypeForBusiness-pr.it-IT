---
title: Pianificare le distribuzioni di Microsoft 365 Government-DoD-Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Linee guida per i professionisti IT per guidare le distribuzioni di Office 365 in entità che gestiscono i dati soggetti al regolamento della difesa del governo degli Stati Uniti.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 12d9350437867b04a181e62e8b23bb6ed78d8fbc
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161737"
---
# <a name="plan-for-microsoft-365-government---dod-deployments"></a>Pianificare le distribuzioni di Microsoft 365 Government-DoD

Questa guida è destinata ai professionisti IT che guidano le distribuzioni di Office 365 nelle entità governative degli Stati Uniti o in altre entità che gestiscono i dati soggetti alle normative governative e ai requisiti, in cui l'uso di Microsoft 365 Government-DoD è appropriato per soddisfare questi requisiti.

> [!NOTE]
> Se l'organizzazione ha già incontrato il governo Microsoft 365-requisiti per l'ammissibilità alla difesa e richiesto e accettato nel programma, è possibile ignorare i passaggi 1 e 2 e passare direttamente al passaggio 3.

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---dod-and-meets-eligibility-requirements"></a>Passaggio 1. Determinare se l'organizzazione ha bisogno di Microsoft 365 Government-DoD e soddisfa i requisiti di ammissibilità. 

L'ambiente Microsoft 365 Government-DoD offre la conformità con i requisiti del governo degli Stati Uniti per i servizi cloud. Oltre a sfruttare le caratteristiche e le funzionalità di Office 365, le organizzazioni traggono vantaggio dalle caratteristiche seguenti che sono univoche per Microsoft 365 Government-DoD:

- Il contenuto del cliente dell'organizzazione viene separato logicamente dal contenuto dei clienti nei servizi commerciali di Office 365 da Microsoft.
- Il contenuto del cliente dell'organizzazione è archiviato negli Stati Uniti.
- L'accesso al contenuto del cliente dell'organizzazione è limitato al personale Microsoft schermato.
- Microsoft 365 Government-DoD è conforme alle certificazioni e alle accreditazioni necessarie per i clienti del settore pubblico.

Per altre informazioni su Microsoft 365 Government-DoD offering for US Government Customers in [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), inclusi i [requisiti di ammissibilità](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

La [Descrizione del servizio governativo degli Stati Uniti di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) descrive i vantaggi della piattaforma, che sono centrati sui requisiti di conformità delle riunioni negli Stati Uniti.


> [!Tip]
> Potrebbe essere necessario trasferire le tabelle di informazioni nella descrizione del servizio in una cartella di lavoro di Excel e aggiungere due colonne: **rilevanti per la mia organizzazione y/n** e **soddisfano le esigenze dell'organizzazione y/n**. È quindi possibile rivedere questo elenco con i colleghi per verificare che il servizio soddisfi le esigenze dell'organizzazione.


|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere se Microsoft 365 Government-DoD è appropriato per l'organizzazione.</li><li>Verificare che l'organizzazione soddisfi i requisiti di ammissibilità.</li></ul> |

> [!Note]
> Microsoft 365 Government-DoD è disponibile solo negli Stati Uniti. I clienti di enti pubblici non-americani possono scegliere tra diversi [piani governativi di Office 365](https://products.office.com/en/government/compare-office-365-government-plans).

## <a name="step-2-apply-for-microsoft-365-government---dod"></a>Passaggio 2. Richiedi Microsoft 365 Government-DoD

Dopo aver deciso che il servizio è appropriato per l'organizzazione, avviare il processo di [applicazione per questo servizio](https://products.office.com/government/eligibility-validation).


## <a name="step-3-understand-microsoft-365-government---dod-default-security-settings"></a>Passaggio 3. Informazioni sulle impostazioni di sicurezza predefinite di Microsoft 365 Government-DoD.

È consigliabile richiedere tempo per esaminare attentamente le impostazioni di [amministratore e sicurezza](enable-features-office-365.md) prima di modificarle e prendere in considerazione gli impatti sulla conformità prima di apportare modifiche alle impostazioni di sicurezza predefinite.

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto decisionale|<ul><li>Decidere se è necessario modificare le impostazioni di sicurezza governative di Microsoft 365 predefinite, risolvendo in primo luogo l'impatto delle eventuali modifiche che potrebbero apportare.</li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---dod"></a>Passaggio 4. Informazioni sulle funzionalità dei team attualmente disponibili in Microsoft 365 Government-DoD

Per soddisfare le esigenze dei clienti del cloud governativo, esistono alcune differenze tra teams in Microsoft 365 Government-DoD e teams in piani aziendali. Fare riferimento alla tabella seguente per vedere quali funzionalità sono disponibili.

|                             | Funzionalità                     | Dipartimento della difesa       |
|-----------------------------|-----------------------------|----------------|
| Base | Accesso | Disponibili |
| | Icone di presenza | Disponibili |
| | Presenza unificata (Skype for business e teams Unified) | Nell'arretrato governativo |
| | Client Linux | Nell'arretrato governativo |
| Attività | Feed | Disponibili |
|  | Attività personali | Disponibili |
| Chat | Conversazione | Disponibili |
| | File | Disponibili |
| | Organigramma | Disponibili |
| | Attività | Disponibili |
| | Interoperabilità (1:1 Teams-chat Skype for business) | Nell'arretrato governativo |
| Teams | Messaggio di canale | Disponibili |
| | File di canale | Disponibili |
| | Scheda OneNote | Nell'arretrato governativo |
| | Inviare un canale tramite posta elettronica | Non disponibile |
| | Aggiungi membro | Disponibili |
| | Accesso guest | Nell'arretrato governativo |
| Riunioni | Pianificare una riunione | Disponibili |
| | Partecipare a una riunione | Disponibili |
| | Riunione VoIP | Disponibili |
| | Condivisione desktop | Disponibili |
| | Dare e prendere il controllo della condivisione | Disponibili |
| | Connettersi da una sala riunioni | Disponibili |
| | Registrazione cloud | Nell'arretrato governativo |
| | Note riunione | Disponibili |
| | Riunioni broadcast | Nell'arretrato governativo |
| | Riunioni federate intra-cloud (DoD-DoD) | Disponibili |
| | Supporto per Surface Hub | Nell'arretrato governativo |
| Chiamate | Contatti | Disponibili |
| | Storia | Disponibili |
| | Casella vocale | Disponibili |
| | Chiamata VoIP | Disponibili |
| | Skype for business-teams Calling | Disponibili |
| | Piani per chiamate | Non disponibile |
| | Servizi di audioconferenza (per consentire ai partecipanti alla riunione di partecipare tramite PSTN) | Disponibili |
| | Routing diretto di Microsoft Phone System | Nell'arretrato governativo |
| | Sala di attesa per i chiamanti PSTN | Nell'arretrato governativo |
| | Coda di chiamata | Nell'arretrato governativo |
| | Supporto di boss e delegati | Nell'arretrato governativo |
| | Trasferimento consultivo e sicuro | Nell'arretrato governativo |
| | Non disturbare l'innovazione | Nell'arretrato governativo |
| | Anello distintivo | Nell'arretrato governativo |
| | 1:1 per raggruppare le escalation delle chiamate con team, Skype for business e partecipanti PSTN | Nell'arretrato governativo |
| | Inoltra al gruppo | Nell'arretrato governativo |
| | Trasferimento a chiamata PSTN | Nell'arretrato governativo |
| | Piani per chiamate di emergenza | Nell'arretrato governativo |
| | Supporto per i telefoni SIP certificati esistenti | Nell'arretrato governativo |
| | USB HID | Disponibili |
| | eDiscovery per le chiamate e le riunioni | Disponibili |
| | Operatore automatico organizzazione | Nell'arretrato governativo |
| | Supporto per Skype consumer-teams Call | Non disponibile |
| File | Recente | Disponibili |
| | Microsoft Teams | Disponibili |
| Negozio | App Store | Non disponibile |
| Ricerca | Messaggi | Disponibili |
| | Persone | Disponibili |
| | File | Disponibili |
| | Comandi barra | Disponibili |
| Conformità | Ricerca di contenuto di conformità | Disponibili |
| | Conservazione | Disponibili |
| | Ricerca nel log di controllo | Disponibili |
| | Blocco legale | Disponibili |
| | eDiscovery | Disponibili |

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto decisionale|<ul><li>Decidere se il set di funzionalità teams soddisfa le esigenze dell'organizzazione.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Passaggio 5. Pianificare la governance

Determinare i requisiti per la governance e il modo in cui è possibile conoscerli. Per altre informazioni, vedere [pianificare la governance in teams](plan-teams-governance.md) .

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Punto decisionale |<ul><li>Determinare e documentare i requisiti di governance seguendo le linee guida in [piano per la governance in teams](plan-teams-governance.md). </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a>Passaggio 6. Distribuire teams per la collaborazione

Dopo aver eseguito l'accesso a Microsoft 365 Government-DoD, seguire il percorso di distribuzione consigliato descritto in [come implementare Microsoft teams](How-to-roll-out-teams.md). Assicurati di interagire con il team di gestione di adozioni e cambiamenti.

È anche possibile collaborare con [FastTrack](https://www.microsoft.com/fasttrack) o con il partner scelto per l'onboard del servizio.
