---
title: Creare o modificare un intervallo di numeri non assegnati in Skype for Business Server
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
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Creare, modificare o eliminare intervalli di numeri non assegnati per l'applicazione Annuncio in Skype for Business Server VoIP aziendale. Ciò influisce sulla modalità di gestione delle chiamate ai numeri non assegnati.
ms.openlocfilehash: 180db35a5ea7c2c55dcdbbdcb3be70f868149d88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837086"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a><span data-ttu-id="10ff2-104">Creare o modificare un intervallo di numeri non assegnati in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="10ff2-104">Create or modify an unassigned number range in Skype for Business Server</span></span>
 
<span data-ttu-id="10ff2-105">Creare, modificare o eliminare intervalli di numeri non assegnati per l'applicazione Annuncio in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="10ff2-105">Create, modify or delete unassigned number ranges for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="10ff2-106">Ciò influisce sulla modalità di gestione delle chiamate ai numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="10ff2-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="10ff2-107">Skype for Business Server consente di dire cosa succede alle chiamate in arrivo a numeri di telefono validi per l'organizzazione, ma non assegnati a un utente o a un telefono.</span><span class="sxs-lookup"><span data-stu-id="10ff2-107">Skype for Business Server enables you to say what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="10ff2-108">Per gestire tali chiamate, è necessario impostare una tabella dei numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="10ff2-108">To handle such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="10ff2-109">È possibile utilizzare la tabella per instradare le chiamate a un'applicazione Annuncio o a un server Messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="10ff2-109">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>
  
<span data-ttu-id="10ff2-p104">La configurazione della tabella dei numeri non assegnati dipende dal modo in cui si desidera utilizzarla. È possibile configurare la tabella con tutti gli interni validi dell'organizzazione, solo con gli interni non assegnati o con una combinazione di numeri di entrambi i tipi. La tabella dei numeri non assegnati può includere sia numeri assegnati che numeri non assegnati ma viene richiamata solo se un chiamante compone un numero non assegnato. Se nella tabella dei numeri non assegnati si inseriscono tutti gli interni validi, è possibile specificare l'azione da eseguire quando un utente lascia l'organizzazione, senza alcuna necessità di riconfigurare la tabella. Se nella tabella si inseriscono interni non assegnati, è possibile modificare l'azione da eseguire per numeri specifici. Se ad esempio si modifica l'interno del servizio di assistenza clienti, è possibile inserire il vecchio numero nella tabella e quindi assegnarlo a un annuncio in cui viene indicato il nuovo numero.</span><span class="sxs-lookup"><span data-stu-id="10ff2-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>
  
## <a name="configure-unassigned-phone-numbers"></a><span data-ttu-id="10ff2-116">Configurare i numeri di telefono non assegnati</span><span class="sxs-lookup"><span data-stu-id="10ff2-116">Configure unassigned phone numbers</span></span>

<span data-ttu-id="10ff2-117">Utilizzare una delle procedure seguenti per configurare intervalli di numeri non assegnati per l'applicazione Annuncio.</span><span class="sxs-lookup"><span data-stu-id="10ff2-117">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="10ff2-118">Prima di configurare la tabella dei numeri non assegnati, è necessario che nel sistema sia già stato definito Annuncio o che sia stata configurata una Operatore automatico messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="10ff2-118">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span> 
  
