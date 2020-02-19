---
title: 'Lync Server 2013: utilizzo della connettività Lync-Skype come utente finale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd9602f629c5854a918debf63992b1b3ff54eb29
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42117339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a><span data-ttu-id="1f883-102">Utilizzo della connettività Lync-Skype in Lync Server 2013 come utente finale</span><span class="sxs-lookup"><span data-stu-id="1f883-102">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f883-103">_**Ultimo argomento modificato:** 2016-12-27_</span><span class="sxs-lookup"><span data-stu-id="1f883-103">_**Topic Last Modified:** 2016-12-27_</span></span>

<span data-ttu-id="1f883-104">La connettività Lync-Skype consente agli utenti di Skype e agli utenti di Lync di aggiungersi tra loro come contatti, scambiare messaggi istantanei e effettuare chiamate audio e video.</span><span class="sxs-lookup"><span data-stu-id="1f883-104">Lync-Skype Connectivity enables Skype users and Lync users to add each other as contacts, exchange instant messages and make audio and video calls.</span></span> <span data-ttu-id="1f883-105">Quando un utente di Skype aggiunge un utente Lync, un utente Skype creerà un contatto in Skype contenente l'URI (Uniform Resource Identifier) SIP (Session Initiation Protocol) dell'utente Lync.</span><span class="sxs-lookup"><span data-stu-id="1f883-105">When a Skype user adds a Lync user, a Skype user will create a contact in Skype containing the session initiation protocol (SIP) uniform resource identifier (URI) of the Lync user.</span></span> <span data-ttu-id="1f883-106">Viceversa, quando un utente di Lync aggiunge un contatto Skype, l'utente Lync creerà un contatto in Lync che conterrà l'account Microsoft (MSA) dell'utente Skype e non il nome utente Skype.</span><span class="sxs-lookup"><span data-stu-id="1f883-106">Conversely, when a Lync user adds a Skype contact, the Lync user will create a contact in Lync that will contain the Microsoft Account (MSA) of the Skype user, and not the Skype user name.</span></span>

