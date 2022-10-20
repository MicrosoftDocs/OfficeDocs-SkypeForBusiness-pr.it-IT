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
ms.openlocfilehash: c541f92b265d5794df4513eb0cda5d2ff2969f20
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614239"
---
# <a name="configure-call-park-and-retrieve"></a>Configurare parcheggio di chiamata e recupero

Parcheggio di chiamata e recupero consente a un utente di mettere in attesa una chiamata. Quando una chiamata è parcheggiata, il servizio genera un codice univoco per il recupero delle chiamate. L'utente che ha parcheggiato la chiamata o un altro utente può quindi usare tale codice con un'app o un dispositivo supportato per recuperare la chiamata. Per altre informazioni, vedere [Parcheggiare una chiamata in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).

Alcuni degli scenari comuni per l'uso del parcheggio di chiamata sono:

- Un receptionist parcheggia una chiamata per qualcuno che lavora in una fabbrica. L'addetto alla reception annuncia quindi la chiamata e il numero di codice sul sistema di indirizzi pubblici. L'utente per cui è stata effettuata la chiamata può quindi prendere un telefono di Teams in fabbrica e immettere il codice per recuperare la chiamata.

- Un utente parcheggia una chiamata su un dispositivo mobile perché la batteria del dispositivo sta esaurendo l'alimentazione. L'utente può quindi immettere il codice per recuperare la chiamata da un telefono da tavolo di Teams.

- Un rappresentante del supporto riceve una chiamata da un cliente e invia un annuncio su un canale di Teams affinché un esperto recuperi la chiamata e aiuti il cliente. Un esperto immette il codice nei client di Teams per recuperare la chiamata.

Per parcheggiare e recuperare le chiamate, un utente deve essere un utente VoIP aziendale e deve essere incluso in un criterio di parcheggio di chiamata.

Per impostazione predefinita, l'intervallo di numeri di ritiro chiamate è compreso tra 10 e 99. È anche possibile creare un intervallo personalizzato compreso tra 10 e 9999. La prima chiamata parcheggiata verrà sottoposta a rendering di un codice di ritiro dell'inizio dell'intervallo (ad esempio 10). La successiva chiamata parcheggiata verrà resa un codice di ritiro incrementato di 1; ovvero 11 e così via, fino alla fine dell'intervallo viene visualizzato come codice di ritiro. Successivamente, i codici di ritiro con rendering ricominciano dall'inizio dell'intervallo. 

È possibile specificare un timeout come numero di secondi di attesa prima di squillare quando la chiamata parcheggiata non è stata ripresa. L'intervallo consentito è di 120-1800 secondi e il valore predefinito è 300 secondi.

Per configurare il parcheggio di chiamata e il recupero, è necessario essere un amministratore di Teams. È disabilitata per impostazione predefinita. È possibile abilitarlo per gli utenti e creare gruppi di utenti usando i criteri del parcheggio di chiamata. Quando si applicano gli stessi criteri a un set di utenti, questi possono parcheggiare e recuperare chiamate tra loro.

> [!NOTE]
> Parcheggio di chiamata e recupero è disponibile solo in [modalità di distribuzione di Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md). Non è supportato nei telefoni IP Skype for Business.

È possibile configurare il parcheggio di chiamata e il recupero usando l'interfaccia di amministrazione di Teams o PowerShell.

## <a name="use-teams-admin-center"></a>Usare l'interfaccia di amministrazione di Teams

Per creare una nuova istanza dei criteri del parco chiamate:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare ai **criteri del parco chiamate** **vocali** > .

2. Nella scheda **Gestisci criteri** fare clic su **Aggiungi**.

3. Assegnare un nome al criterio e quindi impostare **Consenti parcheggio di chiamata** su **Attivato**.

4. Modificare l'intervallo e il timeout del parco in base alle esigenze.

5. Selezionare **Salva**.

È possibile modificare il criterio selezionandolo nell'elenco e facendo clic su **Modifica**.

Per il funzionamento del criterio, è necessario assegnarlo agli utenti. È possibile [assegnare i criteri agli utenti singolarmente](assign-policies-users-and-groups.md) o assegnarli a un gruppo.

Per assegnare criteri di parcheggio di chiamata a un gruppo:

1. Nella scheda **Assegnazione criteri di gruppo** della pagina **Criteri parcheggio di chiamata** fare clic su **Aggiungi gruppo**.

2. Cercare il gruppo da usare e quindi fare clic su **Aggiungi**.

3. Scegliere un rango rispetto ad altre assegnazioni di gruppo.

4. In **Selezionare un criterio** scegliere il criterio a cui assegnare il gruppo.

5. Selezionare **Applica**.

## <a name="use-powershell"></a>Usare PowerShell

Per gestire il parcheggio di chiamata e recuperare i criteri tramite PowerShell, usare i cmdlet del modulo PowerShell di Teams seguenti:

- [New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy)

- [Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy)

- [Get-CsTeamsCallParkPolicy](/powershell/module/skype/get-csteamscallparkpolicy)

- [Remove-CsTeamsCallParkPolicy](/powershell/module/skype/remove-csteamscallparkpolicy)

- [Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy)

### <a name="examples"></a>Esempi

#### <a name="new-custom-call-park-policy"></a>Nuovi criteri personalizzati per i parchi chiamate

L'esempio seguente crea un criterio di parcheggio di chiamata personalizzato che genera numeri di ritiro da 500 a 1500 e che squillerà dopo 600 secondi se la chiamata parcheggiata non ha risposta.

```powershell
PS C:\> New-CsTeamsCallParkPolicy -Identity "SalesPolicy" -AllowCallPark $true -PickupRangeStart 500 -PickupRangeEnd 1500 -ParkTimeoutSeconds 600
```

#### <a name="change-a-call-park-policy"></a>Modificare i criteri di un parcheggio di chiamata

L'esempio seguente disabilita il criterio parcheggio di chiamata:

```powershell
PS C:\> Set-CsTeamsCallParkPolicy -Identity "SalesPolicy" -AllowCallPark $false
```

#### <a name="grant-a-call-park-policy-to-a-user"></a>Concedere criteri di parcheggio di chiamata a un utente

L'esempio seguente concede il criterio parcheggio di chiamata a un utente:

```powershell
PS C:\> Grant-CsTeamsCallParkPolicy -PolicyName "SalesPolicy" -Identity Ken.Myer@contoso.com
```

#### <a name="remove-a-call-park-policy"></a>Rimuovere i criteri del parcheggio di chiamata

L'esempio seguente rimuove i criteri del parcheggio di chiamata:

```powershell
PS C:\> Remove-CsTeamsCallParkPolicy -Identity "SalesPolicy"
```

## <a name="related-topics"></a>Argomenti correlati

[Parcheggiare una chiamata in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Assegnare i criteri agli utenti in Teams](policy-assignment-overview.md)

