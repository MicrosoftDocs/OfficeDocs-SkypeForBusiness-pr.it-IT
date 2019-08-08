---
title: Creare o modificare un intervallo di numeri non assegnati in Skype for Business Server
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
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Creare, modificare o eliminare intervalli di numeri non assegnati per l'applicazione di annunci in Skype for Business Server VoIP aziendale. Ciò influenza il modo in cui vengono gestite le chiamate a numeri non assegnati.
ms.openlocfilehash: f3d646e2d838312ee90453c66d1e7bf239cf1537
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233523"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a><span data-ttu-id="7a503-104">Creare o modificare un intervallo di numeri non assegnati in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7a503-104">Create or modify an unassigned number range in Skype for Business Server</span></span>
 
<span data-ttu-id="7a503-105">Creare, modificare o eliminare intervalli di numeri non assegnati per l'applicazione di annunci in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="7a503-105">Create, modify or delete unassigned number ranges for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="7a503-106">Ciò influenza il modo in cui vengono gestite le chiamate a numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="7a503-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="7a503-107">Skype for Business Server ti consente di dire cosa succede alle chiamate in arrivo ai numeri di telefono validi per l'organizzazione, ma non viene assegnato a un utente o a un telefono.</span><span class="sxs-lookup"><span data-stu-id="7a503-107">Skype for Business Server enables you to say what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="7a503-108">Per gestire tali chiamate, è necessario configurare una tabella dei numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="7a503-108">To handle such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="7a503-109">È possibile usare la tabella per instradare le chiamate a un'applicazione di annuncio o a un server Messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="7a503-109">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>
  
<span data-ttu-id="7a503-110">La configurazione della tabella dei numeri non assegnati dipende dall'utilizzo previsto di questa.</span><span class="sxs-lookup"><span data-stu-id="7a503-110">How you configure the unassigned number table depends on how you want to use it.</span></span> <span data-ttu-id="7a503-111">È possibile configurare la tabella con tutti gli interni validi dell'organizzazione, solo con gli interni non assegnati o con una combinazione di numeri di entrambi i tipi.</span><span class="sxs-lookup"><span data-stu-id="7a503-111">You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers.</span></span> <span data-ttu-id="7a503-112">La tabella dei numeri non assegnati può includere sia numeri assegnati che numeri non assegnati ma viene chiamata solo se un chiamante compone un numero non assegnato.</span><span class="sxs-lookup"><span data-stu-id="7a503-112">The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned.</span></span> <span data-ttu-id="7a503-113">Se nella tabella dei numeri non assegnati si inseriscono tutti gli interni validi, è possibile specificare l'azione da eseguire quando un utente lascia l'organizzazione, senza alcuna necessità di riconfigurare la tabella.</span><span class="sxs-lookup"><span data-stu-id="7a503-113">If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table.</span></span> <span data-ttu-id="7a503-114">Se si includono estensioni non assegnate nella tabella, è possibile modificare l'azione che si verifica per i numeri specifici.</span><span class="sxs-lookup"><span data-stu-id="7a503-114">If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers.</span></span> <span data-ttu-id="7a503-115">Ad esempio, se si modifica l'estensione per il servizio di assistenza clienti, è possibile includere il vecchio numero di servizio clienti nella tabella e quindi assegnarlo a un annuncio che fornisce il nuovo numero.</span><span class="sxs-lookup"><span data-stu-id="7a503-115">For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>
  
## <a name="configure-unassigned-phone-numbers"></a><span data-ttu-id="7a503-116">Configurare i numeri di telefono non assegnati</span><span class="sxs-lookup"><span data-stu-id="7a503-116">Configure unassigned phone numbers</span></span>

<span data-ttu-id="7a503-117">Usare una delle procedure seguenti per configurare gli intervalli di numeri non assegnati per l'applicazione di annuncio.</span><span class="sxs-lookup"><span data-stu-id="7a503-117">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7a503-118">Prima di configurare la tabella dei numeri non assegnati, è necessario che il sistema disponga già di annunci definiti o di un operatore automatico di messaggistica UNIFICAta di Exchange.</span><span class="sxs-lookup"><span data-stu-id="7a503-118">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span> 
  