<span data-ttu-id="1f883-107">**Che cos'è un MSA?**</span><span class="sxs-lookup"><span data-stu-id="1f883-107">**What is an MSA?**</span></span> <span data-ttu-id="1f883-108">Gli utenti Skype devono accedere a Skype con un account Microsoft (in precedenza denominato Windows Live ID) per comunicare con i contatti di Lync.</span><span class="sxs-lookup"><span data-stu-id="1f883-108">Skype users must sign in to Skype with a Microsoft account (previously called Windows Live ID) in order to communicate with Lync contacts.</span></span><span data-ttu-id="1f883-109">Un account Microsoft è costituito dalla combinazione di un indirizzo di posta elettronica e di una password, che può essere utilizzata anche per accedere a servizi quali tecnologia di archiviazione di Microsoft OneDrive, Windows Phone, Microsoft Xbox LIVE online Game Service e messaggistica di Microsoft Outlook e il client di collaborazione (e, in precedenza, il servizio di posta elettronica basato sul Web di Microsoft Hotmail o Windows Live Messenger).</span><span class="sxs-lookup"><span data-stu-id="1f883-109"> A Microsoft account consists of the combination of an email address and a password, which you can also use to sign in to services such as Microsoft OneDrive storage technology, Windows Phone, Microsoft Xbox LIVE online game service, and Microsoft Outlook messaging and collaboration client (and, previously, Microsoft Hotmail web-based e-mail service or Windows Live Messenger).</span></span><span data-ttu-id="1f883-110">Se si utilizza un indirizzo di posta elettronica e una password per accedere a questi o ad altri servizi, si dispone già di un account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1f883-110"> If you use an email address and a password to sign in to these or other services, you already have a Microsoft account.</span></span><span data-ttu-id="1f883-111">Per informazioni dettagliate sulla creazione di un account Microsoft, vedere la pagina di iscrizione all'account [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061)Microsoft all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="1f883-111"> For details about creating a Microsoft Account, see the Microsoft account sign-up page at [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061).</span></span> <span data-ttu-id="1f883-112">È possibile unire l'account Skype esistente con il proprio account Microsoft per l'accesso Single Sign-on, in una vasta gamma di applicazioni e servizi.</span><span class="sxs-lookup"><span data-stu-id="1f883-112">You can merge your existing Skype account with your Microsoft account for single sign-on, across a variety of applications and services.</span></span> <span data-ttu-id="1f883-113">Dopo che l'account è stato Unito, un utente Skype può inviare una richiesta di contatto agli utenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="1f883-113">Once the account is merged a Skype user can send a contact request to Lync users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1f883-114">Affinché gli utenti di Lync e Skype siano in piena comunicazione tra loro, è necessario soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f883-114">In order for Lync and Skype users to fully communicate with each other, the following requirements must be met:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="1f883-115">Gli utenti Skype devono essere connessi al client Skype con un account Microsoft (MSA).</span><span class="sxs-lookup"><span data-stu-id="1f883-115">Skype users must be logged into their Skype client with a Microsoft Account (MSA).</span></span></P>
> <LI>
> <P><span data-ttu-id="1f883-116">Gli utenti di Lync devono essere abilitati per la connettività di messaggistica istantanea pubblica da parte dell'amministratore di Lync.</span><span class="sxs-lookup"><span data-stu-id="1f883-116">Lync users must be enabled for public IM connectivity by their Lync administrator.</span></span></P>
> <LI>
> <P><span data-ttu-id="1f883-117">Quando un utente Skype aggiunge un contatto Lync, verificare che la parola Lync venga visualizzata sotto il nome del contatto.</span><span class="sxs-lookup"><span data-stu-id="1f883-117">When a Skype user adds a Lync contact, verify that the word Lync appears below the contact’s name.</span></span> <span data-ttu-id="1f883-118">Ciò indica che è stato trovato un URI di Lync.</span><span class="sxs-lookup"><span data-stu-id="1f883-118">This indicates that a Lync URI has been found.</span></span></P>
> <LI>
> <P><span data-ttu-id="1f883-119">Quando un utente Skype aggiunge un contatto Lync e vengono restituiti zero risultati della ricerca per tale dominio Lync, il processo di provisioning PIC potrebbe non essere stato completato oppure il dominio Lync non è stato ancora configurato.</span><span class="sxs-lookup"><span data-stu-id="1f883-119">When a Skype user adds a Lync contact and zero search results are returned for that Lync domain, the PIC provisioning process may not have completed, or the Lync domain has not yet been set up.</span></span></P>
> <LI>
> <P><span data-ttu-id="1f883-120">A seconda delle impostazioni di privacy degli utenti di Lync e Skype, la messaggistica istantanea, il video e la presenza potrebbero non funzionare finché i nuovi contatti non vengono accettati da ogni utente.</span><span class="sxs-lookup"><span data-stu-id="1f883-120">Depending on the privacy settings of the Lync and Skype users, IM, video, and presence may not work until the new contacts are accepted by each user.</span></span></P></LI></UL>



</div>

<span data-ttu-id="1f883-121">**Per aggiungere un contatto Skype a Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="1f883-121">**To add a Skype contact to Lync 2013**</span></span>

1.  <span data-ttu-id="1f883-122">Da Lync, fare clic su **Aggiungi contatto, aggiungere un contatto non nell'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="1f883-122">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="1f883-123">Dall'elenco dei provider di contatti disponibili, selezionare **Skype**.</span><span class="sxs-lookup"><span data-stu-id="1f883-123">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="1f883-124">Nel campo **indirizzo di messaggistica istantanea** , immettere l'account Microsoft (MSA) dell'utente Skype.</span><span class="sxs-lookup"><span data-stu-id="1f883-124">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user.</span></span>

4.  <span data-ttu-id="1f883-125">Nella casella a discesa **gruppo di contatti Aggiungi a** , selezionare un gruppo di contatti a cui aggiungere l'utente.</span><span class="sxs-lookup"><span data-stu-id="1f883-125">In the **Add to contact group** dropdown box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="1f883-126">Nella casella a discesa **imposta relazione di privacy** selezionare l'impostazione di contatto appropriata e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f883-126">In the **Set privacy relationship** dropdown box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="1f883-127">L'utente verrà ora visualizzato come contatto in Lync.</span><span class="sxs-lookup"><span data-stu-id="1f883-127">The user will now appear as a contact in Lync.</span></span> <span data-ttu-id="1f883-128">Seleziona l'utente, fai clic con il pulsante destro del mouse sul nome utente e fai clic su **Visualizza scheda contatto** per visualizzare le proprietà dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1f883-128">Select the user, right-click the user name, and click **See Contact Card** to view the user properties.</span></span> <span data-ttu-id="1f883-129">Ora è possibile stabilire una chiamata audio o video con l'utente Skype appena aggiunto.</span><span class="sxs-lookup"><span data-stu-id="1f883-129">You can now establish an audio or video call with the newly added Skype user.</span></span>

