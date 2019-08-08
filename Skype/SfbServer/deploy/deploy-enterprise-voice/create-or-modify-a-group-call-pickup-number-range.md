---
title: Creare o modificare un intervallo di numeri di raccolta di chiamate di gruppo in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Creare o modificare un intervallo di prelievo delle chiamate di gruppo in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 3098d7cf1554586dd2fd2ace934682ae58a90489
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233679"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Creare o modificare un intervallo di numeri di raccolta di chiamate di gruppo in Skype for business

Creare o modificare un intervallo di prelievo delle chiamate di gruppo in Skype for Business Server VoIP aziendale.

Il ritiro delle chiamate di gruppo si basa sull'applicazione Call Park. Quando si distribuisce il pickup di una chiamata di gruppo, è necessario configurare la tabella Orbit di Call Park con intervalli di numeri di telefono designati come numeri di gruppo di prelievo chiamate. Questi numeri di gruppo sono i numeri che gli utenti chiamano per raccogliere chiamate che squillano per un altro utente.

Come i numeri dell'orbita di Call Park, i numeri dei gruppi di pickup delle chiamate devono essere estensioni virtuali che non hanno un utente o un telefono assegnato. Ogni pool Front end in cui si distribuisce il pickup di una chiamata di gruppo può avere uno o più intervalli di numeri di gruppo di prelievo chiamate. Gli intervalli di numeri di gruppo devono essere univoci a livello globale nella distribuzione e devono essere assegnati come tipo **GroupPickup** .

Usare la procedura seguente per creare o modificare un intervallo di numeri del gruppo di raccolta chiamate nella tabella Orbit di Call Park.

> [!NOTE]
> Devi usare Skype for Business Server Management Shell per creare, modificare, rimuovere e visualizzare intervalli di numeri di prelievo delle chiamate di gruppo nella tabella Orbit di Call Park. Gli intervalli di numeri di raccolta delle chiamate di gruppo non sono disponibili nel pannello di controllo di Skype for Business Server.

Gli intervalli di numeri del gruppo di raccolta chiamate devono essere conformi alle regole seguenti:

- Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.

- Il valore del numero iniziale dell'intervallo deve avere la stessa lunghezza del numero finale.

- L'intervallo di numeri deve essere univoco e non può sovrapporsi ad altri intervalli.

- Se l'intervallo di numeri inizia con il \* carattere o #, l'intervallo deve essere maggiore di 100.

- Valori validi: deve corrispondere alla stringa di espressione regolare (\\[* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}). Questo significa che il valore deve essere una stringa che inizia con il \* carattere o # o un numero da 1 a 9 (il primo carattere non può essere uno zero). Se il primo carattere è \* o #, il carattere seguente deve essere un numero da 1 a 9 (non può essere uno zero). I caratteri successivi possono essere qualsiasi numero da 0 a 9 fino a sette caratteri aggiuntivi (ad esempio, "#6000"\*, "92000"\*, "95551212" e "915551212"). Se il primo carattere non \* è o #, il primo carattere deve essere un numero da 1 a 9 (non può essere zero), seguito da un massimo di otto caratteri, ognuno dei quali è compreso tra 0 e 9, ad esempio "915551212", "41212", "300".

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>Per creare o modificare l'intervallo di un gruppo di raccolta chiamate

1. Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di **configurazione**Delegate.

2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

3. USA **New-CsCallParkOrbit** per creare un nuovo intervallo di numeri di gruppo di pick-up delle chiamate. Usare **set-CsCallParkOrbit** per modificare un intervallo esistente di numeri di prelievo delle chiamate.

    Nella riga di comando eseguire:

   ```
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    Ad esempio:

   ```
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    L'esempio seguente mostra come modificare un intervallo di numeri dalle orbite di Call Park per chiamare i gruppi di raccolta.

   ```
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > Usa questo cmdlet per cambiare il tipo assegnato agli intervalli di numeri solo se hai inizialmente specificato il tipo non corretto e l'intervallo di gruppi non è ancora in uso. Se si cambia l'intervallo di numeri da CallPark a GroupPickup o viceversa e l'intervallo di numeri è già in uso, il pick-up di chiamata o di chiamata di gruppo smetterà di funzionare per l'intervallo di numeri. Se ad esempio si modifica un intervallo di numeri da CallPark a GroupPick, l'applicazione di parcheggio delle chiamate non può più usare l'intervallo di orbite per parcheggiare le chiamate.

## <a name="see-also"></a>Vedere anche

[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Eliminare un intervallo di Orbit di Call Park](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