> [!TIP]
> <span data-ttu-id="7a503-119">Quando qualcuno chiama un numero non assegnato, Skype for Business Server esegue la ricerca nella tabella numeri non assegnati dall'alto verso il basso e usa il primo intervallo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="7a503-119">When someone calls an unassigned number, Skype for Business Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="7a503-120">Deve quindi essere specificata un'azione che si vuole eseguire come ultima risorsa per l'ultimo intervallo della tabella.</span><span class="sxs-lookup"><span data-stu-id="7a503-120">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="7a503-121">Per usare il pannello di controllo di Skype for Business Server per configurare i numeri di telefono non assegnati</span><span class="sxs-lookup"><span data-stu-id="7a503-121">To use Skype for Business Server Control Panel to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="7a503-122">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7a503-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="7a503-123">Per informazioni dettagliate, vedere delegare le **autorizzazioni di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="7a503-123">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="7a503-124">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7a503-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="7a503-125">Sulla barra di spostamento sinistra fare clic su **caratteristiche vocali**e quindi su **numero non assegnato**.</span><span class="sxs-lookup"><span data-stu-id="7a503-125">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="7a503-126">Nella pagina **numero non assegnati** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a503-126">On the **Unassigned Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="7a503-127">Per creare un nuovo intervallo di numeri, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7a503-127">To create a new number range, click **New**.</span></span> <span data-ttu-id="7a503-128">In **nome**Digitare un nome identificativo per l'intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="7a503-128">In **Name**, type an identifying name for this range of numbers.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="7a503-129">Dopo aver eseguito il commit del nuovo intervallo di numeri non assegnati al database, non è possibile modificare questo nome.</span><span class="sxs-lookup"><span data-stu-id="7a503-129">After you commit the new unassigned number range to the database, you cannot change this name.</span></span> 
  
   - <span data-ttu-id="7a503-130">Per modificare un intervallo di numeri esistente, digitare tutto o parte del nome dell'intervallo di numeri nel campo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="7a503-130">To modify an existing number range, type all or part of the name of the number range in the search field.</span></span> <span data-ttu-id="7a503-131">Nell'elenco di intervalli di numeri risultante fare clic sul nome desiderato, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="7a503-131">In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="7a503-132">Nel campo primo **intervallo di numeri** Digitare il numero iniziale dell'intervallo, quindi digitare il numero finale dell'intervallo nel secondo campo **intervallo di numeri** .</span><span class="sxs-lookup"><span data-stu-id="7a503-132">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
   - <span data-ttu-id="7a503-133">Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.</span><span class="sxs-lookup"><span data-stu-id="7a503-133">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="7a503-134">Se il numero di inizio dell'intervallo o il numero finale dell'intervallo include un numero di interno, sia il numero iniziale che il numero finale dell'intervallo devono includere un'estensione e il numero di interno deve essere uguale sia per il numero iniziale che per il numero finale.</span><span class="sxs-lookup"><span data-stu-id="7a503-134">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
   - <span data-ttu-id="7a503-135">Il numero deve corrispondere all'espressione regolare (Tel:)? \+)? [1-9] \d{0,17}(; EXT = [1-9] \d{0,9})?.</span><span class="sxs-lookup"><span data-stu-id="7a503-135">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="7a503-136">Questo significa che il numero può iniziare con la stringa tel: (se non specifichi quella stringa, verrà automaticamente aggiunta per te), un segno più (+) e una cifra da 1 a 9.</span><span class="sxs-lookup"><span data-stu-id="7a503-136">This means the number may begin with the string tel: (if you don't specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="7a503-137">Il numero di telefono può contenere fino a 17 cifre e può essere seguito da un interno nel formato ;ext= seguito dal numero dell'interno.</span><span class="sxs-lookup"><span data-stu-id="7a503-137">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
6. <span data-ttu-id="7a503-138">In **servizio annunci**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a503-138">In **Announcement service**, do one of the following:</span></span> 
    
   - <span data-ttu-id="7a503-139">Fare clic su **annuncio**.</span><span class="sxs-lookup"><span data-stu-id="7a503-139">Click **Announcement**.</span></span>
    
   - <span data-ttu-id="7a503-140">Fare clic su **messaggistica unificata di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="7a503-140">Click **Exchange UM**.</span></span>
    
7. <span data-ttu-id="7a503-141">Se nel passaggio precedente è stato fatto clic su **annuncio**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a503-141">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    <span data-ttu-id="7a503-142">un.</span><span class="sxs-lookup"><span data-stu-id="7a503-142">a.</span></span> <span data-ttu-id="7a503-143">In **FQDN del server di destinazione**, fare clic su **Seleziona**, fare clic sull'ID servizio del servizio applicazione che esegue l'applicazione di annuncio che gestirà le chiamate in arrivo in questo intervallo di numeri non assegnati e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7a503-143">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    <span data-ttu-id="7a503-144">b.</span><span class="sxs-lookup"><span data-stu-id="7a503-144">b.</span></span> <span data-ttu-id="7a503-145">In **annuncio**fare clic sull'annuncio da riprodurre per l'intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="7a503-145">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>
    
8. <span data-ttu-id="7a503-146">Se nel passaggio precedente è stato fatto clic su **um Exchange**, in **numero di telefono operatore automatico**fare clic su **Seleziona**, fare clic sul numero di telefono da usare per l'intervallo di numeri non assegnati e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7a503-146">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>
    
9. <span data-ttu-id="7a503-147">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7a503-147">Click **OK**.</span></span>
    
10. <span data-ttu-id="7a503-148">Nella pagina **numero non assegnati** verificare che gli intervalli di numeri non assegnati siano disposti nell'ordine desiderato.</span><span class="sxs-lookup"><span data-stu-id="7a503-148">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want.</span></span> <span data-ttu-id="7a503-149">Per modificare la posizione di un intervallo nella tabella, fare clic su uno o più nomi consecutivi nell'elenco di intervalli e quindi fare clic sulla freccia su o freccia giù.</span><span class="sxs-lookup"><span data-stu-id="7a503-149">To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="7a503-150">Skype for Business Server cerca nella tabella numeri non assegnati dall'alto verso il basso e usa il primo intervallo che corrisponde al numero non assegnato.</span><span class="sxs-lookup"><span data-stu-id="7a503-150">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="7a503-151">Se si hanno intervalli sovrapposti e un intervallo specifica un'ultima azione di ricorso, verificare che l'intervallo sia nella parte inferiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7a503-151">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span> 
  