<span data-ttu-id="1f883-130">Per ulteriori informazioni sul supporto per i contatti, vedere [aggiungere un contatto in Lync](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).</span><span class="sxs-lookup"><span data-stu-id="1f883-130">For additional information on support for contacts, see [Add a contact in Lync](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).</span></span>

<span data-ttu-id="1f883-131">Quando l'account Microsoft di un utente Skype utilizza un nome di dominio personalizzato, ad esempio <strong>bob@contoso.com</strong> , un utente di Lync può aggiungere l'account Microsoft a Lync in due modi:</span><span class="sxs-lookup"><span data-stu-id="1f883-131">When a Skype user’s Microsoft account uses a custom domain name, such as <strong>bob@contoso.com</strong> , a Lync user can add that Microsoft account to Lync in two ways:</span></span>

1.  <span data-ttu-id="1f883-132">Utilizzare l'icona **Aggiungi contatto** o</span><span class="sxs-lookup"><span data-stu-id="1f883-132">Use the **Add a Contact** icon, or</span></span>

2.  <span data-ttu-id="1f883-133">Utilizzare la casella **trova un utente o una sala o** un campo numero.</span><span class="sxs-lookup"><span data-stu-id="1f883-133">Use the **Find someone or a room, or a dial a number** field.</span></span>

<span data-ttu-id="1f883-134">In ogni istanza, l'utente di Lync deve immettere il messaggio di posta elettronica dell'utente Skype nel formato seguente: <strong>User (Domain Name) @msn. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="1f883-134">In each instance, the Lync user must enter the Skype user’s email in the following format: <strong>user(domain name)@msn.com</strong> .</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1f883-135">Questo passaggio non è necessario per gli account Microsoft che utilizzano i seguenti nomi di dominio: <STRONG>@live. com, @hotmail. com o @outlook. com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1f883-135">This step is not required for Microsoft accounts that use the following domain names: <STRONG>@live.com, @hotmail.com or @outlook.com</STRONG>.</span></span> <span data-ttu-id="1f883-136">Per ulteriori informazioni sui nomi di dominio personalizzati supportati, vedere <A href="https://support.microsoft.com/kb/897567">supported Public IM Domains</A>.</span><span class="sxs-lookup"><span data-stu-id="1f883-136">For more information on supported custom domain names, see <A href="https://support.microsoft.com/kb/897567">Supported public IM domains</A>.</span></span>



</div>

<span data-ttu-id="1f883-137">**Per aggiungere un contatto Skype a Lync quando si utilizza un nome di dominio personalizzato**</span><span class="sxs-lookup"><span data-stu-id="1f883-137">**To add a Skype contact to Lync when using a custom domain name**</span></span>

1.  <span data-ttu-id="1f883-138">Da Lync, fare clic su **Aggiungi contatto, aggiungere un contatto non nell'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="1f883-138">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="1f883-139">Dall'elenco dei provider di contatti disponibili, selezionare **Skype**.</span><span class="sxs-lookup"><span data-stu-id="1f883-139">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="1f883-140">Nel campo **indirizzo di messaggistica istantanea** , immettere l'account Microsoft (MSA) dell'utente Skype nel formato <strong>utente (nome di dominio) @msn. com</strong>.</span><span class="sxs-lookup"><span data-stu-id="1f883-140">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user in the format <strong>user(domain name)@msn.com</strong>.</span></span> <span data-ttu-id="1f883-141">Pertanto, per l'utente bob@contoso.com, la voce <strong>sarebbe Bob (contoso. com) @msn.<strong> com.</span><span class="sxs-lookup"><span data-stu-id="1f883-141">So for user bob@contoso.com, the entry would be <strong>bob(contoso.com)@msn.com<strong> .</span></span>

