---
title: Creare o modificare un intervallo di codici orbit del parcheggio di chiamata in Skype for business
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
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Creare o modificare una tabella di un intervallo di codici orbit del parcheggio di chiamata in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 6a17b4faaad026376bccad060cb421a5e2cfa1df
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805476"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a><span data-ttu-id="8ffb2-103">Creare o modificare un intervallo di codici orbit del parcheggio di chiamata in Skype for business</span><span class="sxs-lookup"><span data-stu-id="8ffb2-103">Create or modify a Call Park orbit range in Skype for Business</span></span>

<span data-ttu-id="8ffb2-104">Creare o modificare una tabella di un intervallo di codici orbit del parcheggio di chiamata in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-104">Create or modify a Call Park orbit range table in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="8ffb2-105">Il parcheggio di chiamata utilizza le orbite per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="8ffb2-106">Prima che gli utenti possano parcheggiare e recuperare le chiamate, è necessario configurare la tabella di orbit del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="8ffb2-107">È necessario specificare gli intervalli di numeri di interno (orbite) che l'organizzazione prenoterà per le chiamate al parcheggio e definire il routing per tali intervalli specificando il pool di parcheggio di chiamata che gestisce ogni intervallo.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="8ffb2-108">Quando si definiscono gli intervalli di codici orbit, l'obiettivo è quello di disporre di un numero sufficiente di codici orbit tale da evitare che uno stesso codice orbit venga riutilizzato troppo rapidamente, ma senza eccedere limitando il numero di interni disponibili per gli utenti o altri servizi.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="8ffb2-109">È possibile creare più intervalli di orbit del parcheggio di chiamata per ogni pool di Skype for Business Server in cui è distribuita l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="8ffb2-110">Ogni intervallo di orbit del parcheggio di chiamata deve disporre di un nome univoco globale e di un insieme univoco di estensioni.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ffb2-p102">Un intervallo di codici orbit include in genere al massimo 100 codici orbit. Ogni intervallo può essere più grande, purché sia più piccolo del massimo di 10.000 codici orbit per intervallo e ogni pool includa meno di 50.000 codici orbit. Se un intervallo è troppo piccolo, i codici orbit vengono riutilizzati più rapidamente.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>

<span data-ttu-id="8ffb2-114">Utilizzare blocchi di estensioni virtuali, ovvero a cui non sono assegnati utenti o telefoni, per gli intervalli di codici orbit.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

> [!NOTE]
> <span data-ttu-id="8ffb2-115">L'assegnazione dei numeri DID (Direct Inward Dialing) ai numeri orbitali nella tabella orbit del parcheggio di chiamata non è supportata.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>

