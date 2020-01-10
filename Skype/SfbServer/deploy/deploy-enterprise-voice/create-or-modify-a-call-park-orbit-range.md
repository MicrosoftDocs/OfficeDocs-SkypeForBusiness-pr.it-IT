---
title: Creare o modificare un intervallo orbit di Call Park in Skype for business
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
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Creare o modificare una tabella di Orbit range di Call Park in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: e4dc9e9384210ec2abcceb652b814aef8c401b05
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001726"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a><span data-ttu-id="0506c-103">Creare o modificare un intervallo orbit di Call Park in Skype for business</span><span class="sxs-lookup"><span data-stu-id="0506c-103">Create or modify a Call Park orbit range in Skype for Business</span></span>

<span data-ttu-id="0506c-104">Creare o modificare una tabella di Orbit range di Call Park in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="0506c-104">Create or modify a Call Park orbit range table in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="0506c-105">Call Park USA orbite per le chiamate di parcheggio.</span><span class="sxs-lookup"><span data-stu-id="0506c-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="0506c-106">Prima che gli utenti possano parcheggiare e recuperare le chiamate, è necessario configurare la tabella Orbit di Call Park.</span><span class="sxs-lookup"><span data-stu-id="0506c-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="0506c-107">Devi specificare gli intervalli di numeri di interno (orbite) che l'organizzazione riserva alle chiamate di parcheggio e definire il routing per tali intervalli specificando il pool di parcheggio di chiamata che gestisce ogni intervallo.</span><span class="sxs-lookup"><span data-stu-id="0506c-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="0506c-108">Quando definisci intervalli orbitali, l'obiettivo è quello di avere orbite sufficienti in modo che una qualsiasi orbita non venga riutilizzata troppo rapidamente, ma non così tante orbite che limiti il numero di estensioni disponibili per gli utenti o altri servizi.</span><span class="sxs-lookup"><span data-stu-id="0506c-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="0506c-109">È possibile creare più intervalli orbit di Call Park per ogni pool di Skype for Business Server in cui è distribuita l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="0506c-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="0506c-110">Ogni intervallo di Orbit di Call Park deve avere un nome univoco globale e un set di estensioni univoco.</span><span class="sxs-lookup"><span data-stu-id="0506c-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0506c-111">Un intervallo orbit include in genere 100 o meno orbite.</span><span class="sxs-lookup"><span data-stu-id="0506c-111">An orbit range typically encompasses 100 or fewer orbits.</span></span> <span data-ttu-id="0506c-112">Ogni intervallo può essere molto più grande, purché sia più piccolo del massimo di 10.000 orbite per intervallo e si hanno meno di 50.000 orbite per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="0506c-112">Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool.</span></span> <span data-ttu-id="0506c-113">Se un intervallo è troppo piccolo, le orbite vengono riutilizzate più rapidamente.</span><span class="sxs-lookup"><span data-stu-id="0506c-113">If a range is too small, the orbits are reused more quickly.</span></span>

<span data-ttu-id="0506c-114">Usare blocchi di estensioni virtuali (estensioni che non hanno un utente o un telefono assegnato) per gli intervalli di Orbit.</span><span class="sxs-lookup"><span data-stu-id="0506c-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

> [!NOTE]
> <span data-ttu-id="0506c-115">L'assegnazione di numeri DID (Direct Inward Dialing) come numeri di orbita nella tabella Orbit di parcheggio delle chiamate non è supportata.</span><span class="sxs-lookup"><span data-stu-id="0506c-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>

