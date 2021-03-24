---
title: Parcheggio di chiamata e recupero in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Informazioni su come usare il parcheggio di chiamata e recuperare per mettere una chiamata in attesa in Microsoft Teams.
ms.openlocfilehash: efc36a2bc90b64abf2e886c5e768a26704bd6550
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102802"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Parcheggio di chiamata e recupero in Microsoft Teams

Il parcheggio di chiamata e il recupero è una funzionalità che consente a un utente di mettere una chiamata in attesa. Quando una chiamata è parcheggiata, il servizio genera un codice univoco per il recupero delle chiamate. L'utente che ha parcheggiato la chiamata o qualcun altro può quindi usare il codice con un'app o un dispositivo supportato per recuperare la chiamata. Per informazioni [dettagliate, vedere Parcheggiare](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) una chiamata in Teams.

Alcuni degli scenari comuni per l'uso del parcheggio di chiamata sono:

- Un addetto alla reception parcheggia una chiamata per qualcuno che lavora in una fabbrica. L'addetto alla ricezione annuncia quindi la chiamata e il numero di codice sul sistema di indirizzi pubblici. L'utente per cui è stata chiamata può quindi prelevare un telefono Teams nella fabbrica e immettere il codice per recuperare la chiamata.
- Un utente parcheggia una chiamata su un dispositivo mobile perché la batteria del dispositivo è in esaurimento. L'utente può quindi immettere il codice per recuperare la chiamata da un telefono da tavolo di Teams.
- Un rappresentante del supporto parcheggia una chiamata del cliente e invia un annuncio su un canale di Teams per consentire a un esperto di recuperare la chiamata e aiutare il cliente. Un esperto immette il codice nei client di Teams per recuperare la chiamata

Per parcheggiare e recuperare le chiamate, un utente deve essere un VoIP aziendale utente e deve essere incluso in un criterio di parcheggio di chiamata.

> [!NOTE]
> Il parcheggio di chiamata e il recupero sono disponibili solo in [modalità di distribuzione](teams-and-skypeforbusiness-coexistence-and-interoperability.md) di Teams Only e non sono supportati nei telefoni IP Skype for Business.

## <a name="configure-call-park-and-retrieve"></a>Configurare il parcheggio di chiamata e recuperare

Per configurare e recuperare il parcheggio di chiamata, è necessario essere un amministratore di Teams. È disabilitato per impostazione predefinita. È possibile abilitarlo per gli utenti e creare gruppi di utenti usando i criteri di parcheggio di chiamata. Quando si applicano gli stessi criteri a un set di utenti, possono parcheggiare e recuperare le chiamate tra loro.

Per abilitare un criterio di parcheggio di chiamata

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare **a** Criteri  >  **del parco chiamate vocali.**
2. Nella scheda **Gestisci criteri** fare clic su **Aggiungi.**
3. Assegnare un nome al criterio e quindi impostare **Consenti parcheggio di chiamata** su **Attivata.**

    ![Screenshot delle impostazioni dei criteri del parcheggio di chiamata](media/call-park-add-policy.png)

4. Selezionare **Salva**.

È possibile modificare il criterio selezionandolo nell'elenco e facendo clic su **Modifica**.

Per il corretto funzionamento del criterio, è necessario assegnarlo agli utenti. È possibile [assegnare il criterio agli utenti singolarmente](assign-policies.md) o assegnarli a un gruppo.

Per assegnare un criterio di parte di chiamata a un gruppo

1. Nella scheda **Assegnazione Criteri di** gruppo della pagina Criteri di parcheggio **di** chiamata fare clic su **Aggiungi gruppo.**
2. Cercare il gruppo da usare e quindi fare clic su **Aggiungi**.
3. Scegliere un rango rispetto ad altre assegnazioni di gruppo.
4. In **Selezionare un criterio** scegliere il criterio a cui si vuole assegnare il gruppo.

    ![Immagine dei criteri del parco](media/call-park-assign-policy-to-group.png)

5. Selezionare **Applica**.

## <a name="related-topics"></a>Argomenti correlati

[Parcheggiare una chiamata in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)