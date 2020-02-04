---
title: Pubblicazione di Office Web Apps Server tramite un server proxy inverso
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43a81fff75adbeadb6cfcead3316dab2c89b4269
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a><span data-ttu-id="deeb7-102">Pubblicazione di Office Web Apps Server in Lync Server 2013 con un server proxy inverso</span><span class="sxs-lookup"><span data-stu-id="deeb7-102">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="deeb7-103">_**Argomento Ultima modifica:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="deeb7-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="deeb7-104">Se si vuole che gli utenti esterni (ovvero gli utenti che accedono dall'esterno del firewall dell'organizzazione) abbiano accesso alle presentazioni di PowerPoint in Office Web Apps Server, è necessario usare Office Web Apps Server e un server proxy inverso, ad esempio Microsoft Forefront Gateway di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="deeb7-104">If you want external users (that is, users logging on from outside your organization’s firewall) to have access to Office Web Apps Server PowerPoint presentations then you will need to use Office Web Apps Server and a reverse proxy server such as Microsoft Forefront Threat Management Gateway.</span></span> <span data-ttu-id="deeb7-105">Ciò significa anche che dovrai creare e configurare una regola di pubblicazione del sito Web; Questa regola consentirà di garantire agli utenti la possibilità di connettersi al server.</span><span class="sxs-lookup"><span data-stu-id="deeb7-105">That also means that you will need to create and configure a website publishing rule; that rule will help ensure that users are able to connect to the server.</span></span> <span data-ttu-id="deeb7-106">Se non è necessario consentire l'accesso a utenti esterni, non è necessario configurare una regola di pubblicazione del sito Web.</span><span class="sxs-lookup"><span data-stu-id="deeb7-106">If you do not need to provide access to external users then you do not need to configure a website publishing rule.</span></span>

<span data-ttu-id="deeb7-107">Per configurare una regola di pubblicazione del sito Web in Forefront Threat Management Gateway, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="deeb7-107">To configure a website publishing rule in Forefront Threat Management Gateway complete the following procedure:</span></span>

1.  <span data-ttu-id="deeb7-108">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Microsoft Forefront TMG**e quindi su **gestione di Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-108">Click **Start**, click **All Programs**, click **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="deeb7-109">In Forefront TMG fare clic con il pulsante destro del mouse su **criteri firewall**, scegliere **nuovo**e quindi fare clic su **regola pubblicazione sito Web**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-109">In Forefront TMG, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="deeb7-110">Nella pagina **Introduzione** alla nuova regola di pubblicazione Web digitare un nome per la nuova regola nella casella **Nome regola pubblicazione** Web, ad esempio **regola del server di Office Web Apps**, e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-110">In the New Web Publishing Rule Wizard, on the **Welcome to the New Web Publishing Rule Wizard** page, type a name for your new rule in the **Web publishing rule name** box (for example, **Office Web Apps Server Rule**) and then click **Next**.</span></span>

4.  <span data-ttu-id="deeb7-111">Nella pagina **specifica azione regola** selezionare **Consenti** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-111">On the **Specify Rule Action** page, select **Allow** and then click **Next**.</span></span>

5.  <span data-ttu-id="deeb7-112">Nella pagina **tipo di pubblicazione** selezionare **pubblica un singolo sito Web o bilanciamento del carico** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-112">On the **Publishing Type** page, select **Publish a single Web site or load balancer** and then click **Next**.</span></span>

6.  <span data-ttu-id="deeb7-113">Nella pagina **sicurezza connessione server** selezionare **Usa SSL per connettersi al server Web pubblicato o alla server farm** , quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-113">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm** and then click **Next**.</span></span>

7.  <span data-ttu-id="deeb7-114">Nella pagina **Internal Publishing Details** Digitare il nome di dominio completo del server di Office Web Apps, ad esempio **officewebapps01.contoso.com**, nella casella **Name sito interno** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-114">On the **Internal Publishing Details** page, type the FQDN of your Office Web Apps server (for example, **officewebapps01.contoso.com**) in the **Internal site name** box and then click **Next**.</span></span> <span data-ttu-id="deeb7-115">Il nome immesso nella casella **nome sito interno** deve essere visualizzato nel campo oggetto o nel campo nome alternativo oggetto del certificato assegnato a Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="deeb7-115">The name entered in the **Internal site name** box must appear in the Subject field or the Subject Alternative Name field of the certificate you have assigned to Office Web Apps Server.</span></span>

8.  <span data-ttu-id="deeb7-116">Nella pagina **Dettagli pubblicazione interna** Digitare \*\* / \*\* la casella **percorso (facoltativo)** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-116">On the **Internal Publishing Details** page, type **/\*** in the **Path (optional)** box and then click **Next**.</span></span> <span data-ttu-id="deeb7-117">La sintassi\* //consente di verificare che tutte le cartelle e le sottocartelle per il sito vengano pubblicate.</span><span class="sxs-lookup"><span data-stu-id="deeb7-117">The /\* syntax will help ensure that all the folders and subfolders for the site are published.</span></span>

