---
title: Controllo dell'accesso basato sui ruoli nel portale di gestione di Microsoft Teams Pro
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni sul controllo dell'accesso basato sui ruoli nel portale di gestione di Microsoft Teams Rooms Pro.
f1keywords: ''
ms.openlocfilehash: 2cc62699cb4f59c3f80726f18bc80323557f966f
ms.sourcegitcommit: baf29d244b428712052553f9e4484e72e727247e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2022
ms.locfileid: "69046893"
---
# <a name="role-based-access-control-in-the-microsoft-teams-pro-management-portal"></a>Controllo dell'accesso basato sui ruoli nel portale di gestione di Microsoft Teams Pro

Il controllo degli accessi in base ai ruoli nel portale di gestione Microsoft Teams Rooms Pro consente di gestire l'accesso degli utenti ai dati delle risorse delle chat room nell'organizzazione. Assegnando ruoli agli utenti del portale, è possibile limitare gli elementi che possono visualizzare e modificare. Ogni ruolo ha un set di autorizzazioni che determinano quali utenti con quel ruolo possono accedere e modificare all'interno dell'organizzazione.

Per creare, modificare o assegnare ruoli, l'account deve avere una delle autorizzazioni seguenti:

- Amministratore globale tramite Azure Active Directory (Azure AD)
- Amministratore del servizio gestito tramite il portale di gestione Microsoft Teams Rooms Pro

## <a name="what-is-a-role"></a>Che cos'è un ruolo?

Un ruolo definisce il set di autorizzazioni concesse agli utenti assegnati a tale ruolo. Per il momento, il portale di gestione di Microsoft Teams Rooms Pro ha tre ruoli predefiniti: **Amministratore del servizio gestito**, **Cliente potenziale del sito** e **Tech del sito**. Trattano alcuni scenari comuni per gli utenti dell'organizzazione che potrebbero essere coinvolti nella gestione delle chat room.

Per visualizzare i ruoli, nel riquadro di spostamento sinistro del portale di gestione Microsoft Teams Rooms Pro passare a **Ruoli** e quindi selezionare uno dei ruoli per visualizzare le proprietà, le autorizzazioni e le assegnazioni del ruolo.  

- **Proprietà**: nome, tipo di ruolo e descrizione
- **Autorizzazioni**: elenca le caratteristiche e il livello di autorizzazioni a cui ha accesso il ruolo.
- **Assegnazioni**: elenco di assegnazioni di ruoli che definiscono quali utenti hanno le autorizzazioni configurate per l'ambito degli account delle risorse della chat room. Un ruolo può avere più assegnazioni e un utente può essere in più assegnazioni.

## <a name="built-in-roles"></a>Ruoli predefiniti

È possibile assegnare ruoli predefiniti a gruppi o utenti senza ulteriori configurazioni. Tenere presente che non è possibile eliminare o modificare il nome, la descrizione, il tipo o le autorizzazioni di un ruolo incorporato.

- **Amministratore del servizio gestito**: ha accesso completo al portale di gestione di Microsoft Teams Room Pro.
- **Cliente potenziale del sito**: organizza sale, ha accesso ai report e può gestire i ticket. Non è possibile reimpostare il codice di registrazione o apportare modifiche alle configurazioni dei servizi.  
- **Site Tech**: gestisce i biglietti per stanze specifiche. Non dispone delle autorizzazioni per modificare le configurazioni dei servizi o organizzare le sale.

La tabella seguente riepiloga le operazioni che ogni ruolo può eseguire.

|Funzionalità |Autorizzazione |Amministratore del servizio gestito  |Cliente potenziale del sito  |Tech del sito  |
|---------|---------|---------|---------|---------|
|Camere     |Visualizzare        |&#10004;           |&#10004;           |&#10004;  |
|    |Modificare         |&#10004;           |&#10004;           |&#10004; |
|    |Tasto REIMPOSTA         |&#10004;           |         ||
|    |Chiave di download         |&#10004;           |&#10004;          |&#10004; |
|    |Annullare la registrazione         |&#10004;           |&#10004;           |&#10004; |
|Gestione dei gruppi   |Create         |&#10004;           |           ||
|    |Visualizzare       |&#10004;          |&#10004;           ||
|    |Modificare         |&#10004;           |           ||
|Gestione dell'anello di aggiornamento    |Create         |&#10004;           |           ||
|    |Visualizzare         |&#10004;           |           ||
|    |Modificare         |&#10004;           |           ||
|Rapporti   |Visualizzare        |&#10004;           |&#10004;           ||
|Gestione dei ticket   |Crea evento imprevisto del cliente         |&#10004;           |&#10004;           |&#10004;  |
|    |Visualizzare         |&#10004;           |&#10004;           |&#10004;  |
|    |Aggiornamento         |&#10004;           |&#10004;           |&#10004;  |
|impostazioni del servizio gestione Microsoft Teams Rooms Pro    |Visualizzare         |&#10004;           |         ||
|    |Modificare        |&#10004;           |         ||
|Gestione dei ruoli    |Visualizzare         |&#10004;           |         ||
|    |Modificare         |&#10004;           |         ||

