---
title: Creare o modificare una regola di normalizzazione in Skype for business
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
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Riepilogo: informazioni su come definire, creare e modificare una regola di normalizzazione in Skype for Business Server.'
ms.openlocfilehash: 6f8619304e9d3d801dfa430e6addb5105a2b82a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830766"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a><span data-ttu-id="76cbb-103">Creare o modificare una regola di normalizzazione in Skype for business</span><span class="sxs-lookup"><span data-stu-id="76cbb-103">Create or modify a normalization rule in Skype for Business</span></span>

<span data-ttu-id="76cbb-104">**Riepilogo:** Informazioni su come definire, creare e modificare una regola di normalizzazione in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="76cbb-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server.</span></span>

<span data-ttu-id="76cbb-105">Definire, creare e modificare le regole di normalizzazione in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="76cbb-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="76cbb-106">Per definire una regola di normalizzazione utilizzando crea una regola di normalizzazione</span><span class="sxs-lookup"><span data-stu-id="76cbb-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="76cbb-107">Aprire il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="76cbb-107">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="76cbb-108">Optional Seguire la procedura illustrata in [creare o modificare un dial plan in Skype for Business Server](dial-plans.md) tramite il passaggio 11 o [modificare un dial plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) tramite il passaggio 10.</span><span class="sxs-lookup"><span data-stu-id="76cbb-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>

3. <span data-ttu-id="76cbb-109">In **nuova regola di normalizzazione** o **Modifica regola di normalizzazione** digitare un nome che descriva il tipo di numero normalizzato in **nome** (ad esempio, 5DigitExtension).</span><span class="sxs-lookup"><span data-stu-id="76cbb-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>