9.  <span data-ttu-id="deeb7-118">Nella pagina **Dettagli nome pubblico** selezionare **questo nome di dominio (digitare di seguito)** nell'elenco a discesa **accetta richieste per** e quindi digitare il qualificato per il server Office Web Apps nella casella nome pubblico.</span><span class="sxs-lookup"><span data-stu-id="deeb7-118">On the **Public Name Details** page, select **This domain name (type below)** from the **Accept requests for** drop-down list and then type the fully qualified for your Office Web Apps Server in the Public name box.</span></span> <span data-ttu-id="deeb7-119">Questo nome deve essere il nome usato per accedere al sito Web.</span><span class="sxs-lookup"><span data-stu-id="deeb7-119">This name should be the name used to access your website.</span></span> <span data-ttu-id="deeb7-120">Ad esempio, se si accede al sito usando l'URL http://officewebapps01.contoso.com , è necessario immettere **officewebapps01.contoso.com** nella casella **nome pubblico** .</span><span class="sxs-lookup"><span data-stu-id="deeb7-120">For example, if your site is accessed using the URL http://officewebapps01.contoso.com then you should enter **officewebapps01.contoso.com** in the **Public name** box.</span></span>

10. <span data-ttu-id="deeb7-121">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-121">Click **Next**.</span></span>

11. <span data-ttu-id="deeb7-122">Nella pagina **Seleziona listener Web** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-122">On the **Select Web Listener** page, click **New**.</span></span>

12. <span data-ttu-id="deeb7-123">Nella creazione guidata nuova definizione listener Web digitare un nome per il nuovo listener Web (ad esempio **SSL**) nella casella **nome listener** Web e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-123">In the New Web Listener Definition Wizard, type a name for the new Web listener (for example, **SSL**) in the **Web listener name** box and then click **Next**.</span></span>

13. <span data-ttu-id="deeb7-124">Nella pagina **sicurezza connessione client** selezionare **Richiedi connessioni protette SSL con i client** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-124">On the **Client Connection Security** page, select **Require SSL secured connections with clients** and then click **Next**.</span></span>

14. <span data-ttu-id="deeb7-125">Nella pagina **indirizzi IP del listener Web** selezionare **esterno**, selezionare **interno**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-125">On the **Web Listener IP Addresses** page, select **External**, select **Internal**, and then click **Next**.</span></span>

15. <span data-ttu-id="deeb7-126">Nella pagina **certificati SSL listener** selezionare **Usa un singolo certificato per il listener Web** e quindi fare clic su **Seleziona certificato**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-126">On the **Listener SSL Certificates** page, select **Use a single certificate for this Web Listener** and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="deeb7-127">Nella finestra di dialogo **Seleziona certificato** selezionare il certificato da usare per il listener Web e quindi fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-127">In the **Select Certificate** dialog box, select the certificate to be used for this Web Listener and then click **Select**.</span></span>

17. <span data-ttu-id="deeb7-128">Nella pagina **certificati SSL listener** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-128">On the **Listener SSL Certificates** page, click **Next**.</span></span>

18. <span data-ttu-id="deeb7-129">Nella pagina **impostazioni di autenticazione** selezionare **Nessuna autenticazione** dall'elenco **a discesa selezionare il modo in cui i client impareranno le credenziali per i clienti di Forefront TMG** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-129">On the **Authentication Settings** page, select **No Authentication** from the **Select how clients will provide credentials to Forefront TMG** drop-down list, and then click **Next**.</span></span>

19. <span data-ttu-id="deeb7-130">Nella pagina **Impostazioni Single Sign-in** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-130">On the **Single Sign On Settings** page, click **Next**.</span></span>

20. <span data-ttu-id="deeb7-131">Nella pagina **completamento della creazione guidata nuovo listener Web** esaminare il riepilogo delle opzioni di configurazione effettuate.</span><span class="sxs-lookup"><span data-stu-id="deeb7-131">On the **Completing the New Web Listener Wizard** page, review the summary of the configuration choices you have made.</span></span> <span data-ttu-id="deeb7-132">Una volta pronti, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-132">When ready, click **Finish**.</span></span>

21. <span data-ttu-id="deeb7-133">Nella pagina **Seleziona listener Web** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-133">On the **Select Web Listener** page, click **Next**.</span></span>

22. <span data-ttu-id="deeb7-134">Nella pagina **Delega autenticazione** selezionare **Nessuna delega, ma il client può eseguire** l'autenticazione direttamente dal **selezionare il metodo usato da Forefront TMG per eseguire l'autenticazione nell'elenco a discesa del server Web pubblicato** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-134">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly** from the **Select the method used by Forefront TMG to authenticate to the published Web server** drop-down list and then click **Next**.</span></span>