4.  <span data-ttu-id="1f883-142">Nella casella di riepilogo a discesa **Aggiungi a gruppo di contatti** selezionare un gruppo di contatti a cui aggiungere l'utente.</span><span class="sxs-lookup"><span data-stu-id="1f883-142">In the **Add to contact group** drop-down list box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="1f883-143">Nella casella di riepilogo a discesa **imposta relazione di privacy** selezionare l'impostazione di contatto appropriata e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f883-143">In the **Set privacy relationship** drop-down list box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="1f883-144">Un utente di Lync può anche utilizzare la ricerca di una **persona o una stanza oppure comporre un campo numerico** in Lync e aggiungere un indirizzo simile al seguente <strong>(nome di dominio) @msn. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="1f883-144">A Lync user can also use the **Find someone or a room, or dial a number** field in Lync, and add an address that resembles the following <strong>user(domain name)@msn.com</strong> .</span></span> <span data-ttu-id="1f883-145">Pertanto, per l'account Microsoft bob@contoso.com, la voce sarebbe <strong>Bob (contoso. com) @msn. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="1f883-145">So for the bob@contoso.com Microsoft account, the entry would be <strong>bob(contoso.com)@msn.com</strong> .</span></span>

7.  <span data-ttu-id="1f883-146">Seguire i passaggi 4 e 5 precedenti in questa procedura per aggiungere il contatto a un gruppo di contatti e selezionare la relazione di privacy appropriata.</span><span class="sxs-lookup"><span data-stu-id="1f883-146">Follow steps 4 and 5 earlier in this procedure to add the contact to a contact group and to select the appropriate privacy relationship.</span></span>

<span data-ttu-id="1f883-147">**Per aggiungere un contatto Lync a Skype**</span><span class="sxs-lookup"><span data-stu-id="1f883-147">**To add a Lync contact to Skype**</span></span>

1.  <span data-ttu-id="1f883-148">Accedere a Skype.</span><span class="sxs-lookup"><span data-stu-id="1f883-148">Sign in to Skype.</span></span> <span data-ttu-id="1f883-149">È necessario che l'utente Skype sia connesso al proprio client Skype con un account Microsoft (MSA).</span><span class="sxs-lookup"><span data-stu-id="1f883-149">The Skype user must be logged into their Skype client with a Microsoft Account (MSA).</span></span>

2.  <span data-ttu-id="1f883-150">Selezionare l'icona Aggiungi contatti.</span><span class="sxs-lookup"><span data-stu-id="1f883-150">Select the Add Contacts icon.</span></span>

3.  <span data-ttu-id="1f883-151">Immettere l'URI SIP dell'utente Lync.</span><span class="sxs-lookup"><span data-stu-id="1f883-151">Enter the SIP URI of the Lync user.</span></span> <span data-ttu-id="1f883-152">Esempio: bob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1f883-152">For example, bob@contoso.com.</span></span>

4.  <span data-ttu-id="1f883-153">Quando Skype trova la corrispondenza nei risultati della ricerca, cercare la parola **Lync** al di sotto del nome dell'utente di Lync.</span><span class="sxs-lookup"><span data-stu-id="1f883-153">When Skype finds the match in the search results, look for the word **Lync** below the Lync user’s name.</span></span> <span data-ttu-id="1f883-154">Questo indica che Skype ha individuato correttamente l'URI SIP del client Lync.</span><span class="sxs-lookup"><span data-stu-id="1f883-154">This indicates Skype successfully located the Lync client’s SIP URI.</span></span> <span data-ttu-id="1f883-155">Fare clic sul nome.</span><span class="sxs-lookup"><span data-stu-id="1f883-155">Click the name.</span></span>

5.  <span data-ttu-id="1f883-156">Nell'angolo superiore destro della finestra, fare clic su Aggiungi ai contatti.</span><span class="sxs-lookup"><span data-stu-id="1f883-156">In the top right corner of the window, click Add to Contacts.</span></span>

