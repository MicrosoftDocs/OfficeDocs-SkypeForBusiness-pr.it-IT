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
ms.openlocfilehash: c1d1dae773c96cfa6d16994e5b3c6aec2504b16c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a><span data-ttu-id="d44d2-102">Pubblicazione del server Office Web Apps in Lync Server 2013 utilizzando un server proxy inverso</span><span class="sxs-lookup"><span data-stu-id="d44d2-102">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d44d2-103">_**Ultimo argomento modificato:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="d44d2-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="d44d2-104">Se si desidera che gli utenti esterni, ovvero gli utenti che eseguono l'accesso dall'esterno del firewall dell'organizzazione, possano accedere alle presentazioni di PowerPoint di Office Web Apps Server, sarà necessario usare Office Web Apps Server e un server proxy inverso come Microsoft Forefront Threat Management Gateway.</span><span class="sxs-lookup"><span data-stu-id="d44d2-104">If you want external users (that is, users logging on from outside your organization’s firewall) to have access to Office Web Apps Server PowerPoint presentations then you will need to use Office Web Apps Server and a reverse proxy server such as Microsoft Forefront Threat Management Gateway.</span></span> <span data-ttu-id="d44d2-105">Questo significa anche che sarà necessario creare e configurare una regola di pubblicazione del sito Web. tale regola consentirà di garantire che gli utenti siano in grado di connettersi al server.</span><span class="sxs-lookup"><span data-stu-id="d44d2-105">That also means that you will need to create and configure a website publishing rule; that rule will help ensure that users are able to connect to the server.</span></span> <span data-ttu-id="d44d2-106">Se non è necessario fornire accesso agli utenti esterni, non è necessario configurare una regola di pubblicazione del sito Web.</span><span class="sxs-lookup"><span data-stu-id="d44d2-106">If you do not need to provide access to external users then you do not need to configure a website publishing rule.</span></span>

<span data-ttu-id="d44d2-107">Per configurare una regola di pubblicazione del sito Web in Forefront Threat Management Gateway, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="d44d2-107">To configure a website publishing rule in Forefront Threat Management Gateway complete the following procedure:</span></span>

1.  <span data-ttu-id="d44d2-108">Fare clic su **Start**, scegliere **Tutti i programmi**, **Microsoft Forefront TMG** e quindi **Gestione Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-108">Click **Start**, click **All Programs**, click **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="d44d2-109">In Forefront TMG fare clic con il pulsante destro del mouse su **Criterio firewall**, scegliere **Nuovo** e fare clic su **Regola di pubblicazione sito Web**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-109">In Forefront TMG, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="d44d2-110">Nella pagina iniziale della **Creazione guidata regola di pubblicazione sul Web** digitare un nome per la nuova regola nella casella **Nome regola di pubblicazione sul Web**, ad esempio **Regola Office Web Apps Server**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-110">In the New Web Publishing Rule Wizard, on the **Welcome to the New Web Publishing Rule Wizard** page, type a name for your new rule in the **Web publishing rule name** box (for example, **Office Web Apps Server Rule**) and then click **Next**.</span></span>

4.  <span data-ttu-id="d44d2-111">Nella pagina **Seleziona azione regola** selezionare **Consenti** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-111">On the **Specify Rule Action** page, select **Allow** and then click **Next**.</span></span>

5.  <span data-ttu-id="d44d2-112">Nella pagina **Tipo di pubblicazione** selezionare **Pubblica un singolo sito Web o un sistema di bilanciamento del carico**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-112">On the **Publishing Type** page, select **Publish a single Web site or load balancer** and then click **Next**.</span></span>

6.  <span data-ttu-id="d44d2-113">Nella pagina **Protezione connessione server** selezionare **Utilizzare SSL per connettersi al server Web pubblicato o alla server farm**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-113">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm** and then click **Next**.</span></span>

7.  <span data-ttu-id="d44d2-p102">Nella pagina **Dettagli pubblicazione interna** digitare il nome di dominio completo del server Office Web Apps, ad esempio **officewebapps01.contoso.com**, nella casella **Nome sito interno**, quindi fare clic su **Avanti**. Il nome immesso nella casella **Nome sito interno** deve comparire nel campo Soggetto e nel campo Nome alternativo soggetto del certificato assegnato a Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="d44d2-p102">On the **Internal Publishing Details** page, type the FQDN of your Office Web Apps server (for example, **officewebapps01.contoso.com**) in the **Internal site name** box and then click **Next**. The name entered in the **Internal site name** box must appear in the Subject field or the Subject Alternative Name field of the certificate you have assigned to Office Web Apps Server.</span></span>

