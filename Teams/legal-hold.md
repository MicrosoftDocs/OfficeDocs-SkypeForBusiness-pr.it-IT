---
title: Inserire un utente o un team di Microsoft teams in blocco legale
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Imparerai a inserire un utente o un team di Microsoft teams in blocco legale usando il centro conformità & sicurezza e scopri cosa richiede un blocco legale in base ai requisiti dei dati.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 25bd8e235be79ed805a854cbda2b4947f1c1269b
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968037"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Inserire un utente o un team di Microsoft teams in blocco legale
==================================================

Per inserire un utente o un team in blocco legale, passare al [centro conformità & sicurezza](https://go.microsoft.com/fwlink/?linkid=854628). Quando si crea un nuovo caso, viene visualizzata l'opzione per posizionare le cassette postali o i siti in attesa.

> [!NOTE]
> L'immissione di un utente in blocco non inserisce automaticamente un gruppo in attesa o viceversa.

> [!NOTE]
> Non è ancora supportata la configurazione per l'esenzione legale dei messaggi del canale privato. È supportata la riserva legale dei file condivisi nei canali privati.

> [!IMPORTANT]
> Quando un utente o un gruppo viene messo in attesa, verranno mantenute tutte le copie del messaggio. Esempio: Clay ha inviato un messaggio in un canale e quindi ha modificato il messaggio. In uno scenario di blocco vengono mantenute entrambe le copie del messaggio. Senza blocco legale, viene mantenuto solo il messaggio più recente.

Nella figura seguente è presente un'indagine che prevede l'uso di argilla. Clay è un membro del team broker-dealer.

Se avevamo bisogno di tenere legale tutte le posizioni che Clay avrebbe potuto discutere dei piani di brokeraggio, assicurati che il sito di SharePoint del team venga aggiunto all'elenco dei siti di blocco legale, oltre al sito di OneDrive for business di Clay.

![Screenshot della finestra di dialogo Crea un nuovo blocco.](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image3.png)

Per ricapitolare, usare la tabella seguente per capire cosa occorre inserire in blocco legale in base ai requisiti dei dati:

|Scenario  |Cosa posizionare in blocco  |
|---------|---------|
|**Chat private di Microsoft Teams**     |Cassetta postale dell'utente         |
|**Chat di canale di Microsoft Teams**    |Cassetta postale del gruppo usata per il team         |
|**Contenuto di Microsoft Teams (ad esempio wiki, file)**     |Sito di SharePoint usato dal team         |
|**Contenuto privato**     |Sito di OneDrive for business dell'utente         |