<span data-ttu-id="0506c-116">Usare una delle procedure seguenti per creare o modificare un intervallo di orbit del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="0506c-116">Use one of the following procedures to create or modify a call park orbit range.</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="0506c-117">Per usare il pannello di controllo di Skype for Business Server per creare o modificare un intervallo di numeri per le chiamate di parcheggio</span><span class="sxs-lookup"><span data-stu-id="0506c-117">To use Skype for Business Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="0506c-118">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0506c-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="0506c-119">Per informazioni dettagliate, vedere **delegare le autorizzazioni di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="0506c-119">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="0506c-120">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0506c-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="0506c-121">Sulla barra di spostamento sinistra fare clic su **caratteristiche vocali** e quindi su **Call Park**.</span><span class="sxs-lookup"><span data-stu-id="0506c-121">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4. <span data-ttu-id="0506c-122">Nella pagina **Call Park** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0506c-122">On the **Call Park** page, do one of the following:</span></span>

   - <span data-ttu-id="0506c-123">Per creare un nuovo intervallo di Orbit, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="0506c-123">To create a new orbit range, click **New**.</span></span> <span data-ttu-id="0506c-124">In **nome**Digitare un nome identificativo per l'intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="0506c-124">In **Name**, type an identifying name for this range of numbers.</span></span>

     > [!NOTE]
     > <span data-ttu-id="0506c-125">Dopo aver eseguito il commit dell'intervallo di Orbit nel database, non è possibile modificare questo nome.</span><span class="sxs-lookup"><span data-stu-id="0506c-125">After you commit the orbit range to the database, you cannot change this name.</span></span>

   - <span data-ttu-id="0506c-126">Per modificare un intervallo di orbit esistente, digitare tutto o parte del nome dell'intervallo di Orbit nel campo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="0506c-126">To modify an existing orbit range, type all or part of the name of the orbit range in the search field.</span></span> <span data-ttu-id="0506c-127">Nell'elenco risultante di orbite fare clic sull'orbita desiderata, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="0506c-127">In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5. <span data-ttu-id="0506c-128">Nel campo primo **intervallo di numeri** Digitare il numero di inizio dell'intervallo di estensioni per l'orbita del parcheggio di chiamata, quindi digitare il numero finale dell'intervallo nel secondo campo dell' **intervallo di numeri** .</span><span class="sxs-lookup"><span data-stu-id="0506c-128">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span> <span data-ttu-id="0506c-129">Tenere presente che:</span><span class="sxs-lookup"><span data-stu-id="0506c-129">Be aware:</span></span>

   - <span data-ttu-id="0506c-130">Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.</span><span class="sxs-lookup"><span data-stu-id="0506c-130">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

   - <span data-ttu-id="0506c-131">Il valore del numero iniziale dell'intervallo deve avere la stessa lunghezza del numero finale.</span><span class="sxs-lookup"><span data-stu-id="0506c-131">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

   - <span data-ttu-id="0506c-132">L'intervallo di orbit deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="0506c-132">The orbit range must be unique.</span></span> <span data-ttu-id="0506c-133">Questo intervallo non può sovrapporsi ad altri intervalli.</span><span class="sxs-lookup"><span data-stu-id="0506c-133">This range cannot overlap with any other range.</span></span>

   - <span data-ttu-id="0506c-134">Se l'intervallo orbit inizia con il carattere \* o #, l'intervallo deve essere maggiore di 100.</span><span class="sxs-lookup"><span data-stu-id="0506c-134">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span>

   - <span data-ttu-id="0506c-135">Valori validi: deve corrispondere alla stringa di espressione regolare (\\[\* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="0506c-135">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="0506c-136">Questo significa che il valore deve essere una stringa che inizia con il \* carattere o # o un numero da 1 a 9 (il primo carattere non può essere uno zero).</span><span class="sxs-lookup"><span data-stu-id="0506c-136">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="0506c-137">Se il primo carattere è \* o #, il carattere seguente deve essere un numero da 1 a 9 (non può essere uno zero).</span><span class="sxs-lookup"><span data-stu-id="0506c-137">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="0506c-138">I caratteri successivi possono essere qualsiasi numero da 0 a 9 fino a sette caratteri aggiuntivi (ad esempio, "#6000"\*, "92000"\*, "95551212" e "915551212").</span><span class="sxs-lookup"><span data-stu-id="0506c-138">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="0506c-139">Se il primo carattere non \* è o #, il primo carattere deve essere un numero da 1 a 9 (non può essere zero), seguito da un massimo di otto caratteri, ognuno dei quali è compreso tra 0 e 9, ad esempio "915551212", "41212", "300".</span><span class="sxs-lookup"><span data-stu-id="0506c-139">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

   - <span data-ttu-id="0506c-140">Non dovresti avere più di un totale di 50.000 orbite per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="0506c-140">You should not have more than a total of 50,000 orbits per pool.</span></span> <span data-ttu-id="0506c-141">Ogni intervallo orbit include in genere 100 o meno orbite, ma può essere molto più grande purché includa meno di 10.000 orbite.</span><span class="sxs-lookup"><span data-stu-id="0506c-141">Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits.</span></span> <span data-ttu-id="0506c-142">Anziché specificare un numero iniziale "7000000" e un numero finale "8000000", ad esempio, valutare la possibilità di specificare un numero iniziale "7000000" e un numero finale "7000100".</span><span class="sxs-lookup"><span data-stu-id="0506c-142">For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

6. <span data-ttu-id="0506c-143">In **FQDN del server di destinazione**, fare clic sul nome di dominio completo (FQDN) o sull'ID servizio del servizio applicazione che ospita l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="0506c-143">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="0506c-144">Tutte le chiamate parcheggiate in numeri compresi nell'intervallo specificato dal numero di inizio e dal numero finale nell'intervallo di Orbit verranno indirizzate a questo server o pool.</span><span class="sxs-lookup"><span data-stu-id="0506c-144">All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7. <span data-ttu-id="0506c-145">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="0506c-145">Click **Commit**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="0506c-146">Per usare Skype for Business Server Management Shell per creare o modificare un intervallo di numeri per le chiamate di parcheggio</span><span class="sxs-lookup"><span data-stu-id="0506c-146">To use Skype for Business Server Management Shell to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="0506c-147">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di **configurazione delegate**.</span><span class="sxs-lookup"><span data-stu-id="0506c-147">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="0506c-148">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="0506c-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="0506c-149">USA **New-CsCallParkOrbit** per creare un nuovo intervallo di numeri orbitali.</span><span class="sxs-lookup"><span data-stu-id="0506c-149">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="0506c-150">Usare **set-CsCallParkOrbit** per modificare un intervallo esistente di numeri di orbita.</span><span class="sxs-lookup"><span data-stu-id="0506c-150">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>

    <span data-ttu-id="0506c-151">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="0506c-151">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    <span data-ttu-id="0506c-152">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0506c-152">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    <span data-ttu-id="0506c-153">L'esempio seguente mostra come modificare i numeri in un intervallo di orbit esistente,</span><span class="sxs-lookup"><span data-stu-id="0506c-153">The following example shows how to modify the numbers in an existing orbit range,</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a><span data-ttu-id="0506c-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0506c-154">See also</span></span>

[<span data-ttu-id="0506c-155">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="0506c-155">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="0506c-156">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="0506c-156">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="0506c-157">Eliminare un intervallo di Orbit di Call Park</span><span class="sxs-lookup"><span data-stu-id="0506c-157">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
