---
title: Creare o modificare un intervallo di numeri di prelievo chiamata di gruppo in Skype for Business
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
description: Creare o modificare un intervallo di numeri di prelievo chiamata di gruppo in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: e71915519014b1fa4cfffa3172327e9949ed73a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100422"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Creare o modificare un intervallo di numeri di prelievo chiamata di gruppo in Skype for Business

Creare o modificare un intervallo di numeri di prelievo chiamata di gruppo in Skype for Business Server VoIP aziendale.

La risposta alle chiamate di gruppo si basa sull'applicazione Parcheggio di chiamata. Quando si distribuisce la risposta alle chiamate di gruppo, è necessario configurare la tabella orbit del parcheggio di chiamata con intervalli di numeri di telefono designati come numeri di gruppo di prelievo chiamata. Questi numeri di gruppo sono i numeri che gli utenti comporre per prelevare le chiamate che squillano per un altro utente.

Come i numeri orbit del parcheggio di chiamata, i numeri dei gruppi di prelievo delle chiamate devono essere interni virtuali a cui non è assegnato alcun utente o telefono. Ogni pool Front End in cui si distribuisce la risposta alle chiamate di gruppo può avere uno o più intervalli di numeri di gruppo di prelievo chiamata. Gli intervalli di numeri di gruppo devono essere univoci a livello globale nella distribuzione e devono essere assegnati come **tipo GroupPickup.**

Utilizzare la procedura seguente per creare o modificare un intervallo di numeri di gruppo di prelievo chiamata nella tabella orbit del parcheggio di chiamata.

> [!NOTE]
> È necessario utilizzare Skype for Business Server Management Shell per creare, modificare, rimuovere e visualizzare gli intervalli di numeri di prelievo chiamata di gruppo nella tabella orbit del parcheggio di chiamata. Gli intervalli di numeri di prelievo delle chiamate di gruppo non sono disponibili nel Pannello di controllo di Skype for Business Server.

Gli intervalli di numeri del gruppo di prelievo chiamata devono essere conformi alle regole seguenti:

- Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale.

- Il valore del numero iniziale dell'intervallo deve avere la stessa lunghezza del numero finale.

- L'intervallo di numeri deve essere univoco e non può sovrapporsi ad altri intervalli.

- Se l'intervallo di numeri inizia con il carattere \* o #, l'intervallo deve essere maggiore di 100.

- Valori validi: deve corrispondere alla stringa dell'espressione regolare ([ \\ *|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ). Questo significa che il valore deve essere una stringa che inizia con il carattere o # o un numero da 1 a 9 (il primo carattere \* non può essere uno zero). Se il primo carattere è o #, il carattere seguente deve essere un numero \* da 1 a 9 (non può essere uno zero). I caratteri successivi possono essere da qualsiasi numero da 0 a 9 fino a sette caratteri aggiuntivi (ad esempio, "#6000", " \* 92000", " \* 95551212" e "915551212"). Se il primo carattere non è o #, il primo carattere deve essere un numero da 1 a 9 (non può essere zero), seguito da un massimo di otto caratteri, ognuno dei quali da \* 0 a 9 (ad esempio, "915551212", "41212", "300").

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>Per creare o modificare un intervallo di gruppi di prelievo chiamata

1. Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in **Delegate Setup Permissions.**

2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**

3. Utilizzare **New-CsCallParkOrbit per** creare un nuovo intervallo di numeri di gruppo di prelievo delle chiamate. Utilizzare **Set-CsCallParkOrbit per** modificare un intervallo esistente di numeri di prelievo delle chiamate.

    Nella riga di comando digitare il comando seguente:

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    Ad esempio:

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    Nell'esempio seguente viene illustrato come modificare un intervallo di numeri dai orbit del parcheggio di chiamata ai gruppi di prelievo delle chiamate.

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > Utilizzare questo cmdlet per modificare il tipo assegnato agli intervalli di numeri solo se inizialmente è stato specificato il tipo non corretto e l'intervallo di gruppi non è ancora in uso. Se si modifica l'intervallo di numeri da CallPark a GroupPickup o viceversa e l'intervallo di numeri è già in uso, parcheggio di chiamata o prelievo chiamata di gruppo smetterà di funzionare per tale intervallo di numeri. Se ad esempio si modifica un intervallo di numeri da CallPark a GroupPick, l'applicazione Parcheggio di chiamata non potrà più utilizzare tale intervallo di orbit per parcheggiare le chiamate.

## <a name="see-also"></a>Vedere anche

[New-CsCallParkOrbit](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Eliminare un intervallo di codici orbit del parcheggio di chiamata](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)