---
title: Parcheggio di chiamata e recupero in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Informazioni su come usare il parcheggio di chiamata e recuperarlo per mettere una chiamata in attesa in Microsoft Teams.
ms.openlocfilehash: a2a70515bbe263716fab8e2deded75e44d12fd6e
ms.sourcegitcommit: 3cb40132e36717dfbdc6dfe83e7ea319f3ec9347
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2022
ms.locfileid: "65465447"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Parcheggio di chiamata e recupero in Microsoft Teams

Parcheggio di chiamata e recupero è una funzionalità che consente a un utente di mettere una chiamata in attesa. Quando una chiamata è parcheggiata, il servizio genera un codice univoco per il recupero delle chiamate. L'utente che ha parcheggiato la chiamata o un altro utente può quindi usare tale codice con un'app o un dispositivo supportato per recuperare la chiamata. Per informazioni dettagliate, vedere [Parcheggiare una chiamata in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).

Alcuni degli scenari comuni per l'uso del parcheggio di chiamata sono:

- Un receptionist parcheggia una chiamata per qualcuno che lavora in una fabbrica. L'addetto alla reception annuncia quindi la chiamata e il numero di codice sul sistema di indirizzi pubblici. L'utente per cui è stata effettuata la chiamata può quindi prendere un Teams telefono in fabbrica e immettere il codice per recuperare la chiamata.
- Un utente parcheggia una chiamata su un dispositivo mobile perché la batteria del dispositivo sta esaurendo l'alimentazione. L'utente può quindi immettere il codice per recuperare la chiamata da un telefono da tavolo Teams.
- Un rappresentante del supporto riceve una chiamata da un cliente e invia un annuncio su un canale di Teams per consentire a un esperto di recuperare la chiamata e aiutare il cliente. Un esperto immette il codice nei client Teams per recuperare la chiamata

Per parcheggiare e recuperare le chiamate, un utente deve essere un utente VoIP aziendale e deve essere incluso in un criterio di parcheggio di chiamata.

> [!NOTE]
> Il parcheggio di chiamata e il recupero sono disponibili solo in [modalità di distribuzione Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e non sono supportati in Skype for Business telefoni IP.

## <a name="configure-call-park-and-retrieve"></a>Configurare il parcheggio di chiamata e il recupero

È necessario essere un amministratore Teams per configurare il parcheggio di chiamata e il recupero. È disabilitata per impostazione predefinita. È possibile abilitarlo per gli utenti e creare gruppi di utenti usando i criteri del parcheggio di chiamata. Quando si applicano gli stessi criteri a un set di utenti, questi possono parcheggiare e recuperare chiamate tra loro.

Per impostazione predefinita, l'intervallo di numeri di ritiro chiamate è compreso tra 10 e 99. È anche possibile creare un intervallo personalizzato compreso tra 10 e 9999. La prima chiamata parcheggiata verrà sottoposta a rendering di un codice di ritiro dell'inizio dell'intervallo (ad esempio 10). La successiva chiamata parcheggiata verrà resa un codice di ritiro incrementato di 1; ovvero 11 e così via, fino alla fine dell'intervallo viene visualizzato come codice di ritiro. Successivamente, i codici di ritiro con rendering ricominciano dall'inizio dell'intervallo. 

È possibile specificare un timeout come numero di secondi di attesa prima di squillare quando la chiamata parcheggiata non è stata ripresa. L'intervallo consentito è di 120-1800 secondi e il valore predefinito è 300 secondi.

Per abilitare i criteri del parcheggio di chiamata:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare ai **criteri del parco chiamate** **vocali** > .
2. Nella scheda **Gestisci criteri** fare clic su **Aggiungi**.
3. Assegnare un nome al criterio e quindi impostare **Consenti parcheggio di chiamata** su **Attivato**.
4. Modificare l'intervallo e il timeout del parco in base alle esigenze.
5. Selezionare **Salva**.

È possibile modificare il criterio selezionandolo nell'elenco e facendo clic su **Modifica**.

Per il funzionamento del criterio, è necessario assegnarlo agli utenti. È possibile [assegnare i criteri agli utenti singolarmente](assign-policies-users-and-groups.md) o assegnarli a un gruppo.

Per assegnare criteri di parcheggio di chiamata a un gruppo

1. Nella scheda **Assegnazione criteri di gruppo** della pagina **Criteri parcheggio di chiamata** fare clic su **Aggiungi gruppo**.
2. Cercare il gruppo da usare e quindi fare clic su **Aggiungi**.
3. Scegliere un rango rispetto ad altre assegnazioni di gruppo.
4. In **Selezionare un criterio** scegliere il criterio a cui assegnare il gruppo.

    ![immagine delle politiche del parco.](media/call-park-assign-policy-to-group.png)

5. Selezionare **Applica**.

## <a name="related-topics"></a>Argomenti correlati

[Parcheggiare una chiamata in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Assegnare i criteri agli utenti in Teams](policy-assignment-overview.md)

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy)
