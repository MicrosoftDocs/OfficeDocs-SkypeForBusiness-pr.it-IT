---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: ab375a876eb62e5f41e5dd7cda3743d4010b95ff
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593663"
---
Prima di iniziare, verificare di avere i prerequisiti seguenti:

- Blue Yonder WFM versione 2020.3, 2021.1 o 2021.2.

    > [!NOTE]
    > Se si ha Blue Yonder WFM 2020.3 o 2021.1, applicare la patch 2020.3.0.4 o 2021.1.0.3. Questa patch risolve un problema per cui gli utenti ottengono un messaggio di errore persistente in Turni. Risolve anche un problema che impedisce agli utenti di aggiornare la disponibilità in Turni.

- Nome e URL dell'account del servizio WFM Blue Yonder:

    - URL di autenticazione federata
    - URL di autenticazione dei cookie
    - URL self-service dei dipendenti
    - URL api Web di vendita al dettaglio
    - Site manager API URL
    - URL API di amministrazione

    Se non si hanno queste informazioni, contattare il supporto di Blue Yonder. L'account viene creato a livello aziendale radice da un amministratore aziendale blue yonder. Deve avere accesso API, Amministratore client e Store Manager. L'account e la password sono necessari per creare una connessione.
- L'autenticazione SSO federata è abilitata nell'ambiente Blue Yonder WFM. Contattare il supporto di Blue Yonder per assicurarsi che il servizio SSO federato sia abilitato. Saranno necessarie le informazioni seguenti:

    - federatedSSOValidationService: `https://wfmconnector.teams.microsoft.com/api/v1/fedauth/{tenantId}/6A51B888-FF44-4FEA-82E1-839401E9CD74/authorize` dove {tenantId} è il tuo tenantId
     - proxyHeader: X-MS-AuthToken

- Almeno un team è configurato in Teams.
- L'account Microsoft 365 di sistema è stato aggiunto come proprietario del team a tutti i team di cui si vuole eseguire il mapping.</br> [Creare questo account in Microsoft 365](/microsoft-365/admin/add-users/add-users) assegnare una licenza Microsoft 365 licenza. Quindi, aggiungere l'account come proprietario del team a tutti i team di cui si vuole eseguire il mapping. Il connettore Turni usa questo account durante la sincronizzazione delle modifiche dei turni da Blue Yonder WFM.

    È consigliabile creare un account specifico per questo scopo e non usare l'account utente.