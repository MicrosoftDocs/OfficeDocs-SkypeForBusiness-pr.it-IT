---
title: Gestire l'accesso degli utenti a Dati analitici per l'istruzione
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Informazioni su come gestire l'accesso degli utenti a Dati analitici per l'istruzione in Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32bd773975ff6b67d28ab765ffa7c932e978af7d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145936"
---
# <a name="manage-user-access-to-education-insights"></a>Gestire l'accesso degli utenti a Dati analitici per l'istruzione

Questo documento illustra la procedura necessaria per gestire l'accesso degli utenti a [Dati analitici per l'istruzione in Microsoft Teams](class-insights.md).

È necessario fornire le autorizzazioni per i responsabili dell'istruzione, i dirigenti distrettuali, i presidi scolastici, i dirigenti scolastici, i consulenti, i responsabili delle aree di apprendimento, i direttori dei programmi, gli assistenti sociali e gli psicologi. Ai docenti viene *automaticamente* concessa l'autorizzazione quando sono proprietari di un team di classe.

Per fornire Dati analitici a livello di organizzazione, è necessario [importare i dati dal sistema informativo degli studenti (SIS)](education-insights-sis-data-sync.md) in modo che la struttura gerarchica del sistema didattico di Dati analitici sia mappata correttamente.

> [!NOTE]
> Solo l'amministratore globale può gestire l'accesso degli utenti a Dati analitici.

> [!TIP]
> È consigliabile abilitare Dati analitici per tutti i responsabili della didattica in modo che abbiano a disposizione i dati per conoscere ogni istituto e possano identificare rapidamente i problemi, nonché fornire supporto ai docenti. Anche se si esegue un progetto pilota, può comunque essere utile mantenere Dati analitici abilitato per tutti i responsabili della didattica, impostando però come destinatari delle comunicazioni solo il gruppo pilota di utenti.



## <a name="grant-permissions"></a>Concedere le autorizzazioni

* Aprire l'app Dati analitici, fare clic su **Impostazioni** e selezionare **Autorizzazioni utente**

:::image type="content" source="media/insights-user-permissions.png" alt-text="Impostazioni":::

* Selezionare **Aggiungi utenti**.
* Immettere il nome utente o l'indirizzo di posta elettronica di ogni utente.
* Selezionare il livello di autorizzazione:
  * **Accesso a tutte le organizzazioni** indica che l'utente può visualizzare tutte le unità organizzative a tutti i livelli.
  * **Accesso a istituti specifici** indica che l'utente può visualizzare gli istituti di istruzione selezionati. Iniziare a digitare e selezionare l'istituto nell'elenco. È possibile aggiungere più istituti contemporaneamente.
* Fare clic su **Aggiungi nuovi utenti**.

:::image type="content" source="media/insights-add-users.png" alt-text="Concedere le autorizzazioni":::

> [!NOTE]
> Fornire l'autorizzazione solo ai responsabili della didattica che ne hanno bisogno e solo alle unità organizzative di cui sono responsabili. Se non si è certi che sia necessaria l'autorizzazione dell'utente per una specifica organizzazione, consultare gli esperti in materia di privacy dell'istituto, ad esempio il personale legale o delle risorse umane.

## <a name="edit-permissions"></a>Modificare le autorizzazioni
* Selezionare l'utente specifico e quindi selezionare **Modifica autorizzazioni**.
* Aggiornare il livello di autorizzazione o l'elenco degli istituti e fare clic su **Aggiorna autorizzazioni**.

:::image type="content" source="media/insights-edit-users.png" alt-text="Modificare le autorizzazioni":::

## <a name="remove-permissions"></a>Rimuovere le autorizzazioni
* Selezionare gli utenti da rimuovere e quindi selezionare **Rimuovi utenti**.
* Questi utenti non potranno più accedere a Dati analitici a livello di organizzazione, ma possono comunque accedervi a livello di classe se sono proprietari di un team di classe.

:::image type="content" source="media/insights-remove-users.png" alt-text="Rimuovere le autorizzazioni":::
