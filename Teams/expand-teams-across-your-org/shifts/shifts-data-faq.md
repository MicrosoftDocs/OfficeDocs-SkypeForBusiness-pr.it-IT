---
title: Domande frequenti sui dati relativi ai turni
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Risposte alle domande frequenti sui dati di Shifts, tra cui la posizione in cui sono archiviati i dati di Shifts, la conservazione dei dati, il recupero e la crittografia.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3f26413aa746b37474e7035e313fc8ffff2fb93c
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2022
ms.locfileid: "63039954"
---
# <a name="shifts-data-faq"></a>Domande frequenti sui dati relativi ai turni

Questo articolo illustra le domande frequenti sui dati di Shifts, tra cui la posizione in cui vengono archiviati i dati di Shifts, la conservazione dei dati, il recupero e la crittografia.

## <a name="where-is-shifts-data-stored"></a>Dove vengono archiviati i dati di Shifts?

I dati dei turni vengono archiviati in una delle tre aree geografiche (geos): Asia Pacifico (APAC), Unione Europea (UE) o Stati Uniti. Ogni area geografica archivia i dati in almeno due aree del data center di Azure per disponibilità elevata (HA) e ripristino di emergenza (DR). Oggi, gli Stati Uniti e l'America del Nord utilizzano data center negli Stati Uniti centro-sette-meridionali. Per altre informazioni, vedere [Dove Microsoft 365 archiviati i dati dei clienti](/microsoft-365/enterprise/o365-data-locations).

Attualmente, Shifts offre la residenza dei dati in Australia, Canada, Francia, Giappone e Regno Unito. Stiamo lavorando attivamente per espandere il supporto in altre posizioni.

## <a name="can-i-choose-where-shifts-data-is-stored"></a>È possibile scegliere dove archiviare i dati di Shifts?

Quando si configura il Teams, si sceglie un paese o un'area geografica, che viene impostato a livello di abbonamento. I turni rispettano questa selezione e usa le impostazioni locali e l'area geografica impostate in Teams se l'area geografica è in uso. Se non ci si trova ancora in quell'area geografica, i dati vengono archiviati in un'area geografica vicina che viene supportato. In futuro si prevede di eseguire la migrazione dei dati esistenti, se archiviati in un'area geografica vicina, all'area di cui è stato eseguito il provisioning in Teams.

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>È possibile accedere ed esportare o eliminare i dati personali di un utente in Turni?

Turni è conforme al GDPR (General Data Protection Regulation).Una richiesta formale da parte di una persona (nota come soggetto di dati) di eseguire un'azione sui propri dati personali è detta richiesta DSR (Data Subject Request). È possibile trovare e agire sui dati personali in Turni in risposta a un DSR.

È possibile usare lo strumento Ricerca contenuto di eDiscovery nel Centro conformità Microsoft 365 per cercare ed esportare i dati della pianificazione e dell'orologio in Excel. Per tutti gli altri dati di Shifts, è possibile acquisire screenshot dei dati.

Per altre informazioni, vedere Office 365 richieste per l'oggetto [dei dati per il GDPR e il CCPA](/microsoft-365/compliance/gdpr-dsr-office365).

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>Cosa succede ai dati dei turni se si disattiva Turni per l'organizzazione?

La disattivazione dei turni *nell'organizzazione non elimina* i dati. Se si disattivaNo i turni e in seguito si attivaNo i turni, i dati di Turni saranno comunque disponibili.

Se si elimina il tenant, tutti i dati di Shifts vengono eliminati al termine del periodo di conservazione.

Non è disponibile alcuna opzione per eliminare solo i dati di Shifts. Se si elimina un team in Teams, i dati di pianificazione di Turni associati al team vengono eliminati al termine del periodo di conservazione. Per altre informazioni, vedere [Conservazione, eliminazione](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview) e distruzione dei dati in Microsoft 365.

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>È possibile recuperare una pianificazione di Turni eliminata?

È possibile recuperare una pianificazione eliminata se viene ripristinato Microsoft 365 gruppo di lavoro che la Teams di backup.