> [!TIP]
> <span data-ttu-id="10ff2-119">Quando qualcuno chiama un numero non assegnato, Skype for Business Server cerca la tabella dei numeri non assegnati dall'alto verso il basso e usa il primo intervallo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="10ff2-119">When someone calls an unassigned number, Skype for Business Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="10ff2-120">Pertanto, per l'ultimo intervallo della tabella è consigliabile specificare un'azione che si desidera venga eseguita come ultima risorsa.</span><span class="sxs-lookup"><span data-stu-id="10ff2-120">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="10ff2-121">Per usare il Pannello di controllo di Skype for Business Server per configurare i numeri di telefono non assegnati</span><span class="sxs-lookup"><span data-stu-id="10ff2-121">To use Skype for Business Server Control Panel to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="10ff2-p106">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="10ff2-p106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="10ff2-124">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="10ff2-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="10ff2-125">Sulla barra di spostamento sinistra fare clic su **Funzionalità vocali** e quindi su **Numero non assegnato**.</span><span class="sxs-lookup"><span data-stu-id="10ff2-125">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="10ff2-126">Nella pagina **Numero non assegnato** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="10ff2-126">On the **Unassigned Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="10ff2-p107">Per creare un nuovo intervallo di numeri, fare clic su **Nuovo**. In **Nome** digitare un nome che identifichi l'intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="10ff2-p107">To create a new number range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="10ff2-129">Dopo l'esecuzione del commit del nuovo intervallo di numeri non assegnati nel database non sarà possibile modificare il nome.</span><span class="sxs-lookup"><span data-stu-id="10ff2-129">After you commit the new unassigned number range to the database, you cannot change this name.</span></span> 
  
   - <span data-ttu-id="10ff2-p108">Per modificare un intervallo di numeri esistente, digitare tutto o una parte del nome dell'intervallo di numeri nel campo di ricerca. Nell'elenco di intervalli di numeri risultante fare clic sul nome desiderato, su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="10ff2-p108">To modify an existing number range, type all or part of the name of the number range in the search field. In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="10ff2-132">Nel primo campo **Intervallo numeri** digitare il numero iniziale dell'intervallo e nel secondo campo **Intervallo numeri** digitare il numero finale.</span><span class="sxs-lookup"><span data-stu-id="10ff2-132">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
   - <span data-ttu-id="10ff2-133">Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.</span><span class="sxs-lookup"><span data-stu-id="10ff2-133">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="10ff2-134">Se il numero iniziale o il numero finale dell'intervallo include un numero di interno, devono includerlo entrambi. Il numero di interno deve essere lo stesso per ambedue.</span><span class="sxs-lookup"><span data-stu-id="10ff2-134">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
   - <span data-ttu-id="10ff2-135">Il numero deve corrispondere all'espressione regolare (tel:)?( \+ )? [1-9]\d {0,17} (;ext=[1-9]\d {0,9} )?.</span><span class="sxs-lookup"><span data-stu-id="10ff2-135">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="10ff2-136">Questo significa che il numero può iniziare con la stringa tel: (se non si specifica tale stringa, verrà aggiunta automaticamente), un segno più (+) e una cifra da 1 a 9.</span><span class="sxs-lookup"><span data-stu-id="10ff2-136">This means the number may begin with the string tel: (if you don't specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="10ff2-137">Il numero di telefono può contenere fino a 17 cifre e può essere seguito da un interno nel formato ;ext= seguito dal numero dell'interno.</span><span class="sxs-lookup"><span data-stu-id="10ff2-137">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
6. <span data-ttu-id="10ff2-138">In **Servizio Annuncio** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="10ff2-138">In **Announcement service**, do one of the following:</span></span> 
    
   - <span data-ttu-id="10ff2-139">Fare clic su **Annuncio**.</span><span class="sxs-lookup"><span data-stu-id="10ff2-139">Click **Announcement**.</span></span>
    
   - <span data-ttu-id="10ff2-140">Fare clic su **Messaggistica unificata di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="10ff2-140">Click **Exchange UM**.</span></span>
    
7. <span data-ttu-id="10ff2-141">Se nel passaggio precedente si è fatto clic su **Annuncio**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="10ff2-141">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    <span data-ttu-id="10ff2-142">a.</span><span class="sxs-lookup"><span data-stu-id="10ff2-142">a.</span></span> <span data-ttu-id="10ff2-143">In **FQDN del server di destinazione** fare clic su **Seleziona**, sull'ID del servizio applicazione che esegue l'applicazione Annuncio che gestirà le chiamate in arrivo per questo intervallo di numeri non assegnati e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="10ff2-143">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    <span data-ttu-id="10ff2-144">b.</span><span class="sxs-lookup"><span data-stu-id="10ff2-144">b.</span></span> <span data-ttu-id="10ff2-145">In **Annuncio** fare clic sull'annuncio da riprodurre per l'intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="10ff2-145">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>
    
8. <span data-ttu-id="10ff2-146">Se nel passaggio precedente si è fatto clic su **Messaggistica unificata di Exchange**, in **Numero di telefono operatore automatico** fare clic su **Seleziona**, quindi sul numero di telefono da utilizzare per l'intervallo di numeri non assegnati e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="10ff2-146">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>
    
9. <span data-ttu-id="10ff2-147">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="10ff2-147">Click **OK**.</span></span>
    
10. <span data-ttu-id="10ff2-p112">Nella pagina **Numero non assegnato** verificare che gli intervalli di numeri non assegnati siano disposti nell'ordine desiderato. Per modificare la posizione di un intervallo nella tabella, fare clic su uno o più nomi consecutivi nell'elenco di intervalli e quindi fare clic sulla freccia in su o sulla freccia in giù.</span><span class="sxs-lookup"><span data-stu-id="10ff2-p112">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want. To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="10ff2-150">Skype for Business Server cerca la tabella dei numeri non assegnati dall'alto verso il basso e utilizza il primo intervallo che corrisponde al numero non assegnato.</span><span class="sxs-lookup"><span data-stu-id="10ff2-150">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="10ff2-151">Se vi sono intervalli che si sovrappongono e per un intervallo è specificata un'azione da eseguire come ultimo tentativo, verificare che tale intervallo si trovi alla fine dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="10ff2-151">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span> 
  
