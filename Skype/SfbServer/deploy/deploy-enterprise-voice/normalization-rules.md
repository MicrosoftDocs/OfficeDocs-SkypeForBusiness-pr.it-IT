---
title: Creare o modificare una regola di normalizzazione in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Riepilogo: informazioni su come definire, creare e modificare una regola di normalizzazione in Skype for Business Server.'
ms.openlocfilehash: 4739bdb50e0a76c088cb6129539438c1ac6d795a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195763"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a><span data-ttu-id="32e37-103">Creare o modificare una regola di normalizzazione in Skype for business</span><span class="sxs-lookup"><span data-stu-id="32e37-103">Create or modify a normalization rule in Skype for Business</span></span>

<span data-ttu-id="32e37-104">**Riepilogo:** Informazioni su come definire, creare e modificare una regola di normalizzazione in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="32e37-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server.</span></span>

<span data-ttu-id="32e37-105">Definire, creare e modificare le regole di normalizzazione in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="32e37-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="32e37-106">Per definire una regola di normalizzazione tramite genera una regola di normalizzazione</span><span class="sxs-lookup"><span data-stu-id="32e37-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="32e37-107">Aprire il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="32e37-107">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="32e37-108">Opzionale Seguire i passaggi descritti in [creare o modificare un dial plan in Skype for Business Server](dial-plans.md) tramite il passaggio 11 o [modificare un dial plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) tramite il passaggio 10.</span><span class="sxs-lookup"><span data-stu-id="32e37-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>

3. <span data-ttu-id="32e37-109">Nella **nuova regola** di normalizzazione o **Modifica regola**di normalizzazione digitare un nome che descriva il criterio di numerazione normalizzato in **nome** , ad esempio 5DigitExtension.</span><span class="sxs-lookup"><span data-stu-id="32e37-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>

4. <span data-ttu-id="32e37-110">Opzionale In **Descrizione**Digitare una descrizione della regola di normalizzazione, ad esempio "converte le estensioni a 5 cifre".</span><span class="sxs-lookup"><span data-stu-id="32e37-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="32e37-111">In **genera una regola**di normalizzazione immettere i valori nei campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="32e37-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>

   - <span data-ttu-id="32e37-112">**Cifre iniziali** Opzionale Specificare le cifre iniziali dei numeri composti per cui si vuole che il motivo corrisponda.</span><span class="sxs-lookup"><span data-stu-id="32e37-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="32e37-113">Ad esempio, type425 se si vuole che il motivo corrisponda ai numeri composti che iniziano con 425.</span><span class="sxs-lookup"><span data-stu-id="32e37-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>

   - <span data-ttu-id="32e37-114">**Lunghezza** Specificare il numero di cifre nel modello corrispondente e selezionare se si vuole che il motivo corrisponda esattamente a questa lunghezza, corrispondere a numeri composti con almeno questa lunghezza o corrispondere a numeri composti di qualsiasi lunghezza.</span><span class="sxs-lookup"><span data-stu-id="32e37-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>

   - <span data-ttu-id="32e37-115">**Cifre da rimuovere** Opzionale Specificare il numero di cifre iniziali da rimuovere dai numeri composti per cui si vuole che il motivo corrisponda.</span><span class="sxs-lookup"><span data-stu-id="32e37-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>

   - <span data-ttu-id="32e37-116">**Cifre da aggiungere** Opzionale Specificare le cifre da aggiungere ai numeri composti per cui si vuole che il motivo corrisponda.</span><span class="sxs-lookup"><span data-stu-id="32e37-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>

     <span data-ttu-id="32e37-117">I valori immessi in questi campi si riflettono in **pattern per la corrispondenza** e la **regola di traduzione**.</span><span class="sxs-lookup"><span data-stu-id="32e37-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="32e37-118">Ad esempio, se si lasciano vuote le **cifre iniziali** , Type7 nel campo **lunghezza** e si seleziona **esattamente**e si specificano 0 in **cifre da rimuovere**, l'espressione regolare risultante nel **pattern da corrispondere** è:</span><span class="sxs-lookup"><span data-stu-id="32e37-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>

     <span data-ttu-id="32e37-119">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="32e37-119">^(\d{7})$</span></span>