Per impostazione predefinita, un gruppo di Microsoft 365 viene mantenuto per 30 giorni. Questo periodo di 30 giorni è denominato "eliminazione soffice" perché è comunque possibile ripristinare il gruppo. Per altre informazioni, vedere [Ripristinare un gruppo Microsoft 365 eliminato](/microsoft-365/admin/create-groups/restore-deleted-group?view=o365-worldwide&tabs=admin-center).

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>È possibile usare criteri di conservazione personalizzati per i dati di Turni?

Attualmente, Shifts non supporta criteri di conservazione personalizzati.

Per altre informazioni sui criteri di conservazione in Teams, vedere Informazioni sulla [](/microsoft-365/compliance/retention-policies-teams) conservazione per Teams e Gestire i criteri di conservazione [per](../../retention-policies.md) Teams.

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>È possibile recuperare i dati di Turni per un utente la cui licenza è stata revocata?

Oggi non è possibile recuperare dati per un utente la cui licenza è stata revocata. Questa funzionalità è un elemento su cui stiamo lavorando.

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>Che tipo di crittografia usa Shifts per i dati in pausa e in transito?

I dati dei turni vengono crittografati a riposo da Azure Cosmos DB e Azure Archiviazione. Per altre informazioni, vedere [Crittografia dei dati di Azure in](/azure/security/fundamentals/encryption-atrest) pausa e Crittografia [dei dati in Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest).

Turni segue le Microsoft 365 per la crittografia dei dati in transito. Per altre informazioni, vedere [Crittografia per i dati in transito](/compliance/assurance/assurance-encryption-in-transit).

La crittografia dei dati in pausa e in transito viene verificata ogni anno dal controllo di conformità SOC2.

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>È possibile accedere a copie non modificabili dei dati di Shifts?

Non vengono archiviate copie non modificabili dei dati di Shifts. Ad esempio, un responsabile può apportare modifiche a una programmazione, ad esempio aggiungere note, modificare gli orari dei turni, assegnare attività e così via.

## <a name="can-shifts-data-be-edited"></a>È possibile modificare i dati di Shifts?

Alcuni aspetti dei turni non possono essere modificati e alcuni aspetti che possono essere modificati. Ad esempio, i dettagli del turno, come le note e i colori, possono essere modificati in modo simile a come possono essere modificati nell'app Turni. Le richieste di turni non possono essere modificate a meno che la richiesta non venga ritirata.

Per vedere quali campi sono stati modificati, è possibile cercare nel log di controllo Microsoft 365 eventi turni. Per altre informazioni sugli eventi registrati per le attività turni nel log Microsoft 365 di controllo, vedere Turni [nelle Teams lavoro](../../audit-log-events.md#shifts-in-teams-activities).

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>L'organizzazione usa un sistema di gestione della forza lavoro per la pianificazione. È possibile eseguire l'integrazione con i dati di Shifts e accedervi?

Le API Graph turni consentono di integrare i dati di Turni con sistemi WFM (External Workforce Management). Per altre informazioni, vedere [Graph API](/graph/api/resources/shift).

Sono inoltre disponibili connettori shift gestiti e connettori Shifts open-source. Con questi connettori è possibile integrare il sistema WFM direttamente con Turni. Per altre informazioni sui connettori Shifts e sui sistemi WFM supportati, vedere [Turni connettori](shifts-connectors.md).

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>È possibile eliminare definitivamente i dati di Shifts dopo un periodo di tempo specificato?

Oggi non eliminiamo affatto i dati di Turni. Usando [shifts Graph API](/graph/api/resources/shift), è possibile creare [un'app](/powerapps/maker/) usando Power Apps per conservare i dati per un periodo di tempo specificato. Tuttavia, questa funzionalità non è supportate in modo nativo.

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>È possibile spostare i dati di Shifts in una migrazione da tenant a tenant?

È possibile eseguire la migrazione dei dati dei turni da un tenant a un altro tenant su richiesta specifica. Tenere presente che la migrazione da tenant a tenant non è supportata, ma può essere generata come richiesta del cliente.

## <a name="related-articles"></a>Articoli correlati

- [Turni per Teams](../shifts-for-teams-landing-page.md)
- [Gestire l'app Turni](manage-the-shifts-app-for-your-organization-in-teams.md)
