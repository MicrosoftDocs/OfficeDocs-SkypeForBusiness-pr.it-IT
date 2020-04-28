---
title: Configurare i Crediti comunicazioni per la propria organizzazione
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-apr2020
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: 8deb0d00365803ff8ae585f8f6d4dfefbf72108f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905588"
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="e3313-103">Configurare i Crediti comunicazioni per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="e3313-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="e3313-p101">Per usare i numeri verdi con Skype for business e Microsoft teams, sarà necessario configurare i crediti per le comunicazioni. Ti consigliamo inoltre di configurare i crediti per le comunicazioni per i piani di chiamata (nazionali o internazionali) e per gli utenti di servizi di audioconferenza che hanno la possibilità di effettuare chiamate in uscita a **qualsiasi destinazione**. Sono inclusi molti paesi/aree geografiche, ma alcune destinazioni potrebbero non essere incluse negli abbonamenti al piano chiamante o ai servizi di audioconferenza. Se non si configurano i crediti per le comunicazioni e si assegna una licenza per i **crediti di comunicazione** agli utenti e si esauriscono i minuti per l'organizzazione (a seconda del piano di chiamata o del piano di audioconferenza nel proprio paese/area geografica), gli utenti non potranno effettuare chiamate o effettuare la chiamata dalle riunioni di audioconferenza. È possibile ottenere altre informazioni, inclusi gli importi dei finanziamenti consigliati, leggendo [i crediti per le comunicazioni?](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="e3313-p101">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3313-109">Per scoprire quanto costa, [consulta i prezzi qui](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span><span class="sxs-lookup"><span data-stu-id="e3313-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a><span data-ttu-id="e3313-110">Passaggio 1: assegnare una licenza per i servizi di audioconferenza o per i piani di chiamata agli utenti</span><span class="sxs-lookup"><span data-stu-id="e3313-110">Step 1: Assign an Audio Conferencing or Calling Plan license to your users</span></span>

<span data-ttu-id="e3313-p102">Quando ti iscrivi, Ottieni un certo numero di minuti a seconda del paese/area geografica. È possibile cercare il proprio paese o l'area geografica nell'elenco di disponibilità per i servizi di [audioconferenza e le chiamate in piano](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans#select-your-country-or-region-to-see-whats-available-for-your-organization) per visualizzare il numero di minuti che si otterranno. Dopo aver usato questi minuti, le chiamate verranno disconnesse. Per evitare che ciò accada, è necessario configurare i crediti per le comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="e3313-p102">When you sign up, you get a certain number of minutes depending on your country/region. You can search for your country or region in the [Country or region availability list for Audio Conferencing and Calling Plans](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans#select-your-country-or-region-to-see-whats-available-for-your-organization) to see the number of minutes you will get. After you use those minutes, calls will be disconnected. To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="e3313-115">Per farlo, **occorre assegnare agli utenti una licenza per Audioconferenza o Sistema telefonico**.</span><span class="sxs-lookup"><span data-stu-id="e3313-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="e3313-p103">Assegnare una licenza per i servizi di **audioconferenza** agli utenti. Vedere [assegnare le licenze di Microsoft teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="e3313-p103">Assign an **Audio Conferencing** license to your users. See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>
    
    <span data-ttu-id="e3313-118">Dopo aver assegnato la licenza, è necessario impostare i servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="e3313-118">After you assign this license, you will need to set up audio conferencing.</span></span> <span data-ttu-id="e3313-119">Per istruzioni dettagliate, vedere [provare o acquistare servizi di audioconferenza in Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span><span class="sxs-lookup"><span data-stu-id="e3313-119">For step-by-step instructions, see [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span></span>
    
- <span data-ttu-id="e3313-p105">Assegnare un **sistema telefonico** e una licenza per un piano per chiamate **nazionali o nazionali e internazionali** agli utenti. Vedere [assegnare le licenze di Microsoft teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="e3313-p105">Assign **Phone System** and a **Domestic or Domestic and International** Calling Plan license to your users. See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e3313-122">Anche se non è necessario per i crediti per le comunicazioni, è comunque necessario assegnare anche un **piano per chiamate nazionali** o una licenza per il **piano di chiamate nazionali e internazionali** .</span><span class="sxs-lookup"><span data-stu-id="e3313-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="e3313-p106">Dopo aver assegnato queste licenze, sarà necessario ottenere i numeri di telefono per l'organizzazione e quindi assegnare tali numeri alle persone dell'organizzazione. Per istruzioni dettagliate, vedere [configurare i piani](set-up-calling-plans.md)per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="e3313-p106">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="e3313-125">Per altre informazioni, vedere [licenze per i componenti aggiuntivi Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="e3313-125">For more information, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="e3313-126">Passaggio 2: configurare i Crediti comunicazioni per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="e3313-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="e3313-127">Accedere alla nuova interfaccia di amministrazione di Microsoft 365 con l'account di lavoro o dell'Istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="e3313-127">Sign in to the new Microsoft 365 admin center with your work or school account.</span></span>
    
2. <span data-ttu-id="e3313-128">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft 365, vedere**servizi di acquisto**di **fatturazione** > .</span><span class="sxs-lookup"><span data-stu-id="e3313-128">In the left navigation of the Microsoft 365 admin center, go to **Billing** > **Purchase Services**.</span></span> <span data-ttu-id="e3313-129">Scorrere verso il basso e selezionare **componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e3313-129">Scroll down and select **Add-Ons**.</span></span>

3. <span data-ttu-id="e3313-130">Selezionare **crediti per comunicazioni**.</span><span class="sxs-lookup"><span data-stu-id="e3313-130">Select **Communications Credits**.</span></span>
    
4. <span data-ttu-id="e3313-131">Nella pagina di sottoscrizione **crediti comunicazioni** immettere le informazioni e quindi fare clic su **Avanti**:</span><span class="sxs-lookup"><span data-stu-id="e3313-131">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
   - <span data-ttu-id="e3313-p108">**Aggiungi fondi** Immettere l'importo da aggiungere al proprio account. Se l'opzione di ricarica automatica non è attiva, una volta esauriti i fondi, i Crediti comunicazioni saranno disabilitati (come il servizio per i numeri verdi in entrata). Per evitare di dover ricaricare fondi per i Crediti comunicazioni ogni volta che i fondi disponibili si esauriscono, si consiglia di attivare la funzionalità di autoricarica.</span><span class="sxs-lookup"><span data-stu-id="e3313-p108">**Add funds** Enter the amount that you want to add to your account. If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service). To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
   - <span data-ttu-id="e3313-135">**Autoricarica** L'autoricarica consente di aggiungere automaticamente fondi al saldo quando scende al di sotto dell'importo configurato.</span><span class="sxs-lookup"><span data-stu-id="e3313-135">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
     <span data-ttu-id="e3313-p109">È consigliabile utilizzare la funzione **Autoricarica** per evitare qualsiasi interruzione del servizio, nel caso in cui i Crediti comunicazioni arrivino a 0 (zero). Verrà inviata un'e-mail al completamento della transazione di ricarica, quando essa non va a buon fine (ad esempio una carta di credito scaduta) e anche quando i Crediti comunicazioni arrivano a 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="e3313-p109">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero). You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
   - <span data-ttu-id="e3313-138">**Somma di autoricarica** Nella casella **Ricarica con** indicare l'importo della ricarica da aggiungere automaticamente al proprio account quando il saldo va al di sotto dell'importo configurato.</span><span class="sxs-lookup"><span data-stu-id="e3313-138">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
   - <span data-ttu-id="e3313-p110">**Importo configurato** Specificare l'importo nella casella **Quando il credito scende al di sotto di**, che indicherà quando ' *attivare*  ' l'autoricarica. Quando il credito scende al di sotto di tale importo, l'importo di ricarica specificato verrà aggiunto automaticamente al saldo del tuo account.</span><span class="sxs-lookup"><span data-stu-id="e3313-p110">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge. Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
     > <span data-ttu-id="e3313-p111">I fondi verranno applicati solo ai servizi Crediti comunicazioni alle tariffe Microsoft pubblicate quando i servizi vengono utilizzati. Eventuali fondi non utilizzati entro 12 mesi dalla data di acquisto andranno persi.</span><span class="sxs-lookup"><span data-stu-id="e3313-p111">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used. Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
     > 
     > <span data-ttu-id="e3313-143">La fatturazione mensile per i crediti di comunicazione verrà applicata solo se è stato usato il fondo assegnato, per informazioni su come controllare l'utilizzo mensile, leggere il [report sull'utilizzo PSTN di Skype for business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span><span class="sxs-lookup"><span data-stu-id="e3313-143">Monthly billing for Communication Credits will only be applied if the alloted fund has been used, to learn how to check your monthly usage, read [Skype for Business PSTN usage report](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span></span>
    
5. <span data-ttu-id="e3313-144">Immettere le informazioni di pagamento e scegliere **Esecuzione dell'ordine**.</span><span class="sxs-lookup"><span data-stu-id="e3313-144">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="e3313-145">Se si è un cliente di licenze volume, è possibile scegliere il numero di contratto enterprise agreement per il pagamento.</span><span class="sxs-lookup"><span data-stu-id="e3313-145">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="e3313-146">Se si dispone di più numeri di enterprise agreement, sarà possibile selezionare il contratto enterprise agreement che si desidera utilizzare per il pagamento.</span><span class="sxs-lookup"><span data-stu-id="e3313-146">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="e3313-147">Sarà inoltre possibile specificare un numero d'ordine di acquisto per associare il numero di contratto enterprise agreement (se applicabile).</span><span class="sxs-lookup"><span data-stu-id="e3313-147">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="e3313-p113">Ogni organizzazione farà un diverso uso dei Piani per chiamate, a seconda del volume e delle tariffe. Sarà necessario chiedere questo tipo di dati di utilizzo al provider di servizi corrente. Per queste organizzazioni, che usano già Skype for Business online come provider di servizi, è possibile ottenere i dati di utilizzo esaminandoli in **Interfaccia di amministrazione di Skype for Business** > **Report** > **Dettagli dell'utilizzo della rete PSTN**.</span><span class="sxs-lookup"><span data-stu-id="e3313-p113">Each organization will have a different usage of Calling Plan volume and rates to consider. You will need to get this type of usage data from your current service provider. Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Skype for Business admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="e3313-151">Quando si configurano i crediti per le comunicazioni, è necessario esaminare l'uso delle chiamate per l'organizzazione per determinare gli importi necessari.</span><span class="sxs-lookup"><span data-stu-id="e3313-151">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts you need.</span></span> <span data-ttu-id="e3313-152">Per ottenere informazioni sull'uso delle chiamate, esaminare il report **Dettagli dell'utilizzo della rete PSTN**.</span><span class="sxs-lookup"><span data-stu-id="e3313-152">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="e3313-153">Questo report consente di esportare i record di dati delle chiamate in Excel se è necessario archiviare i dati o creare report personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e3313-153">This report lets you export the call data records to Excel if you need to store the data or create custom reports.</span></span> <span data-ttu-id="e3313-154">Per informazioni su come visualizzare l'utilizzo, leggere [report sull'uso PSTN di Skype for business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).</span><span class="sxs-lookup"><span data-stu-id="e3313-154">To learn how to see usage, read [Skype for Business PSTN usage report](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="e3313-155">Passaggio 3: assegnare agli utenti una licenza Crediti comunicazioni</span><span class="sxs-lookup"><span data-stu-id="e3313-155">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="e3313-156">Accedere con l'account di lavoro o dell'Istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="e3313-156">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="e3313-157">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft 365, accedere a utenti**attivi**degli **utenti** > e quindi selezionare un utente o utenti dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="e3313-157">In the left navigation of the Microsoft 365 admin center, go to **Users** > **Active users**, and then select a user or users from the list.</span></span>
    
3. <span data-ttu-id="e3313-158">Scegliere **licenze e app**.</span><span class="sxs-lookup"><span data-stu-id="e3313-158">Choose **Licenses and Apps**.</span></span>
    
4. <span data-ttu-id="e3313-159">Attivare o disattivare i **crediti di comunicazione** **su** attivato per assegnare la licenza e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e3313-159">Toggle **Communications Credits** to **On** to assign this license, and then select **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e3313-160">Anche se ad alcuni utenti è assegnata una licenza **Enterprise E5**, è consigliabile comunque procedere in questo modo.</span><span class="sxs-lookup"><span data-stu-id="e3313-160">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="e3313-161">Informazioni su piani e prezzi.</span><span class="sxs-lookup"><span data-stu-id="e3313-161">Want to know about plans and pricing?</span></span>

<span data-ttu-id="e3313-162">Per consultare piani e prezzi, consultare uno di questi link:</span><span class="sxs-lookup"><span data-stu-id="e3313-162">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="e3313-163">Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="e3313-163">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="e3313-164">Piani per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="e3313-164">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="e3313-165">Piani Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="e3313-165">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="e3313-166">Per visualizzare le informazioni, è anche possibile [accedere all'interfaccia di amministrazione di Microsoft 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) e**aggiungere abbonamenti**agli**abbonamenti** > alla **fatturazione** > .</span><span class="sxs-lookup"><span data-stu-id="e3313-166">You can also see information by [signing in to the Microsoft 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="e3313-167">Per visualizzare una tabella con la licenza o le licenze necessarie per ogni funzionalità, vedere licenze per i [componenti aggiuntivi Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="e3313-167">To see a table with the license or licenses you will need for each feature, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e3313-168">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e3313-168">Related topics</span></span>

- [<span data-ttu-id="e3313-169">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="e3313-169">Set up Skype for Business Online</span></span>](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [<span data-ttu-id="e3313-170">Configurare Cloud Voicemail - Guida per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="e3313-170">Set up Cloud Voicemail - Admin help</span></span>](set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="e3313-171">[Impostare Piani di chiamata](set-up-calling-plans.md) e [Piani di chiamata per Office 365](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="e3313-171">[Set up Calling Plans](set-up-calling-plans.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="e3313-172">Aggiungere fondi e gestire Credito per la comunicazione</span><span class="sxs-lookup"><span data-stu-id="e3313-172">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
  
 
