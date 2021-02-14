---
title: Creare o modificare un intervallo di numeri di risposta alle chiamate di gruppo in Skype for Business
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
description: Creare o modificare un intervallo di numeri di risposta alle chiamate di gruppo in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: f487c277b8eaa03a5b31ce0dc9696b0efe712340
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822406"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="78ef8-103">Creare o modificare un intervallo di numeri di risposta alle chiamate di gruppo in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="78ef8-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="78ef8-104">Creare o modificare un intervallo di numeri di risposta alle chiamate di gruppo in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="78ef8-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="78ef8-105">La risposta alle chiamate di gruppo si basa sull'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="78ef8-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="78ef8-106">Quando si distribuisce la risposta alle chiamate di gruppo, è necessario configurare la tabella orbit del parcheggio di chiamata con intervalli di numeri di telefono designati come numeri di gruppo di prelievo chiamata.</span><span class="sxs-lookup"><span data-stu-id="78ef8-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="78ef8-107">Questi numeri di gruppo sono i numeri che gli utenti comporre per riprendere le chiamate che squillano per un altro utente.</span><span class="sxs-lookup"><span data-stu-id="78ef8-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="78ef8-108">Come i numeri orbit del parcheggio di chiamata, i numeri del gruppo di prelievo delle chiamate devono essere interni virtuali a cui non è assegnato alcun utente o telefono.</span><span class="sxs-lookup"><span data-stu-id="78ef8-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="78ef8-109">Ogni pool Front End in cui si distribuisce la risposta alle chiamate di gruppo può avere uno o più intervalli di numeri di gruppo di risposta alle chiamate.</span><span class="sxs-lookup"><span data-stu-id="78ef8-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="78ef8-110">Gli intervalli di numeri di gruppo devono essere univoci a livello globale nella distribuzione e devono essere assegnati come **tipo GroupPickup.**</span><span class="sxs-lookup"><span data-stu-id="78ef8-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="78ef8-111">Utilizzare la procedura seguente per creare o modificare un intervallo di numeri di gruppo di prelievo chiamata nella tabella orbit del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="78ef8-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="78ef8-112">È necessario utilizzare Skype for Business Server Management Shell per creare, modificare, rimuovere e visualizzare gli intervalli di numeri di risposta alle chiamate di gruppo nella tabella orbit del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="78ef8-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="78ef8-113">Gli intervalli di numeri di risposta alle chiamate di gruppo non sono disponibili nel Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="78ef8-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="78ef8-114">Gli intervalli di numeri del gruppo di prelievo chiamata devono essere conformi alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="78ef8-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="78ef8-115">Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale.</span><span class="sxs-lookup"><span data-stu-id="78ef8-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="78ef8-116">Il valore del numero iniziale dell'intervallo deve avere la stessa lunghezza del numero finale.</span><span class="sxs-lookup"><span data-stu-id="78ef8-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="78ef8-p104">L'intervallo di numeri deve essere univoco e non può sovrapporsi ad altri intervalli.</span><span class="sxs-lookup"><span data-stu-id="78ef8-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="78ef8-119">Se l'intervallo di numeri inizia con il carattere \* o #, l'intervallo deve essere maggiore di 100.</span><span class="sxs-lookup"><span data-stu-id="78ef8-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="78ef8-120">Valori validi: devono corrispondere alla stringa dell'espressione regolare ([ \\ \*|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ).</span><span class="sxs-lookup"><span data-stu-id="78ef8-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="78ef8-121">Questo significa che il valore deve essere una stringa che inizia con il carattere o # oppure un numero compreso tra 1 e 9 (il primo carattere \* non può essere uno zero).</span><span class="sxs-lookup"><span data-stu-id="78ef8-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="78ef8-122">Se il primo carattere è o #, il carattere seguente deve essere un \* numero da 1 a 9 (non può essere uno zero).</span><span class="sxs-lookup"><span data-stu-id="78ef8-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="78ef8-123">I caratteri successivi possono essere da qualsiasi numero da 0 a 9 fino a sette caratteri aggiuntivi (ad esempio, "#6000", " \* 92000", " \* 95551212" e "915551212").</span><span class="sxs-lookup"><span data-stu-id="78ef8-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="78ef8-124">Se il primo carattere non è o #, il primo carattere deve essere un numero da 1 a 9 (non può essere zero), seguito da un massimo di otto caratteri, ognuno dei quali un numero da \* 0 a 9 (ad esempio, "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="78ef8-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="78ef8-125">Per creare o modificare un intervallo di gruppi di prelievo delle chiamate</span><span class="sxs-lookup"><span data-stu-id="78ef8-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="78ef8-126">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in Delegare le autorizzazioni di **installazione.**</span><span class="sxs-lookup"><span data-stu-id="78ef8-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="78ef8-127">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="78ef8-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="78ef8-128">Utilizzare **New-CsCallParkOrbit per** creare un nuovo intervallo di numeri di gruppo di risposta alle chiamate.</span><span class="sxs-lookup"><span data-stu-id="78ef8-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="78ef8-129">Utilizzare **Set-CsCallParkOrbit per** modificare un intervallo esistente di numeri di risposta alle chiamate.</span><span class="sxs-lookup"><span data-stu-id="78ef8-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="78ef8-130">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="78ef8-130">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="78ef8-131">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="78ef8-131">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="78ef8-132">Nell'esempio seguente viene illustrato come modificare un intervallo di numeri dai orbit del parcheggio di chiamata ai gruppi di prelievo delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="78ef8-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="78ef8-133">Utilizzare questo cmdlet per modificare il tipo assegnato agli intervalli di numeri solo se inizialmente è stato specificato il tipo non corretto e l'intervallo di gruppi non è ancora in uso.</span><span class="sxs-lookup"><span data-stu-id="78ef8-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="78ef8-134">Se si modifica l'intervallo di numeri da CallPark a GroupPickup o viceversa e l'intervallo di numeri è già in uso, il parcheggio di chiamata o la risposta alle chiamate di gruppo smetteranno di funzionare per tale intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="78ef8-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="78ef8-135">Ad esempio, se si modifica un intervallo di numeri da CallPark a GroupPick, l'applicazione Parcheggio di chiamata non potrà più utilizzare tale intervallo di orbit per parcheggiare le chiamate.</span><span class="sxs-lookup"><span data-stu-id="78ef8-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="78ef8-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78ef8-136">See also</span></span>

[<span data-ttu-id="78ef8-137">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="78ef8-137">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="78ef8-138">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="78ef8-138">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="78ef8-139">Eliminare un intervallo di codici orbit del parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="78ef8-139">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
