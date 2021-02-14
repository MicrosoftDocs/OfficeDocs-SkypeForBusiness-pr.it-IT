---
title: Controllo dell'accesso basato sui ruoli con il servizio Microsoft Teams Room Premium
author: dstrome
ms.author: dstrome
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
description: Informazioni sul controllo dell'accesso basato sui ruoli con il servizio gestito Microsoft Teams Rooms.
f1keywords: ''
ms.openlocfilehash: d673a20b122af876d95bac9d11a1db0433a396e4
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662601"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a>Controllo dell'accesso basato sui ruoli con il servizio gestito Sale di Microsoft Teams

Il controllo dell'accesso basato sui ruoli nel servizio gestito Microsoft Teams Rooms consente di gestire l'accesso degli utenti ai dati delle risorse della sala nell'organizzazione. Assegnando ruoli agli utenti del portale dei servizi, è possibile limitare gli elementi che possono visualizzare e modificare. Ogni ruolo ha un set di autorizzazioni che determina quali utenti con quel ruolo possono accedere e modificare all'interno dell'organizzazione.

Per creare, modificare o assegnare ruoli, l'account deve avere una delle autorizzazioni seguenti:

- Amministratore globale con Azure Active Directory (Azure AD)
- Amministratore del servizio gestito tramite il portale del servizio gestito Sale di Microsoft Teams

## <a name="what-is-a-role"></a>Che cos'è un ruolo?

Un ruolo definisce il set di autorizzazioni concesse agli utenti a cui è assegnato il ruolo. Per il momento, il servizio gestito Sale di Microsoft Teams ha tre ruoli **predefiniti:** Amministratore del servizio gestito, **Cliente potenziale** del sito e **Site Tech.** Coprono alcuni scenari comuni per gli utenti dell'organizzazione che potrebbero essere coinvolti nella gestione delle chat room.

Per visualizzare i ruoli, nella barra di spostamento sinistra del portale di servizio gestito di Microsoft Teams Rooms passare a Ruoli e quindi selezionare uno dei ruoli per visualizzare le proprietà, le autorizzazioni e le assegnazioni del ruolo.  

- **Proprietà:** nome, tipo di ruolo e descrizione
- **Autorizzazioni:** elenca le caratteristiche e il livello di autorizzazione a cui ha accesso il ruolo.
- **Assegnazioni:** elenco di assegnazioni di ruoli che definisce quali utenti hanno le autorizzazioni configurate sull'ambito degli account delle risorse della sala. Un ruolo può avere più assegnazioni e un utente può essere in più assegnazioni.

## <a name="built-in-roles"></a>Ruoli predefiniti

È possibile assegnare ruoli predefiniti a gruppi o utenti senza ulteriori configurazioni. Tenere presente che non è possibile eliminare o modificare il nome, la descrizione, il tipo o le autorizzazioni di un ruolo predefinito.

- **Amministratore del servizio gestito:** ha accesso completo al portale di servizio di Microsoft Teams Room Premium.
- **Cliente potenziale** del sito: organizza le sale, ha accesso ai report e può gestire i ticket. Non è possibile reimpostare il codice di registrazione o apportare modifiche alla configurazione del servizio.  
- **Site Tech:** gestisce i ticket per sale specifiche. Non ha le autorizzazioni per modificare il servizio o organizzare le sale nel servizio.

La tabella seguente riepiloga le operazioni che ogni ruolo può eseguire.

|Funzionalità |Autorizzazione |Amministratore del servizio gestito  |Cliente potenziale sito  |Site Tech  |
|---------|---------|---------|---------|---------|
|Sale     |Visualizzare        |&#10004;           |&#10004;           |&#10004;  |
|    |Modifica         |&#10004;           |&#10004;           |&#10004; |
|    |Reimposta codice         |&#10004;           |         ||
|    |Codice per il download         |&#10004;           |&#10004;          |&#10004; |
|    |Annullare la registrazione         |&#10004;           |&#10004;           |&#10004; |
|Gestione dei gruppi   |Create         |&#10004;           |           ||
|    |Visualizzare       |&#10004;          |&#10004;           ||
|    |Modifica         |&#10004;           |           ||
|Aggiornare la gestione dello squillo    |Create         |&#10004;           |           ||
|    |Visualizzare         |&#10004;           |           ||
|    |Modifica         |&#10004;           |           ||
|Report   |Visualizzare        |&#10004;           |&#10004;           ||
|Gestione dei ticket   |Crea evento imprevisto cliente         |&#10004;           |&#10004;           |&#10004;  |
|    |Visualizzare         |&#10004;           |&#10004;           |&#10004;  |
|    |Aggiornamento         |&#10004;           |&#10004;           |&#10004;  |
|Impostazioni del servizio gestito Sale di Microsoft Teams    |Visualizzare         |&#10004;           |         ||
|    |Modifica        |&#10004;           |         ||
|Gestione ruoli    |Visualizzare         |&#10004;           |         ||
|    |Modifica         |&#10004;           |         ||

## <a name="assign-a-role"></a>Assegnare un ruolo

Per assegnare ruoli, è necessario essere un amministratore globale o un amministratore del servizio gestito.

1. Nella barra di spostamento sinistra del portale del servizio gestito Sale di Microsoft Teams, passare a **Ruoli**  >  **impostazioni.**

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="Screenshot della pagina di controllo di accesso che mostra i ruoli":::

2. Selezionare il ruolo da assegnare.
3. Nel riquadro dei ruoli seleziona **Aggiungi**  >  **attività.**

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="Screenshot dell'opzione Aggiungi per aggiungere un ruolo.":::

4. Nella pagina **Impostazioni generali,** in **Proprietà assegnazione,** immettere un nome per l'assegnazione. La descrizione è facoltativa. Scegliere **Avanti.**
5. Nella **casella** Cerca utente  o gruppo di sicurezza della pagina Membri immettere il nome di un utente o gruppo di sicurezza nel tenant a cui si vogliono concedere le autorizzazioni, quindi completare la selezione. Scegliere **Avanti.** 
6. Nella **casella** Cerca chat room o gruppo di chat **room** della pagina Ambito digitare il nome di una chat room o di un gruppo di chat room che l'utente sarà autorizzato a gestire. Scegliere **Avanti.**
7. Nella pagina **Fine** rivedere i dettagli dell'assegnazione. Se sei soddisfatto della configurazione, scegli **Aggiungi attività.** Se si vuole modificare una sezione, usare il **pulsante** Precedente o selezionare il passaggio nel riquadro di spostamento sinistro.  

## <a name="related-topics"></a>Argomenti correlati

- [Servizio gestito Microsoft Teams Rooms](microsoft-teams-rooms-premium.md)