6.  <span data-ttu-id="1f883-157">Il nuovo contatto viene ora aggiunto all'elenco dei contatti, ma verrà visualizzato un punto interrogativo anziché l'icona di stato finché non accetterà la richiesta.</span><span class="sxs-lookup"><span data-stu-id="1f883-157">The new contact is now added to your contact list, but you’ll see a question mark instead of their status icon until they accept your request.</span></span> <span data-ttu-id="1f883-158">Quando il nuovo contatto accetta la richiesta, sarà possibile vedere quando sono online, avviare conversazioni di messaggistica istantanea e effettuare chiamate audio e video.</span><span class="sxs-lookup"><span data-stu-id="1f883-158">When your new contact accepts your request, you will be able to see when they are online, initiate IM conversations, and make audio and video calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1f883-159">È necessario che l'amministratore di Lync Server configuri le impostazioni dei criteri dell'utente di Lync per consentire le richieste in arrivo.</span><span class="sxs-lookup"><span data-stu-id="1f883-159">The Lync Server administrator must configure the Lync user’s policy settings to allow incoming requests.</span></span> <span data-ttu-id="1f883-160">In caso contrario, l'utente di Lync non riceverà le richieste di contatto dall'utente Skype.</span><span class="sxs-lookup"><span data-stu-id="1f883-160">If not, the Lync user will not receive contact requests from the Skype user.</span></span> <span data-ttu-id="1f883-161">A seconda della configurazione delle impostazioni dei criteri dell'utente di Lync, la richiesta di aggiunta dell'utente Skype verrà visualizzata nella <STRONG>nuova</STRONG> scheda del client Lync. Per iniziare la comunicazione con l'utente Skype, l'utente di Lync deve aggiungere l'utente Skype all'elenco Preferiti o a un elenco di contatti.</span><span class="sxs-lookup"><span data-stu-id="1f883-161">Depending on the configuration of the Lync user’s policy settings, the request to add the Skype user will appear on the Lync client’s <STRONG>New</STRONG> tab. To begin communicating with the Skype user, the Lync user must add the Skype user to either the Favorites list or a contact list.</span></span> <span data-ttu-id="1f883-162">Nell'immagine seguente viene mostrato il percorso della <STRONG>nuova</STRONG> scheda nel client Lync.</span><span class="sxs-lookup"><span data-stu-id="1f883-162">The image below shows the location of the <STRONG>New</STRONG> tab in the Lync client.</span></span>

    
    </div>

<span data-ttu-id="1f883-163">Un utente di Lync deve configurare gli avvisi di Lync per garantire che le richieste inviate da un utente Skype vengano visualizzate e siano individuabili dall'utente Lync.</span><span class="sxs-lookup"><span data-stu-id="1f883-163">A Lync user must configure Lync alerts to ensure that requests sent from a Skype user appear and are discoverable by the Lync user.</span></span> <span data-ttu-id="1f883-164">Per configurare gli avvisi di Lync, completare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="1f883-164">To configure Lync alerts, complete the procedure that follows.</span></span>

<span data-ttu-id="1f883-165">**Per configurare gli avvisi di Lync**</span><span class="sxs-lookup"><span data-stu-id="1f883-165">**To configure Lync Alerts**</span></span>

1.  <span data-ttu-id="1f883-166">Dal client Lync, fare clic sull'icona **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="1f883-166">From the Lync client, click the **Options** icon.</span></span>

2.  <span data-ttu-id="1f883-167">Selezionare **avvisi**.</span><span class="sxs-lookup"><span data-stu-id="1f883-167">Select **Alerts**.</span></span>

3.  <span data-ttu-id="1f883-168">In **avvisi generali**, controlla **Dimmi quando qualcuno mi aggiunge all'elenco dei contatti**.</span><span class="sxs-lookup"><span data-stu-id="1f883-168">Under **General alerts**, check **Tell me when someone adds me to his or her contact list**.</span></span>

4.  <span data-ttu-id="1f883-169">In **contatti che non utilizzano Lync**, selezionare **Consenti inviti ma blocca tutte le altre comunicazioni**.</span><span class="sxs-lookup"><span data-stu-id="1f883-169">Under **Contacts not using Lync**, select **Allow invites but block all other communications**.</span></span>

5.  <span data-ttu-id="1f883-170">Fare clic su **OK** per chiudere la finestra Opzioni.</span><span class="sxs-lookup"><span data-stu-id="1f883-170">Click **OK** to close the Options window.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

