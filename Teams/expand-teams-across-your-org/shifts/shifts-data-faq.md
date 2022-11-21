---
title: Domande frequenti su Turni
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Risposte alle domande frequenti sui dati di Turni, inclusa la posizione in cui vengono archiviati i dati di Turni, la conservazione, il recupero e la crittografia dei dati.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365-frontline
- tier2
- highpri
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 39dcbc391096db8edce7dee90abe6ee26e24f027
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131025"
---
# <a name="shifts-data-faq"></a>Domande frequenti su Turni

Questo articolo illustra le domande frequenti sui dati di Turni, tra cui dove vengono archiviati i dati di Turni, la conservazione, il recupero e la crittografia dei dati.

## <a name="where-is-shifts-data-stored"></a>Dove vengono archiviati i dati di Turni?

I dati dei turni vengono archiviati in una delle tre aree geografiche: Asia Pacifico (APAC), Unione Europea (UE) o Stati Uniti. Ogni area geografica archivia i dati in almeno due aree geografiche del data center di Azure per disponibilità elevata (HA) e ripristino di emergenza . Oggi, la geo Stati Uniti/America del Nord utilizza data center nelle Stati Uniti Centro Nord e Centro Sud. Per altre informazioni, vedere [Dove sono archiviati i dati dei clienti di Microsoft 365](/microsoft-365/enterprise/o365-data-locations).

Attualmente, Turni offre la residenza dei dati in Australia, Canada, Francia, Giappone e Regno Unito. Stiamo lavorando attivamente per espandere il supporto in altre posizioni.

## <a name="can-i-choose-where-shifts-data-is-stored"></a>È possibile scegliere dove archiviare i dati di Turni?

Quando configuri Teams per la prima volta, scegli un paese o un'area geografica, che viene impostata a livello di abbonamento. Turni rispetta questa selezione e usa le impostazioni locali e l'area geografica impostate in Teams se supportiamo tale area geografica. Se non ci troviamo ancora in quell'area geografica, archiviamo i dati in un'area nelle vicinanze che supportiamo. In futuro prevediamo di eseguire la migrazione dei dati esistenti, se archiviati in un'area vicina, nell'area di cui è stato eseguito il provisioning in Teams.

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>È possibile accedere ed esportare o eliminare i dati personali di un utente in Turni?

Turni è conforme al Regolamento generale sulla protezione dei dati (GDPR). Una richiesta formale da parte di una persona (nota come soggetto dei dati) di intraprendere un'azione sui propri dati personali è chiamata richiesta dell'interessato (DSR). È possibile trovare e agire sui dati personali in Turni in risposta a un DSR.

È possibile usare lo strumento Ricerca contenuto di eDiscovery nel Portale di conformità di Microsoft Purview per cercare ed esportare i dati di pianificazione e orologio in Excel. Per tutti gli altri dati di Turni, è possibile acquisire screenshot dei dati.