4. <span data-ttu-id="76cbb-110">(Facoltativo) In **Descrizione** digitare una descrizione della regola di normalizzazione, ad esempio "Converte prefissi a 5 cifre".</span><span class="sxs-lookup"><span data-stu-id="76cbb-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="76cbb-111">In **Crea regola di normalizzazione** immettere valori nei campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="76cbb-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>

   - <span data-ttu-id="76cbb-112">**Cifre iniziali** (facoltativo) specificare le cifre iniziali dei numeri composti che si desidera che il modello corrisponda.</span><span class="sxs-lookup"><span data-stu-id="76cbb-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="76cbb-113">Ad esempio, type425 se si desidera che il modello corrisponda ai numeri composti che iniziano con 425.</span><span class="sxs-lookup"><span data-stu-id="76cbb-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>

   - <span data-ttu-id="76cbb-114">**Lunghezza** Specificare il numero di cifre nel motivo corrispondente e selezionare se si desidera che il modello corrisponda esattamente a questa lunghezza, corrispondere a numeri composti che sono almeno questa lunghezza o corrispondere a numeri composti di qualsiasi lunghezza.</span><span class="sxs-lookup"><span data-stu-id="76cbb-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>

   - <span data-ttu-id="76cbb-115">**Cifre da rimuovere** (facoltativa) specificare il numero di cifre iniziali che devono essere rimosse dai numeri composti che si desidera che il modello corrisponda.</span><span class="sxs-lookup"><span data-stu-id="76cbb-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>

   - <span data-ttu-id="76cbb-116">**Cifre da aggiungere** (facoltativa) specificare le cifre che devono essere aggiunte ai numeri composti che si desidera corrispondano al modello.</span><span class="sxs-lookup"><span data-stu-id="76cbb-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>

     <span data-ttu-id="76cbb-117">I valori immessi in questi campi vengono riportati nei campi **Formato per corrispondenza** e **Regola di conversione**.</span><span class="sxs-lookup"><span data-stu-id="76cbb-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="76cbb-118">Ad esempio, se si lasciano vuote le **cifre iniziali** , Type7 nel campo **lunghezza** e si seleziona **esattamente** e si specifica 0 in **cifre da rimuovere**, l'espressione regolare risultante nel **modello da corrispondere** è la seguente:</span><span class="sxs-lookup"><span data-stu-id="76cbb-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>

     <span data-ttu-id="76cbb-119">^ (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="76cbb-119">^(\d{7})$</span></span>

6. <span data-ttu-id="76cbb-120">In **Regola di conversione** specificare un modello per il formato dei numeri di telefono E.164 convertiti, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="76cbb-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>

   - <span data-ttu-id="76cbb-121">Un valore che rappresenta il numero di cifri specificato nel formato della corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="76cbb-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="76cbb-122">Ad esempio, se il modello corrispondente è ^ (\d {7} ) $, $1 nella regola di conversione rappresenta numeri composti a 7 cifre.</span><span class="sxs-lookup"><span data-stu-id="76cbb-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>

   - <span data-ttu-id="76cbb-123">Optional Digitare un valore nel campo **cifre da aggiungere** per specificare le cifre da anteporre al numero convertito (ad esempio, + 1425).</span><span class="sxs-lookup"><span data-stu-id="76cbb-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>

     <span data-ttu-id="76cbb-124">Ad esempio, se **pattern to match** contiene ^ (\d {7} ) $ come modello per i numeri composti e la **regola di conversione** contiene + 1425 $1 come modello per i numeri di telefono e. 164, la regola Normalizza 5550100 in + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="76cbb-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="76cbb-125">(Facoltativo) Se la regola di normalizzazione restituisce un numero di telefono interno all'organizzazione, selezionare **Estensione interna**.</span><span class="sxs-lookup"><span data-stu-id="76cbb-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="76cbb-p104">(Facoltativo) Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Immetti numero di telefono da testare**.</span><span class="sxs-lookup"><span data-stu-id="76cbb-p104">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="76cbb-128">È possibile salvare una regola di normalizzazione che non passa ancora il test e quindi riconfigurarla successivamente.</span><span class="sxs-lookup"><span data-stu-id="76cbb-128">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="76cbb-129">Per informazioni dettagliate, vedere [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span><span class="sxs-lookup"><span data-stu-id="76cbb-129">For details, see [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

9. <span data-ttu-id="76cbb-130">Fare clic su **OK** per salvare la regola di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="76cbb-130">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="76cbb-131">Fare clic su **OK** per salvare il dial plan.</span><span class="sxs-lookup"><span data-stu-id="76cbb-131">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="76cbb-132">Nella pagina **Dial plan** fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="76cbb-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="76cbb-133">Ogni volta che si crea o si modifica una regola di normalizzazione, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="76cbb-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="76cbb-134">Per ulteriori informazioni, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="76cbb-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="76cbb-135">Per definire manualmente una regola di normalizzazione</span><span class="sxs-lookup"><span data-stu-id="76cbb-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="76cbb-136">Aprire il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="76cbb-136">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="76cbb-137">Optional Seguire la procedura illustrata in [creare o modificare un dial plan in Skype for Business Server](dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="76cbb-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md).</span></span>

3. <span data-ttu-id="76cbb-138">In **nuova regola di normalizzazione** o **Modifica regola di normalizzazione** digitare un nome che descriva il tipo di numero normalizzato in **nome** (ad esempio, denominare la normalizzazione rule5DigitExtension).</span><span class="sxs-lookup"><span data-stu-id="76cbb-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>

4. <span data-ttu-id="76cbb-139">Optional In campo **Descrizione** Digitare una descrizione della regola di normalizzazione (ad esempio, "converte le estensioni a 5 cifre").</span><span class="sxs-lookup"><span data-stu-id="76cbb-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="76cbb-140">In **genera una regola di normalizzazione** fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="76cbb-140">In **Build a Normalization Rule**, click **Edit**.</span></span>

6. <span data-ttu-id="76cbb-141">Immettere quanto segue in **Digita espressione regolare**:</span><span class="sxs-lookup"><span data-stu-id="76cbb-141">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="76cbb-142">In **corrispondenza di questo modello** specificare il modello che si desidera utilizzare per la corrispondenza con il numero di telefono composto.</span><span class="sxs-lookup"><span data-stu-id="76cbb-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>

   - <span data-ttu-id="76cbb-143">In **regola di conversione** specificare un modello per il formato dei numeri di telefono E. 164 tradotti.</span><span class="sxs-lookup"><span data-stu-id="76cbb-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>

     <span data-ttu-id="76cbb-144">Ad esempio, se si immette ^ (\d {7} ) $ in **corrispondenza di questo modello** e + 1425 $1 in **regola di conversione**, la regola Normalizza 5550100 in + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="76cbb-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="76cbb-145">(Facoltativo) Se la regola di normalizzazione restituisce un numero di telefono interno all'organizzazione, selezionare **Estensione interna**.</span><span class="sxs-lookup"><span data-stu-id="76cbb-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="76cbb-146">Optional Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**.</span><span class="sxs-lookup"><span data-stu-id="76cbb-146">(Optional) Enter a number to test the normalization rule and then click **Go**.</span></span> <span data-ttu-id="76cbb-147">I risultati del test vengono visualizzati in **Immetti numero di telefono da testare**.</span><span class="sxs-lookup"><span data-stu-id="76cbb-147">The test results are displayed under **Enter a number to test**.</span></span>

9. <span data-ttu-id="76cbb-148">Fare clic su **OK** per salvare la regola di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="76cbb-148">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="76cbb-149">Fare clic su **OK** per salvare il dial plan.</span><span class="sxs-lookup"><span data-stu-id="76cbb-149">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="76cbb-150">Nella pagina **Dial plan** fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="76cbb-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="76cbb-151">Ogni volta che si crea o si modifica una regola di normalizzazione, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="76cbb-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="76cbb-152">Per ulteriori informazioni, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="76cbb-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>


