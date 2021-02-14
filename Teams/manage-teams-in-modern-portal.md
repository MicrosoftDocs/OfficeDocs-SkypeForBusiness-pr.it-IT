---
title: Gestire i team nell'interfaccia di amministrazione di Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Informazioni su come visualizzare o aggiornare i team che l'organizzazione ha configurato per la collaborazione nell'interfaccia di amministrazione di Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c736cf17d263f097e97b32f856bc83cf2fe42a35
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814555"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Gestire i team nell'interfaccia di amministrazione di Microsoft Teams
==========================================

## <a name="overview"></a>Panoramica

Questo articolo fornisce una panoramica degli strumenti di gestione per Teams nell'interfaccia di amministrazione di Microsoft Teams.

Come amministratore, potrebbe essere necessario visualizzare o aggiornare i team che l'organizzazione ha configurato per la collaborazione oppure potrebbe essere necessario eseguire azioni correttive, ad esempio assegnare i proprietari ai team senza proprietario. È possibile gestire i team usati nell'organizzazione tramite il modulo Microsoft Teams PowerShell e l'interfaccia di amministrazione di Microsoft Teams. È possibile accedere all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> . Per le funzionalità di amministrazione complete con questi due set di strumenti, è consigliabile assicurarsi di avere uno dei ruoli seguenti:

- Amministratore globale
- Amministratore del servizio Teams