8.  <span data-ttu-id="d44d2-116">Nella pagina **Dettagli pubblicazione interna** Digitare \*\* / \*\* la casella **percorso (facoltativo)** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-116">On the **Internal Publishing Details** page, type **/\*** in the **Path (optional)** box and then click **Next**.</span></span> <span data-ttu-id="d44d2-117">La sintassi\* //consentirà di verificare che vengano pubblicate tutte le cartelle e le sottocartelle del sito.</span><span class="sxs-lookup"><span data-stu-id="d44d2-117">The /\* syntax will help ensure that all the folders and subfolders for the site are published.</span></span>

9.  <span data-ttu-id="d44d2-118">Nella pagina **Dettagli nome pubblico** selezionare **Questo nome dominio (immettere di seguito)** nell'elenco a discesa **Accetta richieste per**, quindi digitare il nome completo di Office Web Apps Server nella casella Nome pubblico.</span><span class="sxs-lookup"><span data-stu-id="d44d2-118">On the **Public Name Details** page, select **This domain name (type below)** from the **Accept requests for** drop-down list and then type the fully qualified for your Office Web Apps Server in the Public name box.</span></span> <span data-ttu-id="d44d2-119">Questo nome deve corrispondere a quello utilizzato per accedere al sito Web.</span><span class="sxs-lookup"><span data-stu-id="d44d2-119">This name should be the name used to access your website.</span></span> <span data-ttu-id="d44d2-120">Ad esempio, se si accede al sito utilizzando l'URL http://officewebapps01.contoso.com , è necessario immettere **officewebapps01.contoso.com** nella casella **nome pubblico** .</span><span class="sxs-lookup"><span data-stu-id="d44d2-120">For example, if your site is accessed using the URL http://officewebapps01.contoso.com then you should enter **officewebapps01.contoso.com** in the **Public name** box.</span></span>

10. <span data-ttu-id="d44d2-121">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-121">Click **Next**.</span></span>

11. <span data-ttu-id="d44d2-122">Nella pagina **Scegliere Listener Web** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-122">On the **Select Web Listener** page, click **New**.</span></span>

12. <span data-ttu-id="d44d2-123">Nella Creazione guidata definizione listener Web digitare un nome per il listener Web, ad esempio **SSL**, nella casella **Nome listener Web** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-123">In the New Web Listener Definition Wizard, type a name for the new Web listener (for example, **SSL**) in the **Web listener name** box and then click **Next**.</span></span>

13. <span data-ttu-id="d44d2-124">Nella pagina **Protezione di connessione client** selezionare **Richiedi connessioni SSL protette con i client**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-124">On the **Client Connection Security** page, select **Require SSL secured connections with clients** and then click **Next**.</span></span>

14. <span data-ttu-id="d44d2-125">Nella pagina **Indirizzi IP del listener Web** selezionare **Esterno**, selezionare **Interno**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-125">On the **Web Listener IP Addresses** page, select **External**, select **Internal**, and then click **Next**.</span></span>

15. <span data-ttu-id="d44d2-126">Nella pagina \*\*Certificati SSL listener \*\* selezionare **Usa un unico certificato per questo listener Web**, quindi fare clic su **Seleziona certificato**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-126">On the **Listener SSL Certificates** page, select **Use a single certificate for this Web Listener** and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="d44d2-127">Nella finestra di dialogo **Seleziona certificato** selezionare il certificato da usare per il listener Web e fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-127">In the **Select Certificate** dialog box, select the certificate to be used for this Web Listener and then click **Select**.</span></span>

17. <span data-ttu-id="d44d2-128">Nella pagina **Certificati SSL listener** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-128">On the **Listener SSL Certificates** page, click **Next**.</span></span>

18. <span data-ttu-id="d44d2-129">Nella pagina \*\*Impostazione di autenticazione \*\* selezionare **Nessuna autenticazione** nell'elenco a discesa **Selezionare la modalità in cui i client forniscono le credenziali a Forefront TMG**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-129">On the **Authentication Settings** page, select **No Authentication** from the **Select how clients will provide credentials to Forefront TMG** drop-down list, and then click **Next**.</span></span>

19. <span data-ttu-id="d44d2-130">Nella pagina **Impostazioni Single Sign-On** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-130">On the **Single Sign On Settings** page, click **Next**.</span></span>

20. <span data-ttu-id="d44d2-p105">Nella pagina **Completamento della Creazione guidata listener Web** rivedere il riepilogo delle scelte di configurazione effettuate. Al termine, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-p105">On the **Completing the New Web Listener Wizard** page, review the summary of the configuration choices you have made. When ready, click **Finish**.</span></span>

21. <span data-ttu-id="d44d2-133">Nella pagina **Scegliere Listener Web** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-133">On the **Select Web Listener** page, click **Next**.</span></span>