11. <span data-ttu-id="10ff2-152">Quando gli intervalli di numeri non assegnati si trovano nell'ordine desiderato, fare clic su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="10ff2-152">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="10ff2-153">Per utilizzare Skype for Business Server Management Shell per configurare i numeri di telefono non assegnati</span><span class="sxs-lookup"><span data-stu-id="10ff2-153">To use Skype for Business Server Management Shell to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="10ff2-154">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in Delegare le autorizzazioni di **installazione.**</span><span class="sxs-lookup"><span data-stu-id="10ff2-154">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="10ff2-155">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="10ff2-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="10ff2-156">Utilizzare **New-CsUnassignedNumber** per creare un nuovo intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="10ff2-156">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="10ff2-157">Utilizzare **Set-CsUnassignedNumber** per modificare un intervallo di numeri non assegnati esistente.</span><span class="sxs-lookup"><span data-stu-id="10ff2-157">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="10ff2-158">Se vi sono intervalli che si sovrappongono e si desidera che gli intervalli vengano applicati in un ordine specifico, includere il parametro Priority.</span><span class="sxs-lookup"><span data-stu-id="10ff2-158">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter.</span></span> <span data-ttu-id="10ff2-159">Alla chiamata verrà applicato l'intervallo con la priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="10ff2-159">The range with the highest priority will be applied to the call.</span></span> <span data-ttu-id="10ff2-160">Il valore 0 rappresenta la priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="10ff2-160">The value 0 represents the highest priority.</span></span>
  
    <span data-ttu-id="10ff2-161">Nella riga di comando eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="10ff2-161">At the command line, do one of the following:</span></span>
    
   - <span data-ttu-id="10ff2-162">Per creare un intervallo di numeri per un servizio Annuncio, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="10ff2-162">To create a number range for an Announcement service, run:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - <span data-ttu-id="10ff2-163">Per creare un intervallo di numeri per l'Operatore automatico messaggistica unificata di Exchange, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="10ff2-163">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     <span data-ttu-id="10ff2-164">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="10ff2-164">For example:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     <span data-ttu-id="10ff2-165">Oppure</span><span class="sxs-lookup"><span data-stu-id="10ff2-165">Or</span></span>
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     <span data-ttu-id="10ff2-166">Nell'esempio seguente viene illustrato come modificare i numeri di un intervallo di numeri non assegnati esistente:</span><span class="sxs-lookup"><span data-stu-id="10ff2-166">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a><span data-ttu-id="10ff2-167">Eliminare un intervallo di numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="10ff2-167">Delete an unnasigned number range</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="10ff2-168">Per utilizzare il Pannello di controllo di Skype for Business Server per eliminare un intervallo di numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="10ff2-168">To use Skype for Business Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="10ff2-p116">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="10ff2-p116">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="10ff2-171">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="10ff2-171">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="10ff2-172">Sulla barra di spostamento sinistra fare clic su **Funzionalità vocali** e quindi su **Numero non assegnato**.</span><span class="sxs-lookup"><span data-stu-id="10ff2-172">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="10ff2-173">Nel campo di ricerca della pagina **Numero non assegnato** digitare per intero o in parte il nome dell'intervallo di numeri non assegnati che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="10ff2-173">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>
    
5. <span data-ttu-id="10ff2-174">Nell'elenco risultante degli intervalli di numeri fare clic sul nome, su **Modifica** e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="10ff2-174">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="10ff2-175">Fare clic su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="10ff2-175">Click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="10ff2-176">Per utilizzare Skype for Business Server Management Shell per eliminare un intervallo di numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="10ff2-176">To use Skype for Business Server Management Shell to delete an unassigned number range</span></span>

1. <span data-ttu-id="10ff2-177">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in Delegare le autorizzazioni di **installazione.**</span><span class="sxs-lookup"><span data-stu-id="10ff2-177">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="10ff2-178">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="10ff2-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="10ff2-179">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="10ff2-179">At the command line, type:</span></span>
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    <span data-ttu-id="10ff2-180">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="10ff2-180">For example:</span></span>
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > <span data-ttu-id="10ff2-181">Per informazioni dettagliate su altre opzioni, [vedere Remove-CsCallParkOrbit.](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="10ff2-181">For details about more options, see [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="10ff2-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10ff2-182">See also</span></span>

[<span data-ttu-id="10ff2-183">New-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="10ff2-183">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="10ff2-184">Set-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="10ff2-184">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="10ff2-185">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="10ff2-185">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