6. <span data-ttu-id="32e37-120">Nella **regola di traduzione**specificare un motivo per il formato dei numeri di telefono E. 164 tradotti come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="32e37-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>

   - <span data-ttu-id="32e37-121">Valore che rappresenta il numero di cifre specificato nel criterio di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="32e37-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="32e37-122">Ad esempio, se il modello corrispondente è ^ (\d{7}) $ quindi $1 nella regola di traduzione rappresenta numeri composti da 7 cifre.</span><span class="sxs-lookup"><span data-stu-id="32e37-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>

   - <span data-ttu-id="32e37-123">Opzionale Digitare un valore nel campo **cifre da aggiungere** per specificare le cifre da anteporre al numero tradotto, ad esempio + 1425.</span><span class="sxs-lookup"><span data-stu-id="32e37-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>

     <span data-ttu-id="32e37-124">Ad esempio, se **pattern per la corrispondenza** contiene ^ ({7}\d) $ come modello per i numeri composti e la **regola di traduzione** contiene + 1425 $1 come modello per i numeri di telefono e. 164, la regola Normalizza 5550100 in + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="32e37-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="32e37-125">Opzionale Se la regola di normalizzazione genera un numero di telefono interno all'organizzazione, selezionare **estensione interna**.</span><span class="sxs-lookup"><span data-stu-id="32e37-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="32e37-126">Opzionale Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**.</span><span class="sxs-lookup"><span data-stu-id="32e37-126">(Optional) Enter a number to test the normalization rule, and then click **Go**.</span></span> <span data-ttu-id="32e37-127">I risultati del test vengono visualizzati in **immettere un numero da testare**.</span><span class="sxs-lookup"><span data-stu-id="32e37-127">The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="32e37-128">È possibile salvare una regola di normalizzazione che non supera ancora il test e quindi riconfigurarla in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="32e37-128">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="32e37-129">Per informazioni dettagliate, vedere [testare il routing vocale](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span><span class="sxs-lookup"><span data-stu-id="32e37-129">For details, see [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

9. <span data-ttu-id="32e37-130">Fare clic su **OK** per salvare la regola di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="32e37-130">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="32e37-131">Fare clic su **OK** per salvare il dial plan.</span><span class="sxs-lookup"><span data-stu-id="32e37-131">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="32e37-132">Nella pagina **dial plan** fare clic su **commit**e quindi su **Commit all**.</span><span class="sxs-lookup"><span data-stu-id="32e37-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="32e37-133">Ogni volta che si crea o si modifica una regola di normalizzazione, è necessario eseguire il comando **commit tutti** per pubblicare la modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="32e37-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="32e37-134">Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="32e37-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="32e37-135">Per definire manualmente una regola di normalizzazione</span><span class="sxs-lookup"><span data-stu-id="32e37-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="32e37-136">Aprire il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="32e37-136">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="32e37-137">Opzionale Seguire i passaggi descritti in [creare o modificare un dial plan in Skype for Business Server](dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="32e37-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md).</span></span>

3. <span data-ttu-id="32e37-138">Nella **nuova regola** di normalizzazione o **Modifica regola**di normalizzazione digitare un nome che descriva il criterio di numerazione normalizzato in **nome** , ad esempio denominare la rule5DigitExtension di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="32e37-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>

4. <span data-ttu-id="32e37-139">Opzionale In campo **Descrizione** Digitare una descrizione della regola di normalizzazione, ad esempio "converte le estensioni a 5 cifre".</span><span class="sxs-lookup"><span data-stu-id="32e37-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="32e37-140">In **genera una regola**di normalizzazione fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="32e37-140">In **Build a Normalization Rule**, click **Edit**.</span></span>

6. <span data-ttu-id="32e37-141">Immettere le opzioni seguenti nell' **espressione regolare di tipo**:</span><span class="sxs-lookup"><span data-stu-id="32e37-141">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="32e37-142">In **corrispondenza di questo modello**specificare il motivo che si vuole usare per corrispondere al numero di telefono chiamato.</span><span class="sxs-lookup"><span data-stu-id="32e37-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>

   - <span data-ttu-id="32e37-143">Nella **regola di traduzione**specificare un motivo per il formato dei numeri di telefono E. 164 tradotti.</span><span class="sxs-lookup"><span data-stu-id="32e37-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>

     <span data-ttu-id="32e37-144">Ad esempio, se si digita ^ (\d{7}) $ in **corrispondenza di questo modello** e + 1425 $1 nella **regola di traduzione**, la regola Normalizza 5550100 in + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="32e37-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="32e37-145">Opzionale Se la regola di normalizzazione genera un numero di telefono interno all'organizzazione, selezionare **estensione interna**.</span><span class="sxs-lookup"><span data-stu-id="32e37-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="32e37-146">Opzionale Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**.</span><span class="sxs-lookup"><span data-stu-id="32e37-146">(Optional) Enter a number to test the normalization rule and then click **Go**.</span></span> <span data-ttu-id="32e37-147">I risultati del test vengono visualizzati in **immettere un numero da testare**.</span><span class="sxs-lookup"><span data-stu-id="32e37-147">The test results are displayed under **Enter a number to test**.</span></span>

9. <span data-ttu-id="32e37-148">Fare clic su **OK** per salvare la regola di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="32e37-148">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="32e37-149">Fare clic su **OK** per salvare il dial plan.</span><span class="sxs-lookup"><span data-stu-id="32e37-149">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="32e37-150">Nella pagina **dial plan** fare clic su **commit**e quindi su **Commit all**.</span><span class="sxs-lookup"><span data-stu-id="32e37-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="32e37-151">Ogni volta che si crea o si modifica una regola di normalizzazione, è necessario eseguire il comando **commit tutti** per pubblicare la modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="32e37-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="32e37-152">Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="32e37-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>


