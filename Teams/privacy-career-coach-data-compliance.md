---
title: Dati di Career Coach e informazioni sulla conformità
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ''
search.appverid: MET150
f1keywords: ''
description: Scopri le misure di privacy, conformità e estensione adottate da Microsoft per quanto riguarda l'istruzione o l'assistente alla carriera dell'EDU.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 1a21f3337ca9255572c25fd152f928c6444dc317
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242490"
---
# <a name="career-coach-data-and-compliance"></a>Dati e conformità di Career Coach

Questo articolo descrive come usare le funzionalità in-app, oltre ad altri strumenti che consentono di trovare e agire sui dati personali o sulle informazioni personali per rispondere alle richieste dell'interessato (DSR) in conformità agli obblighi del GDPR. Career Coach classifica ampiamente i dati in due categorie: contenuto del cliente e log generati dal sistema. In Assistente alla carriera, il contenuto dei clienti include dati utente, dati di configurazione del tenant e dati sulle attività degli studenti, mentre i log generati dal sistema includono log e dati correlati generati da Microsoft che aiutano Microsoft fornire servizi aziendali agli utenti.

## <a name="customer-content"></a>Contenuto del cliente

### <a name="user-data"></a>Dati utente

I dati degli utenti raccolti da Assistente alla carriera includono informazioni del profilo come obiettivi e progressi delle attività, campo di studio, anno scolastico, competenze salvate, carriere salvate, curriculum e trascrizioni caricati.

#### <a name="deleting-user-data"></a>Eliminazione dei dati utente

Segui questi passaggi per eliminare i dati utente da Career Coach:

1. Un amministratore globale deve [aprire un ticket](https://edusupport.microsoft.com/support?product_id=career_coach) di supporto che indichi chiaramente la richiesta di un'operazione DSR (data subject requests) del GDPR. ** Non è possibile limitare il set di dati o l'intervallo di tempo dell'eliminazione**.
2. La richiesta deve indicare chiaramente il tipo di dati che deve essere eliminato:
    1. Tutti i dati utente per il tenant.
    2. Dati utente per un utente specifico. Includere l'OID dell'utente (identificatori di oggetto) come parte della richiesta di eliminazione.
3. Una volta archiviato, il ticket di supporto verrà risolto dopo una settimana per soddisfare i criteri di conservazione minimi della conformità. È possibile annullare l'operazione durante questo periodo.
4. Dopo una settimana, il team assistente alla carriera elimina tutti i dati correlati al tenant. Microsoft supporto monitora il ticket e ti avviserà una volta completato il processo di eliminazione **, entro non più di 30 giorni**.

#### <a name="exporting-user-data"></a>Esportazione dei dati degli utenti

Segui questi passaggi per esportare i dati degli utenti da Career Coach:

1. [Apri Assistente alla](https://aka.ms/Career_Coach_App)  carriera e visualizza il tuo profilo.
1. Scorri fino alla sezione privacy e sicurezza.
1. Seleziona "Scarica" per esportare tutti i dati dei clienti per il tuo account.

### <a name="tenant-configuration-data"></a>Dati di configurazione tenant

I dati del tenant includono informazioni caricate o generate nell'ambito della configurazione dell'applicazione Assistente alla carriera. Questi dati includono le informazioni sul marchio di un tenant, il logo e l'icona di apprendimento, il catalogo dei corsi, l'URL dell'istituto linkedin, i campi dell'elenco di studi e tutti gli altri dati aggiunti durante la configurazione del tenant Assistente alla carriera nell'interfaccia di amministrazione di Teams.

#### <a name="deleting-tenant-configuration-data"></a>Eliminazione dei dati di configurazione del tenant

Segui questi passaggi per eliminare i dati di configurazione del tenant da Career Coach:

1. Un amministratore globale deve [aprire un ticket di supporto](https://edusupport.microsoft.com/support?product_id=career_coach) indicando chiaramente la richiesta di eliminare i dati di configurazione per il tenant.  **Non è possibile limitare il set di dati o l'intervallo di tempo dell'eliminazione**.
1. Una volta archiviato, il ticket di supporto verrà risolto dopo una settimana per soddisfare i criteri di conservazione minimi della conformità. È possibile annullare l'operazione durante questo periodo.
1. Dopo una settimana, il team assistente alla carriera elimina tutti i dati correlati al tenant. Microsoft supporto monitora il ticket e ti avviserà una volta completato il processo di eliminazione **, entro non più di 30 giorni**.

### <a name="student-activity-data"></a>Dati delle attività degli studenti

Assistente alla carriera archivia i dati delle attività degli studenti nella stessa posizione in  [cui Insights per l'istruzione](class-insights.md). I dati aggregati vengono raccolti nell'esperienza di analisi delle attività degli studenti di Assistente alla carriera. I dati di utilizzo degli studenti acquisiti per potenziare questa funzionalità vengono archiviati e conservati per un anno.

#### <a name="deleting-student-activity-data"></a>Eliminazione dei dati delle attività degli studenti

Per rimuovere i dati delle attività degli studenti per una persona o un tenant, seguire la procedura descritta in [Come eliminare i dati utente dagli approfondimenti dell'istruzione](class-insights.md#how-to-delete-user-data-from-education-insights).

## <a name="system-generated-logs"></a>Log generati dal sistema

I log generati dal sistema includono log e dati correlati generati da Microsoft che aiutano Microsoft fornire servizi aziendali agli utenti. I log generati dal sistema contengono principalmente dati con pseudonimi, ad esempio identificatori univoci (in genere un numero generato dal sistema) che non possono identificare autonomamente una persona ma vengono utilizzati per fornire i servizi aziendali agli utenti. Esempi di questi dati includono:

- Dati sull'utilizzo di prodotti e servizi, ad esempio i log attività degli utenti.
- Richieste di ricerca utente e dati di query.
- Dati generati da prodotti e servizi come prodotto della funzionalità di sistema e dell'interazione da parte di utenti o altri sistemi.

> [!NOTE]
> La possibilità di limitare o rettificare i dati nei log generati dal sistema non è supportata. I dati nei log generati dal sistema costituiscono azioni fattuali condotte all'interno del Microsoft dati cloud e diagnostici e le modifiche a tali dati compromettono la cronologia delle azioni e aumentano i rischi di frode e sicurezza. Career Coach conserva i registri generati dal sistema per 30 giorni.

### <a name="exporting-and-deleting-system-generated-logs"></a>Esportazione ed eliminazione di log generati dal sistema

L'amministratore globale tenant è l'unica persona all'interno dell'organizzazione che può accedere ai log generati dal sistema associati all'uso da parte di un utente specifico di servizi e applicazioni Office 365. Career Coach si allinea con [il processo di accesso ed esportazione dei log generati dal sistema forniti da Office 365](/compliance/regulatory/gdpr-dsr-Office365#accessing-and-exporting-system-generated-logs).

## <a name="more-information"></a>Altre informazioni

- [Introduzione a Career Coach per Microsoft Teams](career-coach.md)
- [Domande frequenti sulla privacy](https://privacy.microsoft.com/faq)
- [Microsoft prodotti e dati - Microsoft Privacy](https://privacy.microsoft.com/privacy-in-our-products)
- [impostazioni di privacy dell'account Microsoft](https://account.microsoft.com/account/privacy?refd=privacy.microsoft.com&ru=https%3A%2F%2Faccount.microsoft.com%2Fprivacy%2F%3Frefd%3Dprivacy.microsoft.com&destrt=privacy-dashboard)
