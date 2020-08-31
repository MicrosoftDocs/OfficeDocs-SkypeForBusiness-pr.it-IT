---
title: Controllo dell'accesso basato sui ruoli con il servizio Microsoft teams room Premium
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni sul controllo di accesso basato sui ruoli con il servizio Managed Rooms di Microsoft teams.
f1keywords: ''
ms.openlocfilehash: 2f3886d7f7f59521028b87f05ffedfaa1fae9ac2
ms.sourcegitcommit: 206e01b72218f57e68823dc23b7ca28bce7cb3bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300290"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a>Controllo dell'accesso basato sui ruoli con il servizio Managed Rooms di Microsoft Teams

Il controllo di accesso basato sui ruoli (RBAC) nel servizio Managed Rooms di Microsoft teams consente di gestire l'accesso degli utenti ai dati delle risorse della sala nell'organizzazione. Assegnando ruoli agli utenti del portale del servizio, è possibile limitarne la visualizzazione e la modifica. Ogni ruolo include un set di autorizzazioni che determinano gli utenti con cui il ruolo può accedere e modificare all'interno dell'organizzazione.

Per creare, modificare o assegnare ruoli, l'account deve avere una delle autorizzazioni seguenti:

- Amministratore globale tramite Azure Active Directory (Azure AD)
- Amministratore del servizio gestito tramite il portale del servizio Managed Rooms di Microsoft Teams

## <a name="what-is-a-role"></a>Che cos'è un ruolo?

Un ruolo definisce il set di autorizzazioni concesse agli utenti assegnati a tale ruolo. Per il momento, il servizio Managed Rooms di Microsoft teams include tre ruoli predefiniti: **amministratore del servizio gestito**, **Lead del sito**e **tecnologia del sito**. Coprono alcuni scenari comuni per gli utenti dell'organizzazione che potrebbero essere coinvolti nella gestione delle sale.

Per visualizzare i ruoli, nella barra di spostamento sinistra del portale del servizio gestito di Microsoft teams rooms, accedere a **ruoli**e quindi selezionare uno dei ruoli per visualizzare le proprietà, le autorizzazioni e le assegnazioni del ruolo.  

- **Proprietà**: nome, tipo di ruolo e descrizione
- **Autorizzazioni**: elenca le caratteristiche e il livello di autorizzazioni a cui il ruolo ha accesso.
- **Assegnazioni**: elenco delle assegnazioni di ruolo che definiscono gli utenti che dispongono delle autorizzazioni configurate per l'ambito degli account delle risorse della sala. Un ruolo può avere più assegnazioni e un utente può essere in più assegnazioni.

## <a name="built-in-roles"></a>Ruoli predefiniti

È possibile assegnare ruoli predefiniti a gruppi o utenti senza ulteriori configurazioni. Tieni presente che non puoi eliminare o modificare il nome, la descrizione, il tipo o le autorizzazioni di un ruolo predefinito.

- **Amministratore del servizio gestito**: ha accesso completo al portale del servizio Microsoft teams room Premium.
- **Lead sito**: organizza le sale, ha accesso ai report e può gestire i ticket. Non è possibile reimpostare la chiave di registrazione o apportare modifiche alla configurazione del servizio.  
- **Sito Tech**: gestisce i biglietti per camere specifiche. Non dispone delle autorizzazioni per modificare il servizio o organizzare le camere nel servizio.

La tabella seguente riepiloga le operazioni che ogni ruolo può eseguire.

|Funzionalità |Autorizzazione |Amministratore del servizio gestito  |Lead sito  |Tecnologia del sito  |
|---------|---------|---------|---------|---------|
|Sale     |Visualizzazione        |&#10004;           |&#10004;           |&#10004;  |
|    |Modificare         |&#10004;           |&#10004;           |&#10004; |
|    |Tasto Reset         |&#10004;           |         ||
|    |Tasto download         |&#10004;           |&#10004;          |&#10004; |
|    |Annullano         |&#10004;           |&#10004;           |&#10004; |
|Gestione dei gruppi   |Create         |&#10004;           |           ||
|    |Visualizzazione       |&#10004;          |&#10004;           ||
|    |Modificare         |&#10004;           |           ||
|Gestione delle suonerie di aggiornamento    |Create         |&#10004;           |           ||
|    |Visualizzazione         |&#10004;           |           ||
|    |Modificare         |&#10004;           |           ||
|Rapporti   |Visualizzazione        |&#10004;           |&#10004;           ||
|Gestione ticket   |Creare un incidente cliente         |&#10004;           |&#10004;           |&#10004;  |
|    |Visualizzazione         |&#10004;           |&#10004;           |&#10004;  |
|    |Aggiornamento         |&#10004;           |&#10004;           |&#10004;  |
|Impostazioni del servizio Managed Rooms di Microsoft Teams    |Visualizzazione         |&#10004;           |         ||
|    |Modificare        |&#10004;           |         ||
|Gestione dei ruoli    |Visualizzazione         |&#10004;           |         ||
|    |Modificare         |&#10004;           |         ||

## <a name="assign-a-role"></a>Assegnare un ruolo

Per assegnare ruoli, è necessario essere un amministratore globale o un amministratore del servizio gestito.

1. Nella barra di spostamento sinistra del portale dei servizi gestiti di Microsoft teams rooms, vedere ruoli **delle impostazioni**  >  **Roles**.

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="Screenshot della pagina di controllo di Access che mostra i ruoli":::

2. Selezionare il ruolo che si vuole assegnare.
3. Nel riquadro ruolo selezionare **assegnazioni**  >  **Aggiungi**.

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="Screenshot dell'opzione Aggiungi per aggiungere un ruolo.":::

4. Nella pagina **Impostazioni generali** , in **Proprietà assegnazione**, immettere un nome per l'assegnazione. La descrizione è facoltativa. Scegliere **Avanti.**
5. Nella casella **Cerca utente o gruppo di sicurezza** della pagina **membri** immettere il nome di un utente o di un gruppo di sicurezza nel tenant a cui si vogliono assegnare le autorizzazioni e quindi completare la selezione. Scegliere **Avanti**. 
6. Nella pagina **ambito** nella casella Cerca in **sala o** in un gruppo di chat digitare il nome di un gruppo di chat room o room che l'utente potrà gestire. Scegliere **Avanti**.
7. Nella pagina **fine** esaminare i dettagli dell'assegnazione. Se si è soddisfatti della configurazione, scegliere **Aggiungi assegnazione**. Se si vuole modificare una sezione, usare il pulsante **precedente** o selezionare il passaggio nella barra di spostamento sinistra.  

## <a name="related-topics"></a>Argomenti correlati

- [Servizio Managed Rooms di Microsoft Teams](microsoft-teams-rooms-premium.md)
