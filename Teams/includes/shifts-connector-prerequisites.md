---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: ab375a876eb62e5f41e5dd7cda3743d4010b95ff
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2022
ms.locfileid: "64593663"
---
Prima di iniziare, assicurarsi di avere i prerequisiti seguenti:

- Blue Yonder WFM versione 2020.3, 2021.1 o 2021.2.

    > [!NOTE]
    > Se si dispone di Blue Yonder WFM 2020.3 o 2021.1, applicare la patch 2020.3.0.4 o 2021.1.0.3. Questa patch risolve un problema per cui gli utenti ricevono un messaggio di errore persistente in Turni. Risolve anche un problema che impedisce agli utenti di aggiornare la loro disponibilità in Turni.

- Nome dell'account del servizio WFM blue yonder e password e URL del servizio:

    - URL di autenticazione federata
    - URL di autenticazione dei cookie
    - URL self-service dei dipendenti
    - URL DELL'API Web di vendita
    - URL API gestione siti
    - URL DELL'API di amministrazione

    Se non hai queste informazioni, contatta il supporto di Blue Yonder. L'account viene creato a livello aziendale radice da un amministratore aziendale blue yonder. Deve avere accesso API, Amministratore client e Store Manager. L'account e la password sono necessari per creare una connessione.
- L'autenticazione SSO federata è abilitata nell'ambiente WFM Blue Yonder. Contattare il supporto blue yonder per verificare che SSO federato sia abilitato. Saranno necessarie le informazioni seguenti:

    - federatedSSOValidationService: `https://wfmconnector.teams.microsoft.com/api/v1/fedauth/{tenantId}/6A51B888-FF44-4FEA-82E1-839401E9CD74/authorize` dove {tenantId} è il tuo tenantId
     - proxyHeader: X-MS-AuthToken

- Almeno un team è configurato in Teams.
- È stato aggiunto l'account di sistema Microsoft 365 come proprietario del team a tutti i team da mappare.</br> [Creare questo account in Microsoft 365](/microsoft-365/admin/add-users/add-users) e assegnargli una licenza Microsoft 365. Quindi, aggiungere l'account come proprietario del team a tutti i team da mappare. Il connettore Turni usa questo account quando la sincronizzazione di Turni cambia da Blue Yonder WFM.

    È consigliabile creare un account specifico per questo scopo e non usare l'account utente.