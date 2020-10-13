---
title: Chiamare il parcheggio e il recupero in Microsoft Teams
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
description: Informazioni su come usare Call Park e retrieve per effettuare una chiamata in attesa in Microsoft teams.
ms.openlocfilehash: e64d9dafec0f3a4b65abc532ecfa60583fe6da84
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424594"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Chiamare il parcheggio e il recupero in Microsoft Teams

Call Park and retrieve è una funzionalità che consente a un utente di effettuare una chiamata in attesa. Quando una chiamata viene parcheggiata, il servizio genera un codice univoco per il recupero delle chiamate. L'utente che ha parcheggiato la chiamata o qualcun altro può quindi usare il codice con un'app o un dispositivo supportato per recuperare la chiamata. Per informazioni dettagliate, vedere [parcheggiare una chiamata in teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) .

Alcuni degli scenari comuni per l'uso di Call Park sono i seguenti:

- Un receptionist parcheggia una chiamata per qualcuno che lavora in una fabbrica. L'addetto alla ricezione annuncia quindi la chiamata e il numero di codice sul sistema di indirizzi pubblici. L'utente a cui è consentita la chiamata può quindi prendere un telefono per le squadre in fabbrica e immettere il codice per recuperare la chiamata.
- Un utente parcheggia una chiamata su un dispositivo mobile perché la batteria del dispositivo sta esaurendo la potenza. L'utente può quindi immettere il codice per recuperare la chiamata da un telefono da tavolo teams.
- Un supporto rappresentativo parcheggia una chiamata del cliente e invia un annuncio su un canale di teams per un esperto per recuperare la chiamata e aiutare il cliente. Un esperto immette il codice nei client di teams per recuperare la chiamata

Per parcheggiare e recuperare le chiamate, un utente deve essere un utente di VoIP aziendale e deve essere incluso in un criterio per il parcheggio delle chiamate.

> [!NOTE]
> Call Park and retrieve è disponibile solo in [modalità di distribuzione solo in teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e non è supportato nei telefoni IP Skype for business.

## <a name="configure-call-park-and-retrieve"></a>Configurare il parcheggio delle chiamate e il recupero

È necessario essere un amministratore di teams per configurare Call Park e retrieve. È disabilitata per impostazione predefinita. Puoi abilitarlo per gli utenti e creare gruppi di utenti usando i criteri per il parcheggio delle chiamate. Quando si applica lo stesso criterio a un set di utenti, è possibile parcheggiare e recuperare le chiamate tra di loro.

Per abilitare un criterio per il parcheggio delle chiamate

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**accedere ai criteri per il parcheggio per le  >  **chiamate**vocali.
2. Nella scheda **Gestisci criteri** fare clic su **Aggiungi**.
3. Assegnare un nome al criterio e quindi passare **Consenti al parcheggio** di chiamata **.**

    ![Screenshot delle impostazioni dei criteri per il parcheggio delle chiamate](media/call-park-add-policy.png)

4. Selezionare **Salva**.

Per modificare il criterio, selezionarlo nell'elenco e fare clic su **modifica**.

Affinché il criterio funzioni, deve essere assegnato agli utenti. È possibile [assegnare i criteri agli utenti singolarmente](assign-policies.md) o assegnarli a un gruppo.

Per assegnare un criterio per la parte di chiamata a un gruppo

1. Nella pagina **criteri di parcheggio chiamata** , nella scheda **assegnazione criteri di gruppo** , fare clic su **Aggiungi gruppo**.
2. Cercare il gruppo che si vuole usare e quindi fare clic su **Aggiungi**.
3. Scegliere un rango rispetto ad altre assegnazioni di gruppo.
4. In **selezionare un criterio**scegliere i criteri a cui si vuole assegnare il gruppo.

    ![](media/call-park-assign-policy-to-group.png)

5. Fare clic su **applica**.

## <a name="related-topics"></a>Argomenti correlati

[Parcheggiare una chiamata in teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Assegnare criteri agli utenti in teams](assign-policies.md)

[New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)