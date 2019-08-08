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
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="144a3-103">Creare o modificare un intervallo di numeri di raccolta di chiamate di gruppo in Skype for business</span><span class="sxs-lookup"><span data-stu-id="144a3-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="144a3-104">Creare o modificare un intervallo di prelievo delle chiamate di gruppo in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="144a3-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="144a3-105">Il ritiro delle chiamate di gruppo si basa sull'applicazione Call Park.</span><span class="sxs-lookup"><span data-stu-id="144a3-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="144a3-106">Quando si distribuisce il pickup di una chiamata di gruppo, è necessario configurare la tabella Orbit di Call Park con intervalli di numeri di telefono designati come numeri di gruppo di prelievo chiamate.</span><span class="sxs-lookup"><span data-stu-id="144a3-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="144a3-107">Questi numeri di gruppo sono i numeri che gli utenti chiamano per raccogliere chiamate che squillano per un altro utente.</span><span class="sxs-lookup"><span data-stu-id="144a3-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="144a3-108">Come i numeri dell'orbita di Call Park, i numeri dei gruppi di pickup delle chiamate devono essere estensioni virtuali che non hanno un utente o un telefono assegnato.</span><span class="sxs-lookup"><span data-stu-id="144a3-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="144a3-109">Ogni pool Front end in cui si distribuisce il pickup di una chiamata di gruppo può avere uno o più intervalli di numeri di gruppo di prelievo chiamate.</span><span class="sxs-lookup"><span data-stu-id="144a3-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="144a3-110">Gli intervalli di numeri di gruppo devono essere univoci a livello globale nella distribuzione e devono essere assegnati come tipo **GroupPickup** .</span><span class="sxs-lookup"><span data-stu-id="144a3-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="144a3-111">Usare la procedura seguente per creare o modificare un intervallo di numeri del gruppo di raccolta chiamate nella tabella Orbit di Call Park.</span><span class="sxs-lookup"><span data-stu-id="144a3-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="144a3-112">Devi usare Skype for Business Server Management Shell per creare, modificare, rimuovere e visualizzare intervalli di numeri di prelievo delle chiamate di gruppo nella tabella Orbit di Call Park.</span><span class="sxs-lookup"><span data-stu-id="144a3-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="144a3-113">Gli intervalli di numeri di raccolta delle chiamate di gruppo non sono disponibili nel pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="144a3-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="144a3-114">Gli intervalli di numeri del gruppo di raccolta chiamate devono essere conformi alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="144a3-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="144a3-115">Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.</span><span class="sxs-lookup"><span data-stu-id="144a3-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="144a3-116">Il valore del numero iniziale dell'intervallo deve avere la stessa lunghezza del numero finale.</span><span class="sxs-lookup"><span data-stu-id="144a3-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="144a3-p104">L'intervallo di numeri deve essere univoco e non può sovrapporsi ad altri intervalli.</span><span class="sxs-lookup"><span data-stu-id="144a3-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="144a3-119">Se l'intervallo di numeri inizia con il \* carattere o #, l'intervallo deve essere maggiore di 100.</span><span class="sxs-lookup"><span data-stu-id="144a3-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="144a3-120">Valori validi: deve corrispondere alla stringa di espressione regolare (\\[\* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="144a3-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="144a3-121">Questo significa che il valore deve essere una stringa che inizia con il \* carattere o # o un numero da 1 a 9 (il primo carattere non può essere uno zero).</span><span class="sxs-lookup"><span data-stu-id="144a3-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="144a3-122">Se il primo carattere è \* o #, il carattere seguente deve essere un numero da 1 a 9 (non può essere uno zero).</span><span class="sxs-lookup"><span data-stu-id="144a3-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="144a3-123">I caratteri successivi possono essere qualsiasi numero da 0 a 9 fino a sette caratteri aggiuntivi (ad esempio, "#6000"\*, "92000"\*, "95551212" e "915551212").</span><span class="sxs-lookup"><span data-stu-id="144a3-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="144a3-124">Se il primo carattere non \* è o #, il primo carattere deve essere un numero da 1 a 9 (non può essere zero), seguito da un massimo di otto caratteri, ognuno dei quali è compreso tra 0 e 9, ad esempio "915551212", "41212", "300".</span><span class="sxs-lookup"><span data-stu-id="144a3-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="144a3-125">Per creare o modificare l'intervallo di un gruppo di raccolta chiamate</span><span class="sxs-lookup"><span data-stu-id="144a3-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="144a3-126">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di **configurazione**Delegate.</span><span class="sxs-lookup"><span data-stu-id="144a3-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="144a3-127">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="144a3-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="144a3-128">USA **New-CsCallParkOrbit** per creare un nuovo intervallo di numeri di gruppo di pick-up delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="144a3-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="144a3-129">Usare **set-CsCallParkOrbit** per modificare un intervallo esistente di numeri di prelievo delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="144a3-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="144a3-130">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="144a3-130">At the command line, run:</span></span>

   ```
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="144a3-131">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="144a3-131">For example:</span></span>

   ```
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="144a3-132">L'esempio seguente mostra come modificare un intervallo di numeri dalle orbite di Call Park per chiamare i gruppi di raccolta.</span><span class="sxs-lookup"><span data-stu-id="144a3-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="144a3-133">Usa questo cmdlet per cambiare il tipo assegnato agli intervalli di numeri solo se hai inizialmente specificato il tipo non corretto e l'intervallo di gruppi non è ancora in uso.</span><span class="sxs-lookup"><span data-stu-id="144a3-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="144a3-134">Se si cambia l'intervallo di numeri da CallPark a GroupPickup o viceversa e l'intervallo di numeri è già in uso, il pick-up di chiamata o di chiamata di gruppo smetterà di funzionare per l'intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="144a3-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="144a3-135">Se ad esempio si modifica un intervallo di numeri da CallPark a GroupPick, l'applicazione di parcheggio delle chiamate non può più usare l'intervallo di orbite per parcheggiare le chiamate.</span><span class="sxs-lookup"><span data-stu-id="144a3-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="144a3-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="144a3-136">See also</span></span>

[<span data-ttu-id="144a3-137">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="144a3-137">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="144a3-138">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="144a3-138">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="144a3-139">Eliminare un intervallo di Orbit di Call Park</span><span class="sxs-lookup"><span data-stu-id="144a3-139">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
