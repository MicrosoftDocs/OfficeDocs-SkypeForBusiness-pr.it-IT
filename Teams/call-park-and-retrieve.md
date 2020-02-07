---
title: Chiamare il parcheggio e il recupero in Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 04/12/2019
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
description: USA Call Park e recupera per effettuare una chiamata in attesa nel servizio Teams nel cloud.
ms.openlocfilehash: b4b5200f139f5610ff1109b97742607d3b633ff6
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824594"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Chiamare il parcheggio e il recupero in Microsoft Teams

Call Park and retrieve è una funzionalità che consente a un utente di inserire una chiamata in attesa nel servizio Teams nel cloud. Quando una chiamata viene parcheggiata, il servizio genera un codice univoco per il recupero delle chiamate. L'utente che ha parcheggiato la chiamata o qualcun altro può quindi usare il codice e un'app o un dispositivo supportato per recuperare la chiamata. 

Alcuni degli scenari comuni per l'uso di Call Park sono i seguenti: 

- Un receptionist parcheggia una chiamata per qualcuno che lavora in una fabbrica. L'addetto alla ricezione annuncia quindi la chiamata e il numero di codice sul sistema di indirizzi pubblici. L'utente a cui è consentita la chiamata può quindi prendere un telefono per le squadre in fabbrica e immettere il codice per recuperare la chiamata.
- Un utente parcheggia una chiamata su un dispositivo mobile perché la batteria del dispositivo sta esaurendo la potenza. L'utente può quindi immettere il codice per recuperare la chiamata da un telefono da tavolo teams.
- Un supporto rappresentativo parcheggia una chiamata del cliente e invia un annuncio su un canale di teams per un esperto per recuperare la chiamata e aiutare il cliente. Un esperto immette il codice nei client di teams per recuperare la chiamata

> [!IMPORTANT]
> Questa caratteristica è disponibile solo in modalità di distribuzione solo teams. Per altre informazioni sulle modalità di distribuzione dei team, vedere [comprendere la coesistenza e l'interoperabilità di Microsoft teams e Skype for business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licenza richiesta

Per parcheggiare e recuperare le chiamate, un utente deve essere un utente di VoIP aziendale e un amministratore deve concedere all'utente un criterio per il parcheggio delle chiamate. Per altre informazioni sul modello di licenza, vedere [licenze di Office 365 per Microsoft teams](office-365-licensing.md).

## <a name="call-park-and-retrieve-feature-availability"></a>Chiamare il parcheggio e recuperare la disponibilità delle caratteristiche

Call Park and retrieve è attualmente supportato dai seguenti client e dispositivi. (Supportata solo in modalità teams, con o senza connettività PSTN)

| Capacità | Desktop Teams | App teams Mac | App Web Teams (Edge) |App teams per dispositivi mobili iOS/Android | Telefono IP Teams | Telefono IP Skype for business |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| Parcheggiare una chiamata | Sì | Sì | Sì | Sì | Prossimamente| No |
| Recuperare una chiamata parcheggiata | Sì | Sì | Sì | Sì | Prossimamente| No |
| Chiamata non recuperata Ring back | Sì | Sì | Sì | Sì | Prossimamente| No |

## <a name="configuring-call-park-and-retrieve"></a>Configurazione di Call Park e recupero

È necessario essere un amministratore per configurare il parcheggio delle chiamate e il recupero e la caratteristica è disabilitata per impostazione predefinita. Puoi abilitarlo per gli utenti e creare gruppi di utenti usando i criteri per il parcheggio delle chiamate. Quando si applica lo stesso criterio a un set di utenti, è possibile parcheggiare e recuperare le chiamate tra di loro. Per configurare Call Park per gli utenti e creare gruppi di utenti di Call Park, seguire la procedura di [assegnazione di un parcheggio](#assign-a-call-park-policy) di chiamata seguente.

Per informazioni su come usare la funzionalità chiama parcheggio e recupera, vedere [parcheggiare una chiamata in teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).

### <a name="enable-a-call-park-policy"></a>Abilitare un criterio per il parcheggio delle chiamate

Seguire questa procedura per abilitare un criterio per il parcheggio delle chiamate:

1. Accedere ai criteri per il**** > **parcheggio**dell'interfaccia di amministrazione > di **Microsoft teams**.
2. Selezionare **nuovo criterio**.
3. Assegnare un nome al criterio e quindi passare **Consenti al parcheggio** di chiamata **.**
4. Selezionare **Salva**.

### <a name="assign-a-call-park-policy"></a>Assegnare un criterio per il parcheggio delle chiamate

Seguire questa procedura per assegnare un criterio di parcheggio di chiamata a uno o più utenti:

1. Accedere ai criteri per il**** > **parcheggio**dell'interfaccia di amministrazione > di **Microsoft teams**.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio.
3. Selezionare **Gestisci utenti**.
4. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o per nome utente, selezionare il nome e quindi fare clic su **Aggiungi**. Ripetere questo passaggio per ogni utente che si vuole aggiungere.
5. Al termine dell'aggiunta di utenti, selezionare **Salva**.
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a>Configurare il parcheggio delle chiamate e il recupero con PowerShell

Usa il cmdlet di PowerShell [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) per creare un criterio per il parcheggio delle chiamate.

Usare il cmdlet di PowerShell [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) per concedere un criterio per il parcheggio delle chiamate.

È possibile modificare l'impostazione predefinita usando [set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) come indicato di seguito:

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a>Risoluzione dei problemi

Se gli utenti non riescono a visualizzare il pulsante parcheggia o Recupera: 

- Verificare che l'utente disponga dei criteri di parcheggio delle chiamate abilitati. 

Se un utente tenta di recuperare una chiamata e non riesce, verificare quanto segue:

- Verificare che l'utente stia usando il client teams o un dispositivo/telefono abilitato per Teams
- Raggruppamento: l'utente è un membro del gruppo Call Park, che si basa sull'assegnazione di criteri di parcheggio per le chiamate a teams. 
- Modalità Isola-Call Park and retrieve non è disponibile nella modalità Isola di teams.
- La chiamata è già stata recuperata o terminata.

## <a name="more-information"></a>Altre informazioni

[Parcheggiare una chiamata in teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).
