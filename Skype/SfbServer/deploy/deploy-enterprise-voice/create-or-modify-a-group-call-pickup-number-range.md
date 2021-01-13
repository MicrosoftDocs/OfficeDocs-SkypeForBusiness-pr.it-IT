---
title: Creare o modificare un intervallo di numeri di prelievo delle chiamate di gruppo in Skype for business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Creare o modificare un intervallo di numeri di prelievo delle chiamate di gruppo in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: f487c277b8eaa03a5b31ce0dc9696b0efe712340
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822406"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Creare o modificare un intervallo di numeri di prelievo delle chiamate di gruppo in Skype for business

Creare o modificare un intervallo di numeri di prelievo delle chiamate di gruppo in Skype for Business Server VoIP aziendale.

Il prelievo delle chiamate di gruppo si basa sull'applicazione Parcheggio di chiamata. Quando si distribuisce il prelievo delle chiamate di gruppo, è necessario configurare la tabella di orbit del parcheggio di chiamata con intervalli di numeri di telefono designati come numeri del gruppo di prelievo delle chiamate. Questi numeri di gruppo sono i numeri che gli utenti chiamano per raccogliere le chiamate che squillano per un altro utente.

Analogamente ai numeri dell'orbita del parcheggio di chiamata, i numeri del gruppo di prelievo delle chiamate devono essere estensioni virtuali a cui non è assegnato alcun utente o telefono. Ogni pool Front end in cui si distribuisce il prelievo delle chiamate di gruppo può avere uno o più intervalli di numeri del gruppo di prelievo delle chiamate. Gli intervalli di numeri di gruppo devono essere univoci a livello globale nella distribuzione e devono essere assegnati come tipo di **GroupPickup** .

Utilizzare la procedura seguente per creare o modificare un intervallo di numeri del gruppo di prelievo delle chiamate nella tabella orbit del parcheggio di chiamata.

> [!NOTE]
> È necessario utilizzare Skype for Business Server Management Shell per creare, modificare, rimuovere e visualizzare gli intervalli di numeri di prelievo delle chiamate di gruppo nella tabella orbit del parcheggio di chiamata. Gli intervalli di numeri di prelievo delle chiamate di gruppo non sono disponibili nel pannello di controllo di Skype for Business Server.

Gli intervalli di numeri del gruppo di prelievo delle chiamate devono essere conformi alle regole seguenti:

- Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale.

- Il valore del numero iniziale dell'intervallo deve avere la stessa lunghezza del numero finale.

- L'intervallo di numeri deve essere univoco e non può sovrapporsi ad altri intervalli.

- Se l'intervallo di numeri inizia con il carattere \* o #, l'intervallo deve essere maggiore di 100.

- Valori validi: deve corrispondere alla stringa di espressione regolare ([ \\ * | #]? [ 1-9] \d {0,7} ) | ([1-9] \d {0,8} ). Questo significa che il valore deve essere una stringa che inizia con il carattere \* o # o un numero da 1 a 9 (il primo carattere non può essere uno zero). Se il primo carattere è \* o #, il carattere seguente deve essere un numero compreso tra 1 e 9 (non può essere uno zero). I caratteri successivi possono essere qualsiasi numero compreso tra 0 e 9 fino a sette caratteri aggiuntivi, ad esempio "#6000", " \* 92000", " \* 95551212" e "915551212". Se il primo carattere non è \* o #, il primo carattere deve essere un numero da 1 a 9 (non può essere zero), seguito da un massimo di otto caratteri, ognuno dei quali è compreso tra 0 e 9, ad esempio "915551212", "41212", "300".

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>Per creare o modificare un intervallo di gruppi di prelievo di chiamata

1. Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in **delegate Setup Permissions**.

2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.

3. Utilizzare **New-CsCallParkOrbit** per creare un nuovo intervallo di numeri del gruppo di prelievo delle chiamate. Utilizzare **set-CsCallParkOrbit** per modificare un intervallo esistente di numeri di prelievo delle chiamate.

    Nella riga di comando digitare il comando seguente:

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    Ad esempio:

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    Nell'esempio seguente viene illustrato come modificare un intervallo di numeri dalle orbite del parcheggio di chiamata ai gruppi di prelievo delle chiamate.

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > Utilizzare questo cmdlet per modificare il tipo assegnato agli intervalli di numeri solo se inizialmente è stato specificato il tipo non corretto e l'intervallo di gruppi non è ancora in uso. Se si modifica l'intervallo di numeri da CallPark a GroupPickup o viceversa e l'intervallo di numeri è già in uso, il servizio parcheggio di chiamata o di chiamata di gruppo smetterà di funzionare per tale intervallo di numeri. Ad esempio, se si modifica un intervallo di numeri da CallPark a GroupPick, l'applicazione Parcheggio di chiamata non è più in grado di utilizzare l'intervallo di orbite per parcheggiare le chiamate.

## <a name="see-also"></a>Vedere anche

[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Eliminare un intervallo di codici orbit del parcheggio di chiamata](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
