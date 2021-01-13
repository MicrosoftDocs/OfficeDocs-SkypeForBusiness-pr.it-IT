---
title: Creare o modificare una regola di conversione per la presentazione ID chiamata in Skype for Business Server
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
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Riepilogo: informazioni su come definire una regola di conversione utilizzando lo strumento Crea regola di conversione in Skype for Business Server.'
ms.openlocfilehash: b93d271abd0ade1b178e859f2a0599464a6759e5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804196"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="e04a8-103">Creare o modificare una regola di conversione per la presentazione ID chiamata in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e04a8-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="e04a8-104">**Riepilogo:** Informazioni su come definire una regola di conversione utilizzando lo strumento Crea regola di conversione in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e04a8-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="e04a8-105">Seguire questa procedura se si desidera definire una regola di conversione immettendo un insieme di valori nello strumento **Crea regola di conversione** e abilitando il pannello di controllo di Skype for Business Server per generare la corrispondente regola di conversione e il relativo modello.</span><span class="sxs-lookup"><span data-stu-id="e04a8-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="e04a8-106">In alternativa, è possibile scrivere manualmente un'espressione regolare per definire il formato e la regola di conversione corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="e04a8-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="e04a8-107">Per informazioni dettagliate, vedere [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span><span class="sxs-lookup"><span data-stu-id="e04a8-107">For details, see [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="e04a8-108">Per definire una regola tramite lo strumento Crea regola di conversione</span><span class="sxs-lookup"><span data-stu-id="e04a8-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="e04a8-109">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e04a8-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="e04a8-110">Per iniziare a definire una regola di conversione, seguire i passaggi descritti in [Configure a Trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through Step 10 o [Configure a Trunk Without Media Bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through Step 9.</span><span class="sxs-lookup"><span data-stu-id="e04a8-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="e04a8-111">In **Nome** nella pagina **Nuova regola di conversione** o **Modifica regola di conversione** digitare un nome descrittivo del formato del numero da convertire.</span><span class="sxs-lookup"><span data-stu-id="e04a8-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="e04a8-112">Optional In **Descrizione** Digitare una descrizione della regola di conversione, ad esempio la composizione a distanza interurbana degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="e04a8-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="e04a8-113">Nella sezione **Crea regola di conversione** della finestra di dialogo immettere i valore nei campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e04a8-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="e04a8-114">**Cifre iniziali**: (facoltativo) specificare le cifre iniziali dei numeri a cui si desidera corrisponda il formato.</span><span class="sxs-lookup"><span data-stu-id="e04a8-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="e04a8-115">Ad esempio, immettere + in questo campo per specificare una corrispondenza con i numeri nel formato E.164, che iniziano con +.</span><span class="sxs-lookup"><span data-stu-id="e04a8-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="e04a8-116">**Lunghezza**: specificare il numero di cifre nel formato e specificare se si desidera applicare il formato ai numeri esattamente di questa lunghezza, almeno di questa lunghezza o di qualsiasi lunghezza.</span><span class="sxs-lookup"><span data-stu-id="e04a8-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="e04a8-117">Ad esempio, immettere 11 e selectAt almeno nell'elenco a discesa in modo che corrispondano a numeri con una lunghezza di almeno 11 cifre.</span><span class="sxs-lookup"><span data-stu-id="e04a8-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="e04a8-118">**Cifre da rimuovere**: (facoltativo) specificare il numero di cifre iniziali da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="e04a8-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="e04a8-119">Ad esempio, immettere 1 per eliminare il valore + dall'inizio del numero.</span><span class="sxs-lookup"><span data-stu-id="e04a8-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="e04a8-120">**Prefisso**: (facoltativo) specificare le cifre da aggiungere all'inizio dei numeri convertiti.</span><span class="sxs-lookup"><span data-stu-id="e04a8-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="e04a8-121">Ad esempio, immettere 011 se si desidera aggiungere 011 all'inizio dei numeri convertiti quando si applica questa regola.</span><span class="sxs-lookup"><span data-stu-id="e04a8-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

     <span data-ttu-id="e04a8-p106">I valori immessi in questi campi vengono riportati nei campi **Formato per corrispondenza** e **Regola di conversione**. Se si specificano i valori di esempio precedenti, ad esempio, l'espressione regolare risultante nel campo **Formato per corrispondenza** sarà:</span><span class="sxs-lookup"><span data-stu-id="e04a8-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

     <span data-ttu-id="e04a8-124">^\+(\d {9} \d +) $</span><span class="sxs-lookup"><span data-stu-id="e04a8-124">^\+(\d{9}\d+)$</span></span>

     <span data-ttu-id="e04a8-125">Nel campo **Regola di conversione** specificare un modello per il formato dei numeri convertiti.</span><span class="sxs-lookup"><span data-stu-id="e04a8-125">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="e04a8-126">Il modello è composto da due parti:</span><span class="sxs-lookup"><span data-stu-id="e04a8-126">This pattern has two parts:</span></span>

   - <span data-ttu-id="e04a8-127">Un valore (ad esempio $1) che rappresenta il numero di cifre nel formato corrispondente</span><span class="sxs-lookup"><span data-stu-id="e04a8-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="e04a8-128">(Facoltativo) Un valore che è possibile aggiungere all'inizio del numero immettendolo nel campo **Prefisso**</span><span class="sxs-lookup"><span data-stu-id="e04a8-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

     <span data-ttu-id="e04a8-129">In base ai valori di esempio precedenti, nel campo Regola di conversione viene visualizzato **011$1**.</span><span class="sxs-lookup"><span data-stu-id="e04a8-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

     <span data-ttu-id="e04a8-130">Con l'applicazione di questa regola di conversione il numero +441235551010 diventa 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="e04a8-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="e04a8-131">Fare clic su **OK** per salvare la regola di conversione.</span><span class="sxs-lookup"><span data-stu-id="e04a8-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="e04a8-132">Fare clic su **OK** per salvare la configurazione del trunk.</span><span class="sxs-lookup"><span data-stu-id="e04a8-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="e04a8-133">Nella pagina **Configurazione trunk** fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="e04a8-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e04a8-134">Ogni volta che si crea o modifica una regola di conversione, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="e04a8-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="e04a8-135">Per ulteriori informazioni, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="e04a8-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="e04a8-136">Per definire manualmente una regola di conversione</span><span class="sxs-lookup"><span data-stu-id="e04a8-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="e04a8-137">Aprire il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e04a8-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="e04a8-138">Per iniziare a definire una regola di conversione, seguire i passaggi descritti in [Configure a Trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through Step 10 o [Configure a Trunk Without Media Bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through Step 9.</span><span class="sxs-lookup"><span data-stu-id="e04a8-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="e04a8-139">Nel campo **Nome** della pagina **Nuova regola di conversione** o **Modifica regola di conversione** digitare un nome che descriva il formato del numero da convertire.</span><span class="sxs-lookup"><span data-stu-id="e04a8-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="e04a8-140">Optional In **Descrizione** Digitare una descrizione della regola di conversione, ad esempio il numero di chiamate interurbane internazionali degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="e04a8-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="e04a8-141">Fare clic su **Modifica** nella parte inferiore della sezione **Crea regola di conversione**.</span><span class="sxs-lookup"><span data-stu-id="e04a8-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="e04a8-142">Immettere quanto segue in **Digita espressione regolare**:</span><span class="sxs-lookup"><span data-stu-id="e04a8-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="e04a8-143">In **Trova corrispondenza per questo formato** specificare il modello di formato da utilizzare per trovare corrispondenze con i numeri da convertire.</span><span class="sxs-lookup"><span data-stu-id="e04a8-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="e04a8-144">In **Regola di conversione** specificare un modello per il formato dei numeri convertiti.</span><span class="sxs-lookup"><span data-stu-id="e04a8-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

     <span data-ttu-id="e04a8-145">Ad esempio, se si immette ^ \+ (\d {9} \d +) $ in **corrispondono a questo modello** and011 $1 in **regola di conversione**, la regola verrà convertita da + 441235551010 a 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="e04a8-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="e04a8-146">Fare clic su **OK** per salvare la regola di conversione.</span><span class="sxs-lookup"><span data-stu-id="e04a8-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="e04a8-147">Fare clic su **OK** per salvare la configurazione del trunk.</span><span class="sxs-lookup"><span data-stu-id="e04a8-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="e04a8-148">Nella pagina **Configurazione trunk** fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="e04a8-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e04a8-149">Ogni volta che si crea o modifica una regola di conversione, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="e04a8-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="e04a8-150">Per ulteriori informazioni, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="e04a8-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="e04a8-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e04a8-151">See also</span></span>

[<span data-ttu-id="e04a8-152">Configurare un trunk con bypass multimediale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e04a8-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="e04a8-153">Configurare un trunk senza bypass multimediale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e04a8-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="e04a8-154">Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business</span><span class="sxs-lookup"><span data-stu-id="e04a8-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="e04a8-155">Distribuire il bypass multimediale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e04a8-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