22. <span data-ttu-id="d44d2-134">Nella pagina **Delega autenticazione** selezionare **Nessuna delega, ma il client può eseguire l'autenticazione direttamente** nell'elenco a discesa **Scegliere il metodo utilizzato da Forefront TMG per autenticare il server Web pubblicato**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-134">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly** from the **Select the method used by Forefront TMG to authenticate to the published Web server** drop-down list and then click **Next**.</span></span>

23. <span data-ttu-id="d44d2-p106">Nella pagina **Gruppi di utenti** verificare che siano elencati i gruppi di utenti appropriati. Per impostazione predefinita si tratta del gruppo **Tutti gli utenti**. Per aggiungere altri set di utenti definiti, fare clic su **Aggiungi**. Al termine, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-p106">On the **User Sets** page, confirm that the appropriate user sets are listed. By default, this is the **All Users** user set. Click **Add** to add other user sets you may have defined. When complete, click **Next**.</span></span>

24. <span data-ttu-id="d44d2-139">Nella pagina finale della **Creazione guidata regola di pubblicazione sul Web** fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-139">On the **Completing the New Web Publishing Rule Wizard** page, click **Finish**.</span></span>

<span data-ttu-id="d44d2-p107">Fare clic su **Fine** non significa che il processo è terminato, ovvero la nuova regola non viene applicata e abilitata automaticamente. A questo scopo sarà necessario fare clic sul pulsante **Applica** nell'interfaccia utente di Forefront TMG. Quando si fa clic su **Applica** viene visualizzata la finestra di dialogo con la\*\*\*\* descrizione della modifica apportata alla configurazione. Per applicare la nuova regola di pubblicazione, fare clic su **Applica** in tale finestra.</span><span class="sxs-lookup"><span data-stu-id="d44d2-p107">Note that clicking **Finish** does not mean that you completed the process; that is, this does not automatically apply and enable the new rule. Instead, you will need to click the **Apply** button that will appear in the Forefront TMG user interface. When you click **Apply** the **Configuration Change Description** dialog box will appear. Click **Apply** in that dialog box to enable the new publishing rule.</span></span>

<span data-ttu-id="d44d2-144">Dopo l'applicazione della nuova regola, è necessario apportare alcune modifiche minime alla regola per assicurarsi che gli utenti possano utilizzare le nuove funzionalità di presentazione di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="d44d2-144">After your new rule has been applied, you will then need to make some minor modifications to the rule to make sure that users can use the new PowerPoint presentation capabilities.</span></span> <span data-ttu-id="d44d2-145">Eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="d44d2-145">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="d44d2-146">In Forefront TMG fare clic con il pulsante destro del mouse sulla nuova regola di pubblicazione e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-146">In Forefront TMG, right-click the name of the new publishing rule and then click **Properties**.</span></span>

2.  <span data-ttu-id="d44d2-147">Nella scheda**A** della finestra di dialogo **Proprietà** selezionare l'opzione **Inoltra l'intestazione host originale e non quella effettiva (nel campo Nome sito interno)**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-147">In the **Properties** dialog box, on the **To** tab, select the option **Forward the original host header instead of the actual one**.</span></span>

3.  <span data-ttu-id="d44d2-148">Nella scheda **Traffico** fare clic su **Filtri** e quindi fare clic su **Configura HTTP**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-148">On the **Traffic** tab, click **Filtering** and then click **Configure HTTP**.</span></span>

4.  <span data-ttu-id="d44d2-149">Nella finestra di dialogo **Configura criteri HTTP per la regola** deselezionare la casella di controllo **Verifica normalizzazione** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-149">In the **Configuring HTTP policy for rule** dialog box, clear the **Verify normalization** check box and then click **OK**.</span></span>

5.  <span data-ttu-id="d44d2-150">Nella finestra di dialogo **Proprietà** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-150">In the **Properties** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="d44d2-p109">In Forefront TMG fare clic su **Applica** per abilitare le modifiche. Quando viene visualizzata la finestra di dialogo contenente la descrizione della\*\*\*\* modifica apportata alla configurazione, fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="d44d2-p109">In Forefront TMG, click **Apply** to enable the changes. When the **Configuration Change Description** dialog box appears, click **Apply**.</span></span>

<span data-ttu-id="d44d2-153">Dopo aver completato l'installazione, è possibile testare il server Office Web Apps utilizzando le procedure descritte nell'argomento [convalidare la configurazione del server Office Web Apps in Lync server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span><span class="sxs-lookup"><span data-stu-id="d44d2-153">After completing the installation you can test your Office Web Apps Server using the procedures in the topic [Validating the configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