Per altre informazioni sui ruoli di amministratore in Teams, vedere Usare i ruoli di amministratore di [Microsoft Teams](using-admin-roles.md)per gestire Teams e su come usare i cmdlet di PowerShell per la gestione dei team nella guida di riferimento ai cmdlet di [Microsoft Teams.](https://docs.microsoft.com/powershell/teams/?view=teams-ps)



## <a name="teams-overview-grid"></a>Griglia di panoramica di Teams

Gli strumenti di gestione per i team sono sotto il **nodo Team** nell'interfaccia di amministrazione di Microsoft Teams. Nell'interfaccia di amministrazione selezionare **Teams**  >  **Gestire i team.** Ogni team è supportato da un gruppo di Microsoft 365 e questo nodo offre una visualizzazione dei gruppi abilitati per Microsoft Teams nell'organizzazione.

![Screenshot della griglia di panoramica di Teams](media/manage-teams-in-modern-portal-grid.png)  

Nella griglia vengono visualizzate le proprietà seguenti:

- **Nome del team**
- **Canali:** un conteggio di tutti i canali del team, incluso il canale generale predefinito.
- **Membri del** team: numero totale di utenti, inclusi proprietari, guest e membri del tenant.
- **Proprietari:** numero di proprietari di questo team.
- **Guest:** numero di utenti guest B2B di Azure Active Directory che sono membri di questo team.
- **Privacy:** visibilità/AccessType del gruppo di Microsoft 365 di supporto.
- **Stato:** stato Archiviato o Attivo per questo team. Altre informazioni sull'archiviazione dei team in [Archivia o ripristina un team.](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)
- **Descrizione:** descrizione del gruppo di Microsoft 365 di supporto.
- **Classificazione:** classificazione (se usata nell'organizzazione) assegnata al gruppo di Microsoft 365 di backup. Per altre informazioni sulle classificazioni, [vedere Creare classificazioni per i gruppi di Office nell'organizzazione.](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- **GroupID:** l'ID Gruppo univoco del gruppo di Microsoft 365 di supporto.

> [!NOTE]
> Se non tutte queste proprietà sono visualizzate nella griglia, fare clic **sull'icona Modifica** colonne. Nel riquadro **Modifica colonne** è possibile usare gli interruttori per attivare o disattivare le colonne nella griglia. Al termine, fare clic su **Applica.**

### <a name="add"></a>Aggiungi

Per aggiungere un nuovo team, fare clic su **Aggiungi.** Nel riquadro **Aggiungi un** nuovo team assegnare un nome e una descrizione al team, specificare se si vuole impostare un team privato o pubblico e impostare la classificazione.

> [!NOTE]
> I nuovi team creati possono essere gestiti immediatamente nell'interfaccia di amministrazione di Teams, a differenza dell'esperienza in altri client come Outlook.

### <a name="edit"></a>Modifica

Per modificare le impostazioni specifiche del gruppo e del team, selezionare il team facendo clic a sinistra del nome del team e quindi **selezionando Modifica.**

### <a name="archive"></a>Archivia

È possibile archiviare un team. Archiviando un team, il team entra in modalità di sola lettura all'interno di Teams. Gli amministratori possono archiviare e annullare l'archiviazione dei team per conto dell'organizzazione nell'interfaccia di amministrazione. 

### <a name="delete"></a>Elimina

L'eliminazione di un team è un'eliminazione recisa del team e del gruppo di Microsoft 365 corrispondente. Per ripristinare un team eliminato per errore, seguire le istruzioni in [Ripristinare un gruppo eliminato.](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)

### <a name="search"></a>Ricerca

La ricerca attualmente supporta la stringa "Inizia con" ed esegue la ricerca nel **campo Nome** team.

## <a name="team-profile"></a>Profilo del team

Puoi passare alla pagina del profilo del team di qualsiasi team dalla griglia di panoramica dei team principali facendo clic sul nome del team. La pagina del profilo del team mostra i membri, i proprietari e i guest che appartengono al team (e il gruppo di Microsoft 365 di supporto), nonché i canali e le impostazioni del team. Dalla pagina del profilo del team è possibile:

- Aggiungere o rimuovere membri e proprietari.
- Aggiungere o rimuovere canali (tenere presente che non è possibile rimuovere il canale Generale).
- Modificare le impostazioni del team e del gruppo.
 
![Screenshot di un profilo del team di esempio](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a>Apportare modifiche ai team

Nella pagina del profilo del team è possibile modificare gli elementi seguenti di un team:

- **Membri:** aggiungere o rimuovere membri e alzare o abbassare di livello i proprietari.
- **Canali:** aggiungere nuovi canali e modificare o rimuovere canali esistenti. Ricorda che non puoi eliminare il canale generale predefinito.
- **Nome del team**
- **Descrizione**
- **Privacy:** consente di specificare se il team è pubblico o privato.
- **Classificazione:** supportata dalle classificazioni dei gruppi di Microsoft 365. Scegliere **Informazioni** riservate, **Altamente** riservato o **Generale.**
- **Impostazioni conversazioni: consente** di specificare se i membri possono modificare ed eliminare i messaggi inviati.
- **Impostazioni dei** canali: specificare se i membri possono creare nuovi canali e modificare quelli esistenti e aggiungere, modificare e rimuovere schede, connettori e app.

Le modifiche apportate a un team vengono registrate. Se si modificano le impostazioni del gruppo (modificando il nome, la descrizione, la foto, la privacy, la classificazione o i membri del team), le modifiche vengono attribuite all'utente tramite la pipeline di controllo. Se si eseguono azioni su impostazioni specifiche di Teams, le modifiche vengono rilevate e attribuite all'utente nel canale Generale del team.

## <a name="troubleshooting"></a>Risoluzione dei problemi

**Problema: Teams mancante nella griglia Panoramica team**

Alcuni team non sono presenti nell'elenco dei team nella griglia di panoramica di Teams.

**Causa:** questo problema si verifica quando il team non è stato profilo correttamente (o non ancora) dal sistema, il che può portare a una proprietà mancante per il riconoscimento.

**Soluzione: impostare manualmente la proprietà sul valore corretto tramite MS Graph**

Sostituire **{groupid}** nella query per l'effettivo GroupId in questione, che è possibile ottenere tramite la powershell di Exchange Online, con il cmdlet **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)",** come attributo "**ExternalDirectoryObjectId**".

1. Esplora [grafici di](https://developer.microsoft.com/graph/graph-explorer)Access.

2. Accedere a Esplora grafici nel menu a sinistra.

3. Modificare la riga della query in: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid} .

4. Aggiungere il valore seguente nel corpo della richiesta: {"resourceProvisioningOptions": ["Team"]}.

5. Eseguire la query in alto a destra.

6. Verificare che il team sia visualizzato correttamente nell'interfaccia di amministrazione di Microsoft Teams - Panoramica del team.

## <a name="learn-more"></a>Altre informazioni

- [Informazioni di riferimento per i cmdlet di Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [Usare i ruoli di amministratore di Teams per gestire Teams](using-admin-roles.md)
- [Pianificare la gestione del ciclo di vita in Teams](plan-teams-lifecycle.md)