## <a name="create-a-custom-role"></a>Creare un ruolo personalizzato

Se i ruoli predefiniti non soddisfano le esigenze dell'organizzazione, è possibile creare un ruolo e configurarne le autorizzazioni in base alle esigenze. Per creare un ruolo, è necessario essere un amministratore globale o un amministratore del servizio gestito. 

1. Nel riquadro di spostamento sinistro del portale di gestione di Microsoft Teams Rooms Pro passare a **Ruoli impostazioni** > .
2. Selezionare **Crea ruolo**.
3. Nella pagina **Impostazioni generali** , in **Proprietà ruolo**, immettere un nome per il ruolo. In **Descrizione** immettere i dettagli su questo ruolo. Scegliere **Avanti**.
4. Nella pagina **Autorizzazioni** , in **Autorizzazioni ruolo**, scegliere le autorizzazioni per questo ruolo selezionando le caselle di controllo appropriate. Scegliere **Avanti** per creare la prima assegnazione per questo ruolo.
5. Nella pagina **Assegnazioni** , in **Proprietà assegnazione**, immettere un nome per l'assegnazione. La descrizione è facoltativa. In **Impostazioni di notifica** selezionare la casella di controllo **Notifiche tramite posta elettronica** se gli utenti di questo ruolo devono ricevere notifiche tramite posta elettronica dal servizio nelle sale nell'ambito di questa assegnazione. Scegliere **Avanti**.
6. Nella casella **Cerca utente o gruppo di sicurezza** della pagina **Membri** immettere il nome di un utente o di un gruppo di sicurezza nel tenant a cui assegnare le autorizzazioni e quindi completare la selezione. Scegliere **Avanti**. 
7. Nella casella **Cerca gruppo di chat room o gruppo** di chat room nella pagina **Ambito** digitare il nome di un gruppo di chat room o di una chat room che l'utente sarà autorizzato a gestire. Scegliere **Avanti**.
8. Nella pagina **Fine** esaminare i dettagli del ruolo e dell'assegnazione. Se si è soddisfatti della configurazione, scegliere **Aggiungi nuovo ruolo**. Se si vuole modificare una sezione, usare il pulsante **Precedente** o selezionare il passaggio nel riquadro di spostamento sinistro.  

## <a name="assign-a-role"></a>Assegnare un ruolo

Per assegnare i ruoli, è necessario essere un amministratore globale o un amministratore del servizio gestito o avere un ruolo con autorizzazioni di gestione dei ruoli.

1. Nel riquadro di spostamento sinistro del portale di gestione di Microsoft Teams Rooms Pro passare a **Ruoli impostazioni** > .

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="Screenshot della pagina di controllo di Access che mostra i ruoli.":::

2. Selezionare il ruolo da assegnare.
3. Nel riquadro dei ruoli selezionare **Aggiungi assegnazioni** > .

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="Screenshot dell'opzione Aggiungi per aggiungere un ruolo.":::

4. Nella pagina **Impostazioni generali** , in **Proprietà assegnazione**, immettere un nome per l'assegnazione. La descrizione è facoltativa. In **Impostazioni di notifica** selezionare la casella di controllo **Notifiche tramite posta elettronica** se gli utenti di questo ruolo devono ricevere notifiche tramite posta elettronica dal servizio nelle sale **nell'ambito** di questa assegnazione. Scegliere **Avanti**. 
5. Nella casella **Cerca utente o gruppo di sicurezza** della pagina **Membri** immettere il nome di un utente o di un gruppo di sicurezza nel tenant a cui assegnare le autorizzazioni e quindi completare la selezione. Scegliere **Avanti**. 
6. Nella casella **Cerca gruppo di chat room o gruppo** di chat room nella pagina **Ambito** digitare il nome di un gruppo di chat room o di una chat room che l'utente sarà autorizzato a gestire. Scegliere **Avanti**.
7. Nella pagina **Fine** esaminare i dettagli dell'attività. Se si è soddisfatti della configurazione, scegliere **Aggiungi attività**. Se si vuole modificare una sezione, usare il pulsante **Precedente** o selezionare il passaggio nel riquadro di spostamento sinistro.  

## <a name="related-topics"></a>Argomenti correlati

- [portale di gestione Microsoft Teams Rooms Pro](rooms-pro-management.md)