11. <span data-ttu-id="7a503-152">Quando si hanno gli intervalli di numeri non assegnati nell'ordine desiderato, fare clic su **commit tutti**.</span><span class="sxs-lookup"><span data-stu-id="7a503-152">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="7a503-153">Per usare Skype for Business Server Management Shell per configurare i numeri di telefono non assegnati</span><span class="sxs-lookup"><span data-stu-id="7a503-153">To use Skype for Business Server Management Shell to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="7a503-154">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di **configurazione**Delegate.</span><span class="sxs-lookup"><span data-stu-id="7a503-154">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="7a503-155">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7a503-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="7a503-156">USA **New-CsUnassignedNumber** per creare un nuovo intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="7a503-156">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="7a503-157">Usare **Set-CsUnassignedNumber** per modificare un intervallo di numeri non assegnati esistente.</span><span class="sxs-lookup"><span data-stu-id="7a503-157">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="7a503-158">Se si hanno intervalli sovrapposti e si vogliono applicare gli intervalli in un ordine specifico, includere il parametro Priority.</span><span class="sxs-lookup"><span data-stu-id="7a503-158">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter.</span></span> <span data-ttu-id="7a503-159">L'intervallo con la priorità più alta verrà applicato alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="7a503-159">The range with the highest priority will be applied to the call.</span></span> <span data-ttu-id="7a503-160">Il valore 0 rappresenta la priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="7a503-160">The value 0 represents the highest priority.</span></span>
  
    <span data-ttu-id="7a503-161">Nella riga di comando eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a503-161">At the command line, do one of the following:</span></span>
    
   - <span data-ttu-id="7a503-162">Per creare un intervallo di numeri per un servizio di annuncio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="7a503-162">To create a number range for an Announcement service, run:</span></span>
    
     ```
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - <span data-ttu-id="7a503-163">In alternativa, per creare un intervallo di numeri per l'operatore automatico di messaggistica unificata di Exchange, eseguire:</span><span class="sxs-lookup"><span data-stu-id="7a503-163">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     <span data-ttu-id="7a503-164">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7a503-164">For example:</span></span>
    
     ```
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     <span data-ttu-id="7a503-165">O</span><span class="sxs-lookup"><span data-stu-id="7a503-165">Or</span></span>
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     <span data-ttu-id="7a503-166">L'esempio seguente mostra come modificare i numeri in un intervallo di numeri non assegnati esistente:</span><span class="sxs-lookup"><span data-stu-id="7a503-166">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
     ```
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a><span data-ttu-id="7a503-167">Eliminare un intervallo di numeri unnasigned</span><span class="sxs-lookup"><span data-stu-id="7a503-167">Delete an unnasigned number range</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="7a503-168">Per usare il pannello di controllo di Skype for Business Server per eliminare un intervallo di numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="7a503-168">To use Skype for Business Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="7a503-169">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7a503-169">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="7a503-170">Per informazioni dettagliate, vedere delegare le **autorizzazioni di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="7a503-170">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="7a503-171">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7a503-171">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="7a503-172">Sulla barra di spostamento sinistra fare clic su **caratteristiche vocali** e quindi su **numero non assegnato**.</span><span class="sxs-lookup"><span data-stu-id="7a503-172">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="7a503-173">Nel campo di ricerca della pagina **numero non assegnato** digitare tutto o parte del nome dell'intervallo di numeri non assegnati che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="7a503-173">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>
    
5. <span data-ttu-id="7a503-174">Nell'elenco risultante di intervalli di numeri fare clic sul nome, scegliere **modifica**e quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="7a503-174">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="7a503-175">Fare clic su **commit tutti**.</span><span class="sxs-lookup"><span data-stu-id="7a503-175">Click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="7a503-176">Per usare Skype for Business Server Management Shell per eliminare un intervallo di numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="7a503-176">To use Skype for Business Server Management Shell to delete an unassigned number range</span></span>

1. <span data-ttu-id="7a503-177">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di **configurazione**Delegate.</span><span class="sxs-lookup"><span data-stu-id="7a503-177">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="7a503-178">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7a503-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="7a503-179">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="7a503-179">At the command line, type:</span></span>
    
   ```
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    <span data-ttu-id="7a503-180">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7a503-180">For example:</span></span>
    
   ```
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > <span data-ttu-id="7a503-181">Per informazioni dettagliate su altre opzioni, vedere [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7a503-181">For details about more options, see [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7a503-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a503-182">See also</span></span>

[<span data-ttu-id="7a503-183">New-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="7a503-183">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="7a503-184">Set-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="7a503-184">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="7a503-185">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="7a503-185">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
