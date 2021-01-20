---
title: Approvazioni disponibilità delle applicazioni in teams
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Informazioni sulla disponibilità di applicazioni approvate in Microsoft teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f916b4e794c862a05a42f075ca2f210a079ff42a
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909520"
---
# <a name="teams-approvals-app-availability"></a>Disponibilità delle app di approvazioni Teams

L'app approvazioni è disponibile come app personale per tutti gli utenti di Microsoft teams.
L'app approvazioni offre un modo semplice per offrire controllo, conformità, responsabilità e flussi di lavoro sia alle approvazioni strutturate che destrutturate in teams.

 ![Mostra l'app approvazioni](media/approvals-selection.png)

Gli utenti possono aggiungere l'app approvations per salvarla nella barra dei menu.

 ![Mostra l'app approvazioni con l'opzione pin](media/approvalApp-pin.png)

La prima approvazione creata dall'app approvazioni attiverà il provisioning della soluzione di approvazione nell'ambiente CDS (Common Data Service) predefinito. Le approvazioni create dall'app approvazioni verranno archiviate nell'ambiente CDS predefinito.

In questo articolo vengono illustrati i ruoli e i requisiti dell'app approvazione.

## <a name="required-permissions-and-licenses"></a>Autorizzazioni e licenze necessarie

Per usare l'app approvazioni, è necessario disporre delle autorizzazioni per gli elementi seguenti:

- Autorizzazioni per creare un database di Microsoft CDS.

- Un account in [Flow.Microsoft.com](https://flow.microsoft.com/)

- Ruolo di amministratore nell'ambiente di destinazione.

- Licenza per un [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), un Office 365 o una dinamica 365.

## <a name="storage-with-cds"></a>Archiviazione con CD

Common Data Model (CDM) è il linguaggio di dati condiviso usato dalle applicazioni aziendali e analitiche nei CD. È costituito da un set di uno schema di dati estensibile standardizzato pubblicato da Microsoft e dai nostri partner che consente la coerenza dei dati e il relativo significato tra le applicazioni e i processi aziendali. Leggi altre informazioni sul [modello di dati comune di Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).

Leggi altre informazioni sul [flusso di lavoro approvazione](https://docs.microsoft.com/power-automate/modern-approvals).

## <a name="approvals-teams-app-permissions"></a>Autorizzazioni per le app teams approvations

L'app Team approvations consente di accedere alle caratteristiche seguenti:

- Ricevere i messaggi e i dati forniti.

- Inviare messaggi e notifiche.

- Renderizzare le app personali e le finestre di dialogo senza un'intestazione fornita da teams.

- Accedere alle informazioni del profilo, ad esempio il nome, l'indirizzo di posta elettronica, il nome della società e la lingua preferita.

- Ricevere i messaggi e i dati forniti dai membri del team in un canale.

- Inviare messaggi e notifiche in un canale.

- Accedere alle informazioni del team:
  - nome del team
  - elenco canali
  - Roster (nomi e indirizzi di posta elettronica del membro del team).

- Usare le informazioni del team per contattarle.

## <a name="disable-the-approvals-app"></a>Disabilitare l'app approvazioni

L'app approvazioni è disponibile per impostazione predefinita. Puoi disabilitare l'app nell'interfaccia di amministrazione di teams.

  1. Accedere all'interfaccia di amministrazione di teams.

  2. Espandi le **app teams** e seleziona **Gestisci app**.

  3. Cercare l'app approvazioni.

![Mostra lo spostamento dell'interfaccia di amministrazione con le app teams > gestire le app evidenziate](media/manage-approval-apps.png)

  4. Selezionare approvazioni.

  5. Selezionare l'attiva/disattiva per disabilitare l'app per l'organizzazione.

![Mostra i dettagli per l'app approvazioni](media/approvals-details.png)

## <a name="retention-policy"></a>Criteri di conservazione

Le approvazioni create dall'app approvazioni sono archiviate nell'ambiente CDS predefinito, che in questo momento non supporta i backup. Leggi altre informazioni su come [eseguire il backup e il ripristino di ambienti-Power Platform \| Microsoft docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).

## <a name="auditing"></a>Controllo

L'app approvations registra gli eventi di controllo nel centro sicurezza e conformità di Microsoft 365. È possibile visualizzare il log di controllo.

1. Accedere al sito di conformità Microsoft 365.

2. Selezionare la sezione **controllo** .

3. Cercare attività in **attività di approvazione di Microsoft teams**.

È possibile cercare le attività seguenti:

- Creare una nuova richiesta di approvazione

- Visualizzare i dettagli delle richieste di approvazione

- Richiesta di approvazione approvata

- Richiesta di approvazione rifiutata

- Richiesta di approvazione annullata

- Richiesta di approvazione condivisa

- File allegato alla richiesta di approvazione

- Richiesta di approvazione riassegnata

- Aggiunta della firma elettronica alla richiesta di approvazione

Per accedere ad altre approvazioni di controllo in flusso, abilitare e configurare il controllo nell'ambiente predefinito per l'approvazione delle entità primarie, la richiesta di approvazione e la risposta all'approvazione. Le operazioni di creazione, aggiornamento ed eliminazione sono eventi controllabili per i record di approvazione. Leggi altre informazioni sui [dati di controllo e sulle attività degli utenti per la sicurezza e la conformità-Power Platform \| Microsoft docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).

Il controllo può essere ulteriormente personalizzato nel [Centro sicurezza e conformità di Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).

1. Per usare i report preconfigurati, accedere a Microsoft 365 sicurezza e conformità.

2. Selezionare **cerca & investigazione**.

3. Eseguire una ricerca nel log di controllo e selezionare la scheda **attività dinamiche 365** .

Leggi altre informazioni su [Microsoft dataverse e la registrazione delle attività delle app basate su modelli-Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).

## <a name="security"></a>Sicurezza

Dall'app Team approvations, gli utenti hanno accesso per creare nuove approvazioni e visualizzare le approvazioni che hanno inviato e ricevuto. Gli utenti non avranno accesso alle approvazioni create da altri, a meno che non siano un risponditore o un visualizzatore della richiesta.

> [!Note]
> A un utente verrà assegnato un ruolo di Visualizzatore di una richiesta se fa parte della chat o del canale in cui è stato creato l'approvazione. Non avranno la possibilità di intervenire sulla richiesta se non hanno dato questo ruolo al momento della creazione dell'approvazione.