23. <span data-ttu-id="deeb7-135">Nella pagina **set di utenti** verificare che siano elencati i set di utenti appropriati.</span><span class="sxs-lookup"><span data-stu-id="deeb7-135">On the **User Sets** page, confirm that the appropriate user sets are listed.</span></span> <span data-ttu-id="deeb7-136">Per impostazione predefinita, questo è il set di **utenti all** Users.</span><span class="sxs-lookup"><span data-stu-id="deeb7-136">By default, this is the **All Users** user set.</span></span> <span data-ttu-id="deeb7-137">Fare clic su **Aggiungi** per aggiungere altri set di utenti che possono essere stati definiti.</span><span class="sxs-lookup"><span data-stu-id="deeb7-137">Click **Add** to add other user sets you may have defined.</span></span> <span data-ttu-id="deeb7-138">Al termine, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-138">When complete, click **Next**.</span></span>

24. <span data-ttu-id="deeb7-139">Nella pagina **completamento della nuova creazione guidata regola Web Publishing** fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-139">On the **Completing the New Web Publishing Rule Wizard** page, click **Finish**.</span></span>

<span data-ttu-id="deeb7-140">Tieni presente che fare clic su **fine** non significa che hai completato il processo; Questo significa che non si applica automaticamente e Abilita la nuova regola.</span><span class="sxs-lookup"><span data-stu-id="deeb7-140">Note that clicking **Finish** does not mean that you completed the process; that is, this does not automatically apply and enable the new rule.</span></span> <span data-ttu-id="deeb7-141">Sarà invece necessario fare clic sul pulsante **applica** che verrà visualizzato nell'interfaccia utente di Forefront TMG.</span><span class="sxs-lookup"><span data-stu-id="deeb7-141">Instead, you will need to click the **Apply** button that will appear in the Forefront TMG user interface.</span></span> <span data-ttu-id="deeb7-142">Quando si fa clic su **applica** viene visualizzata la finestra di dialogo **Descrizione modifica configurazione** .</span><span class="sxs-lookup"><span data-stu-id="deeb7-142">When you click **Apply** the **Configuration Change Description** dialog box will appear.</span></span> <span data-ttu-id="deeb7-143">Fare clic su **applica** nella finestra di dialogo per abilitare la nuova regola di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="deeb7-143">Click **Apply** in that dialog box to enable the new publishing rule.</span></span>

<span data-ttu-id="deeb7-144">Dopo l'applicazione della nuova regola, sarà necessario apportare alcune modifiche minime alla regola per verificare che gli utenti possano usare le nuove funzionalità di presentazione di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="deeb7-144">After your new rule has been applied, you will then need to make some minor modifications to the rule to make sure that users can use the new PowerPoint presentation capabilities.</span></span> <span data-ttu-id="deeb7-145">Per eseguire questa operazione, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="deeb7-145">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="deeb7-146">In Forefront TMG fare clic con il pulsante destro del mouse sul nome della nuova regola di pubblicazione e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-146">In Forefront TMG, right-click the name of the new publishing rule and then click **Properties**.</span></span>

2.  <span data-ttu-id="deeb7-147">Nella scheda a della finestra **di** dialogo **Proprietà** selezionare l'opzione **Inoltra l'intestazione host originale invece di quella effettiva**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-147">In the **Properties** dialog box, on the **To** tab, select the option **Forward the original host header instead of the actual one**.</span></span>

3.  <span data-ttu-id="deeb7-148">Nella scheda **traffico** fare clic su **filtro** e quindi su **configura http**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-148">On the **Traffic** tab, click **Filtering** and then click **Configure HTTP**.</span></span>

4.  <span data-ttu-id="deeb7-149">Nella finestra di dialogo **configurazione dei criteri HTTP per la regola** deselezionare la casella di controllo **Verifica normalizzazione** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-149">In the **Configuring HTTP policy for rule** dialog box, clear the **Verify normalization** check box and then click **OK**.</span></span>

5.  <span data-ttu-id="deeb7-150">Nella finestra di dialogo **Proprietà** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-150">In the **Properties** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="deeb7-151">In Forefront TMG fare clic su **applica** per abilitare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="deeb7-151">In Forefront TMG, click **Apply** to enable the changes.</span></span> <span data-ttu-id="deeb7-152">Quando viene visualizzata la finestra di dialogo **Descrizione modifica configurazione** , fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="deeb7-152">When the **Configuration Change Description** dialog box appears, click **Apply**.</span></span>

<span data-ttu-id="deeb7-153">Dopo aver completato l'installazione, è possibile testare il server di Office Web Apps usando le procedure descritte nell'argomento [convalida della configurazione di Office Web Apps Server in Lync server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span><span class="sxs-lookup"><span data-stu-id="deeb7-153">After completing the installation you can test your Office Web Apps Server using the procedures in the topic [Validating the configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