<span data-ttu-id="8ffb2-116">Per creare o modificare un intervallo orbit del parcheggio di chiamata, usare una delle procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-116">Use one of the following procedures to create or modify a call park orbit range.</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="8ffb2-117">Per utilizzare il pannello di controllo di Skype for Business Server per creare o modificare un intervallo di numeri per il parcheggio delle chiamate</span><span class="sxs-lookup"><span data-stu-id="8ffb2-117">To use Skype for Business Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="8ffb2-p103">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-p103">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="8ffb2-120">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="8ffb2-121">Sulla barra di spostamento sinistra fare clic su **Funzionalità vocali** e quindi su **Parcheggio di chiamata**.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-121">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4. <span data-ttu-id="8ffb2-122">Nella pagina **Parcheggio di chiamata** effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ffb2-122">On the **Call Park** page, do one of the following:</span></span>

   - <span data-ttu-id="8ffb2-p104">Per creare un nuovo intervallo orbit, fare clic su **Nuovo**. In **Nome** digitare un nome per identificare l'intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-p104">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>

     > [!NOTE]
     > <span data-ttu-id="8ffb2-125">Dopo l'esecuzione del commit dell'intervallo orbit nel database non sarà possibile modificare il nome.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-125">After you commit the orbit range to the database, you cannot change this name.</span></span>

   - <span data-ttu-id="8ffb2-p105">Per modificare un intervallo orbit esistente, digitarne il nome, per intero o in parte, nel campo di ricerca. Nell'elenco dei codici orbit risultante fare clic sul codice desiderato, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-p105">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5. <span data-ttu-id="8ffb2-128">Nel primo campo **Intervallo numeri** digitare il numero iniziale dell'intervallo di estensioni per i codici orbit di parcheggio di chiamata e nel secondo campo **Intervallo numeri** digitare il numero finale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-128">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span> <span data-ttu-id="8ffb2-129">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8ffb2-129">Be aware:</span></span>

   - <span data-ttu-id="8ffb2-130">Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-130">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

   - <span data-ttu-id="8ffb2-131">Il valore del numero iniziale dell'intervallo deve avere la stessa lunghezza del numero finale.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-131">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

   - <span data-ttu-id="8ffb2-p107">L'intervallo di codici orbit deve essere univoco. Tale intervallo non può sovrapporsi ad altri intervalli.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-p107">The orbit range must be unique. This range cannot overlap with any other range.</span></span>

   - <span data-ttu-id="8ffb2-134">Se l'intervallo di Orbit inizia con il carattere \* o #, l'intervallo deve essere maggiore di 100.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-134">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span>

   - <span data-ttu-id="8ffb2-135">Valori validi: deve corrispondere alla stringa di espressione regolare ([ \\ \* | #]? [ 1-9] \d {0,7} ) | ([1-9] \d {0,8} ).</span><span class="sxs-lookup"><span data-stu-id="8ffb2-135">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="8ffb2-136">Questo significa che il valore deve essere una stringa che inizia con il carattere \* o # o un numero da 1 a 9 (il primo carattere non può essere uno zero).</span><span class="sxs-lookup"><span data-stu-id="8ffb2-136">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="8ffb2-137">Se il primo carattere è \* o #, il carattere seguente deve essere un numero compreso tra 1 e 9 (non può essere uno zero).</span><span class="sxs-lookup"><span data-stu-id="8ffb2-137">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="8ffb2-138">I caratteri successivi possono essere qualsiasi numero compreso tra 0 e 9 fino a sette caratteri aggiuntivi, ad esempio "#6000", " \* 92000", " \* 95551212" e "915551212".</span><span class="sxs-lookup"><span data-stu-id="8ffb2-138">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="8ffb2-139">Se il primo carattere non è \* o #, il primo carattere deve essere un numero da 1 a 9 (non può essere zero), seguito da un massimo di otto caratteri, ognuno dei quali è compreso tra 0 e 9, ad esempio "915551212", "41212", "300".</span><span class="sxs-lookup"><span data-stu-id="8ffb2-139">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

   - <span data-ttu-id="8ffb2-p109">In totale non vi possono essere più di 50.000 codici orbit per ogni pool. Ogni intervallo di codici orbit in genere comprende al massimo 100 codici orbit, ma può essere anche molto più esteso, purché non superi i 10.000 codici orbit. Ad esempio, anziché specificare "7000000" come numero iniziale e "8000000" come numero finale, considerare la possibilità di specificare "7000000" e "7000100" rispettivamente come numero iniziale e numero finale.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-p109">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

6. <span data-ttu-id="8ffb2-p110">In **FQDN del server di destinazione** fare clic sul nome di dominio completo (FQDN) o sull'ID del servizio dell'applicazione che ospita l'applicazione Parcheggio di chiamata. Tutte le chiamate parcheggiate nei numeri dell'intervallo specificato dal numero iniziale e dal numero finale dell'intervallo di codici orbit saranno instradate a tale server o pool.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-p110">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application. All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7. <span data-ttu-id="8ffb2-145">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-145">Click **Commit**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="8ffb2-146">Per utilizzare Skype for Business Server Management Shell per creare o modificare un intervallo di numeri per il parcheggio delle chiamate</span><span class="sxs-lookup"><span data-stu-id="8ffb2-146">To use Skype for Business Server Management Shell to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="8ffb2-147">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in **delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-147">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="8ffb2-148">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="8ffb2-149">Usare **New-CsCallParkOrbit** per creare un nuovo intervallo di numeri orbit.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-149">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="8ffb2-150">Usare **Set-CsCallParkOrbit** per modificare un intervallo di numeri orbit esistente.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-150">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>

    <span data-ttu-id="8ffb2-151">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8ffb2-151">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    <span data-ttu-id="8ffb2-152">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8ffb2-152">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    <span data-ttu-id="8ffb2-153">L'esempio seguente mostra come modificare i numeri di un intervallo orbit esistente.</span><span class="sxs-lookup"><span data-stu-id="8ffb2-153">The following example shows how to modify the numbers in an existing orbit range,</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a><span data-ttu-id="8ffb2-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ffb2-154">See also</span></span>

[<span data-ttu-id="8ffb2-155">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="8ffb2-155">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="8ffb2-156">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="8ffb2-156">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="8ffb2-157">Eliminare un intervallo di codici orbit del parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="8ffb2-157">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
