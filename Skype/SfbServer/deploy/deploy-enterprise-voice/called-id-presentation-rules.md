---
title: Creare o modificare una regola di traduzione per la presentazione di ID chiamata in Skype for Business Server
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
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Riepilogo: informazioni su come definire una regola di traduzione usando lo strumento crea una regola di traduzione in Skype for Business Server.'
ms.openlocfilehash: 13e89fd836c971085a3a1fc40b7e60793e10eb68
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187433"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="e3636-103">Creare o modificare una regola di traduzione per la presentazione di ID chiamata in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e3636-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="e3636-104">**Riepilogo:** Informazioni su come definire una regola di traduzione usando lo strumento crea una regola di traduzione in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e3636-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="e3636-105">Seguire questa procedura se si vuole definire una regola di traduzione immettendo un set di valori nello strumento **Crea una regola di traduzione** e abilitando il pannello di controllo di Skype for Business Server per generare il modello di corrispondenza corrispondente e la regola di traduzione.</span><span class="sxs-lookup"><span data-stu-id="e3636-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="e3636-106">In alternativa, è possibile eseguire manualmente un'espressione regolare di scrittura per definire il modello e la regola di traduzione corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="e3636-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="e3636-107">Per informazioni dettagliate, vedere [creare o modificare manualmente una regola di traduzione](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span><span class="sxs-lookup"><span data-stu-id="e3636-107">For details, see [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="e3636-108">Per definire una regola usando lo strumento crea una regola di traduzione</span><span class="sxs-lookup"><span data-stu-id="e3636-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="e3636-109">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e3636-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="e3636-110">Per iniziare a definire una regola di traduzione, seguire la procedura descritta in [configurare un trunk con il bypass multimediale in Skype for Business Server](configure-trunk-with-media-bypass.md) tramite il passaggio 10 o [configurare un trunk senza bypass multimediale in Skype for Business Server](configure-trunk-without-media-bypass.md) tramite il passaggio 9.</span><span class="sxs-lookup"><span data-stu-id="e3636-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="e3636-111">In **nome** nella pagina **nuova** regola di traduzione o **Modifica regola di traduzione** digitare un nome che descriva il modello di numero da tradurre.</span><span class="sxs-lookup"><span data-stu-id="e3636-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="e3636-112">Opzionale In **Descrizione**Digitare una descrizione della regola di traduzione, ad esempio le chiamate interurbane internazionali degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="e3636-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="e3636-113">Nella sezione **genera una regola di traduzione** della finestra di dialogo immettere i valori nei campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3636-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="e3636-114">**Cifre iniziali**: (facoltativo) specificare le cifre iniziali dei numeri a cui si vuole che corrisponda il motivo.</span><span class="sxs-lookup"><span data-stu-id="e3636-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="e3636-115">Ad esempio, immettere + in questo campo per abbinare i numeri nel formato E. 164 (che iniziano con +).</span><span class="sxs-lookup"><span data-stu-id="e3636-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="e3636-116">**Length**: specificare il numero di cifre nel criterio di corrispondenza e selezionare se si vuole che il pattern corrisponda a numeri di lunghezza uguale a quella specificata, almeno questa lunghezza o qualsiasi lunghezza.</span><span class="sxs-lookup"><span data-stu-id="e3636-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="e3636-117">Ad esempio, immettere 11 e selectAt almeno nell'elenco a discesa in base a numeri che hanno una lunghezza di almeno 11 cifre.</span><span class="sxs-lookup"><span data-stu-id="e3636-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="e3636-118">**Cifre da rimuovere**: (facoltativo) specificare il numero di cifre iniziali da eliminare.</span><span class="sxs-lookup"><span data-stu-id="e3636-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="e3636-119">Ad esempio, immettere 1 per eliminare il + dall'inizio del numero.</span><span class="sxs-lookup"><span data-stu-id="e3636-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="e3636-120">**Cifre da aggiungere**: (facoltativo) specificare le cifre da anteporre ai numeri tradotti.</span><span class="sxs-lookup"><span data-stu-id="e3636-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="e3636-121">Ad esempio, immetti 011 se vuoi che 011 venga anteposto ai numeri tradotti quando viene applicata la regola.</span><span class="sxs-lookup"><span data-stu-id="e3636-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

     <span data-ttu-id="e3636-122">I valori immessi in questi campi si riflettono nei campi della regola **per la corrispondenza** e la **traduzione** .</span><span class="sxs-lookup"><span data-stu-id="e3636-122">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields.</span></span> <span data-ttu-id="e3636-123">Ad esempio, se specifichi i valori di esempio precedenti, l'espressione regolare risultante nel campo **pattern to match** è:</span><span class="sxs-lookup"><span data-stu-id="e3636-123">For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

     <span data-ttu-id="e3636-124">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="e3636-124">^\+(\d{9}\d+)$</span></span>

     <span data-ttu-id="e3636-125">Il campo della **regola di traduzione** specifica un modello per il formato dei numeri tradotti.</span><span class="sxs-lookup"><span data-stu-id="e3636-125">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="e3636-126">Questo modello include due parti:</span><span class="sxs-lookup"><span data-stu-id="e3636-126">This pattern has two parts:</span></span>

   - <span data-ttu-id="e3636-127">Un valore, ad esempio $1, che rappresenta il numero di cifre nel modello corrispondente</span><span class="sxs-lookup"><span data-stu-id="e3636-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="e3636-128">Opzionale Un valore che puoi anteporre immettendolo nel campo **cifre da aggiungere**</span><span class="sxs-lookup"><span data-stu-id="e3636-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

     <span data-ttu-id="e3636-129">Usando i valori di esempio precedenti, viene visualizzato 011 $1 nel campo della **regola di traduzione** .</span><span class="sxs-lookup"><span data-stu-id="e3636-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

     <span data-ttu-id="e3636-130">Quando viene applicata questa regola di traduzione, + 441235551010 diventa 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="e3636-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="e3636-131">Fare clic su **OK** per salvare la regola di traduzione.</span><span class="sxs-lookup"><span data-stu-id="e3636-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="e3636-132">Fare clic su **OK** per salvare la configurazione trunk.</span><span class="sxs-lookup"><span data-stu-id="e3636-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="e3636-133">Nella pagina **trunk Configuration** fare clic su **commit**e quindi su **Commit all**.</span><span class="sxs-lookup"><span data-stu-id="e3636-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e3636-134">Ogni volta che si crea o si modifica una regola di traduzione, è necessario eseguire il comando **commit tutti** per pubblicare la modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="e3636-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="e3636-135">Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="e3636-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="e3636-136">Per definire manualmente una regola di traduzione</span><span class="sxs-lookup"><span data-stu-id="e3636-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="e3636-137">Aprire il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e3636-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="e3636-138">Per iniziare a definire una regola di traduzione, seguire la procedura descritta in [configurare un trunk con il bypass multimediale in Skype for Business Server](configure-trunk-with-media-bypass.md) tramite il passaggio 10 o [configurare un trunk senza bypass multimediale in Skype for Business Server](configure-trunk-without-media-bypass.md) tramite il passaggio 9.</span><span class="sxs-lookup"><span data-stu-id="e3636-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="e3636-139">Nel campo **nome** della pagina **nuova** regola di traduzione o **Modifica regola di traduzione** digitare un nome che descriva il modello di numero da tradurre.</span><span class="sxs-lookup"><span data-stu-id="e3636-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="e3636-140">Opzionale In **Descrizione**Digitare una descrizione della regola di traduzione, ad esempio le chiamate interurbane internazionali degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="e3636-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="e3636-141">Fare clic su **modifica** nella parte inferiore della sezione **Compila una regola di traduzione** .</span><span class="sxs-lookup"><span data-stu-id="e3636-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="e3636-142">Immettere le opzioni seguenti nell' **espressione regolare di tipo**:</span><span class="sxs-lookup"><span data-stu-id="e3636-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="e3636-143">In **Confronta questo modello**, specifica il motivo che verrà usato per corrispondere ai numeri da tradurre.</span><span class="sxs-lookup"><span data-stu-id="e3636-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="e3636-144">Nella **regola di traduzione**specificare un motivo per il formato dei numeri tradotti.</span><span class="sxs-lookup"><span data-stu-id="e3636-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

     <span data-ttu-id="e3636-145">Ad esempio, se si digita ^\+(\d{9}\d +) $ in **corrisponde a questo modello** And011 $1 nella **regola di traduzione**, la regola tradurrà + 441235551010 in 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="e3636-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="e3636-146">Fare clic su **OK** per salvare la regola di traduzione.</span><span class="sxs-lookup"><span data-stu-id="e3636-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="e3636-147">Fare clic su **OK** per salvare la configurazione trunk.</span><span class="sxs-lookup"><span data-stu-id="e3636-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="e3636-148">Nella pagina **trunk Configuration** fare clic su **commit**e quindi su **Commit all**.</span><span class="sxs-lookup"><span data-stu-id="e3636-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e3636-149">Ogni volta che si crea o si modifica una regola di traduzione, è necessario eseguire il comando **commit tutti** per pubblicare la modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="e3636-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="e3636-150">Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="e3636-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3636-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3636-151">See also</span></span>

[<span data-ttu-id="e3636-152">Configurare un trunk con il bypass multimediale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e3636-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="e3636-153">Configurare un trunk senza bypass multimediale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e3636-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="e3636-154">Pubblicare le modifiche in sospeso nella configurazione del routing vocale in Skype for business</span><span class="sxs-lookup"><span data-stu-id="e3636-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="e3636-155">Distribuire il bypass multimediale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e3636-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