Per altre informazioni, vedere [Office 365 richieste dell'interessato per il GDPR e il CCPA](/microsoft-365/compliance/gdpr-dsr-office365).

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>Cosa succede ai dati di Turni se si disattiva Turni per l'organizzazione?

La disattivazione di Turni nell'organizzazione *non* elimina i dati. Se si disattiva Turni e successivamente si attiva Turni, i dati di Turni saranno ancora disponibili.

Se si elimina il tenant, tutti i dati di Turni vengono eliminati al termine del periodo di conservazione.

Non è possibile eliminare solo i dati di Turni. Se si elimina un team in Teams, i dati della pianificazione di Turni associati al team vengono eliminati al termine del periodo di conservazione. Per altre informazioni, vedere [Conservazione, eliminazione e distruzione dei dati in Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>È possibile recuperare una pianificazione di Turni eliminata?

È possibile recuperare una pianificazione eliminata se il gruppo di Microsoft 365 che lo esegue il backup (o il team in Teams) viene ripristinata.

Per impostazione predefinita, un gruppo di Microsoft 365 viene mantenuto per 30 giorni. Questo periodo di 30 giorni è denominato "eliminazione soft" perché è comunque possibile ripristinare il gruppo. Per altre informazioni, vedere [Ripristinare un gruppo di Microsoft 365 eliminato](/microsoft-365/admin/create-groups/restore-deleted-group?tabs=admin-center).

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>È possibile usare criteri di conservazione personalizzati per i dati di Turni?

Attualmente Turni non supporta criteri di conservazione personalizzati.

Per altre informazioni sui criteri di conservazione in Teams, vedere [Informazioni sulla conservazione per Teams](/microsoft-365/compliance/retention-policies-teams) e [Gestire i criteri di conservazione per Teams](../../retention-policies.md).

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>È possibile recuperare i dati di Turni per un utente la cui licenza è stata revocata?

Oggi non offriamo la possibilità di recuperare i dati per un utente la cui licenza è stata revocata. Questa funzionalità è qualcosa a cui stiamo lavorando.

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>Quale tipo di crittografia usa Turni per i dati archiviati e in transito?

I dati turni vengono crittografati inattivi dal database di Azure Cosmos e da Archiviazione di Azure. Per altre informazioni, vedere [Crittografia dei dati di Azure inattivi](/azure/security/fundamentals/encryption-atrest) e [Crittografia dei dati in Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest).

Turni segue le linee guida di Microsoft 365 per la crittografia dei dati in transito. Per altre informazioni, vedere [Crittografia dei dati in transito](/compliance/assurance/assurance-encryption-in-transit).

La crittografia dei dati a turni inattivi e in transito viene verificata annualmente dal controllo di conformità SOC2.

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>È possibile accedere a copie non modificabili dei dati di Turni?

Non archiviamo copie non modificabili dei dati di Turni. Ad esempio, un responsabile può apportare modifiche a una programmazione, ad esempio aggiungere note, modificare gli orari dei turni, assegnare attività e così via.

## <a name="can-shifts-data-be-edited"></a>I dati di Turni possono essere modificati?

Alcuni aspetti di Turni non possono essere modificati e alcuni aspetti che possono essere modificati. Ad esempio, i dettagli del turno, come le note e i colori, possono essere modificati in modo simile a come possono essere modificati nell'app Turni. Le richieste shift non possono essere modificate a meno che la richiesta non venga ritirata.

Per vedere quali campi sono stati modificati, è possibile cercare gli eventi Turni nel log di controllo di Microsoft 365. Per altre informazioni sugli eventi registrati per le attività di Turni nel log di controllo di Microsoft 365, vedere [Turni nelle attività di Teams](../../audit-log-events.md#shifts-in-teams-activities).

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>L'organizzazione usa un sistema di gestione della forza lavoro per la pianificazione. È possibile integrare e accedere ai dati di Turni?

Le API Shifts Graph consentono di integrare i dati di Turni con i sistemi di gestione della forza lavoro esterna (WFM). Per altre informazioni, vedi [API Shifts Graph](/graph/api/resources/shift).

Sono inoltre disponibili connettori Turni gestiti. Questi connettori consentono di integrare il sistema di WFM direttamente con Turni. Per altre informazioni sui connettori Turni e sui sistemi di WFM supportati, vedere [Connettori Turni](/microsoft-365/frontline/shifts-connectors).

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>I dati di Turni possono essere eliminati definitivamente dopo un periodo di tempo specificato?

Oggi non eliminiamo affatto i dati di Turni. Usando [le API Shifts Graph](/graph/api/resources/shift), è possibile [creare un'app usando Power Apps](/powerapps/maker/) per conservare i dati per un periodo di tempo specificato. Tuttavia, non supportiamo questa funzionalità in modo nativo.

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>I dati di Turni possono essere spostati in una migrazione da tenant a tenant?

Per eseguire la migrazione dei dati di Turni esistenti in un altro tenant, è necessario esportare le pianificazioni di Turni per un intervallo di date, modificare i nomi utente (se necessario) e quindi importare le pianificazioni nel tenant di destinazione. È possibile esportare fino a 100 giorni di dati di Turni alla volta. L'intervallo di date può essere nel passato o nel futuro. Se è necessario esportare i dati per un intervallo di tempo più lungo di 100 giorni, ripetere il processo.

Prima di eseguire la migrazione dei dati di Turni, assicurarsi che siano soddisfatti i requisiti seguenti:

- Il dominio tenant di destinazione, i team e i membri del team devono già esistere. La migrazione non crea team né modifica l'appartenenza o la proprietà del team.
- L'app Turni deve essere configurata nei team nel tenant di destinazione e avere una pianificazione vuota. Tenere presente che la migrazione non sostituisce o elimina i dati esistenti. Questo significa che se un team ha una pianificazione esistente, gli utenti potrebbero vedere turni duplicati o in conflitto, che devono essere risolti manualmente.
- Non viene eseguita la migrazione delle richieste aperte (ad esempio le richieste di scambio e di permesso) in attesa di approvazione. È consigliabile chiudere tutte le richieste aperte prima di iniziare la migrazione dei dati.

Ecco una panoramica dei passaggi per eseguire la migrazione dei dati di Turni a un altro tenant.

1. Nel tenant di origine, per ogni team, esportare la pianificazione di Turni:
    1. In Turni, nella pagina **Pianificazione**, passare ad **Altre opzioni (...)** >  **Programma di esportazione**.
    1. Selezionare un intervallo di date.
    1. Attivare **Esporta in un formato che può essere importato** e quindi selezionare **Esporta**. I dati della pianificazione di Turni verranno esportati in un file di Excel.
1. Nell'ambito della migrazione, se un membro del team cambia il dominio di posta elettronica, aggiornare manualmente il file di Excel per modificare il nome dell'entità utente (UPN) di tali utenti nel dominio tenant di destinazione.
1. Nel tenant di destinazione importare la pianificazione in ogni team.
    1. In Turni, nella pagina **Pianificazione**, passare ad **Altre opzioni (...)** >  **Programma di importazione**.
    1. Selezionare **Carica file**, passare al file di Excel del team e quindi selezionare **Apri**.

Per altre informazioni, vedere [Modello di Excel per Turni](https://support.microsoft.com/office/the-excel-template-for-shifts-6fc6a206-e7cc-4907-87b8-a296bae84ce3).

## <a name="related-articles"></a>Articoli correlati

- [Turni per Teams](../shifts-for-teams-landing-page.md)
- [Gestire l'app Turni](manage-the-shifts-app-for-your-organization-in-teams.md)
