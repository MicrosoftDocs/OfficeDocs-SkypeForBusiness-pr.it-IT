---
title: 'Lync Server 2013: Configurazione del proxy inverso per i dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the reverse proxy for mobility
ms:assetid: 3f4a9e33-77e4-4c18-a73f-24d4bec8ea9c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690011(v=OCS.15)
ms:contentKeyID: 48183946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51fffae60df68a6aa2843919f95d7a00590ddd65
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-reverse-proxy-for-mobility-in-lync-server-2013"></a><span data-ttu-id="eb4fe-102">Configurazione del proxy inverso per i dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb4fe-102">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb4fe-103">_**Argomento Ultima modifica:** 2014-03-20_</span><span class="sxs-lookup"><span data-stu-id="eb4fe-103">_**Topic Last Modified:** 2014-03-20_</span></span>

<span data-ttu-id="eb4fe-104">Se si vuole usare l'individuazione automatica per i client di dispositivi mobili, è necessario modificare una regola esistente o crearne una nuova per il proxy inverso, indipendentemente dal fatto che vengano aggiornati gli elenchi di nomi alternativi oggetto nei certificati di proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-104">If you want to use automatic discovery for mobile device clients, you need to modify an existing or create a new web publishing rule for the reverse proxy whether or not you update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="eb4fe-105">Se si decide di usare HTTPS per le richieste di servizio di individuazione automatica di Lync Server 2013 e aggiornare gli elenchi di nomi alternativi oggetto nei certificati proxy inverso, è necessario assegnare il certificato pubblico aggiornato al listener SSL (Secure Sockets Layer) il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-105">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="eb4fe-106">Per informazioni dettagliate sulle voci di nome alternativo oggetto richieste, vedere [requisiti tecnici per la mobilità in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="eb4fe-106">For details about the required subject alternative name entries, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="eb4fe-107">Devi quindi modificare il listener esistente per i servizi Web esterni o creare una nuova regola di pubblicazione Web per l'URL del servizio di individuazione automatica esterna.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-107">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="eb4fe-108">Se non si dispone già di una regola di pubblicazione Web per l'URL dei servizi Web di Lync Server 2013 esterno per il pool di front-end, è anche necessario pubblicare una regola.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-108">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool, you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eb4fe-109">La regola di pubblicazione del proxy inverso e il listener possono servire sia i servizi Web esterni che il servizio di individuazione automatica, purché il certificato assegnato al listener contenga il nome dell'oggetto e i nomi alternativi oggetto per entrambi.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-109">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="eb4fe-110">Per informazioni dettagliate sulla configurazione predefinita del listener Web e della regola di pubblicazione, vedere <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configurare i server proxy inversi per Lync Server 2013</A> per ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-110">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="eb4fe-111">Se si decide di usare HTTP per le richieste di servizio di individuazione automatica iniziali in modo che non sia necessario aggiornare i nomi alternativi dell'oggetto per il proxy inverso, è necessario creare o modificare una regola di pubblicazione Web per la porta 80.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-111">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="eb4fe-112">Le procedure descritte in questa sezione illustrano come creare o modificare le regole di pubblicazione Web in Microsoft Forefront Threat Management Gateway 2010 per l'individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-112">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eb4fe-113">Queste procedure presuppongono che sia stata installata la versione standard di Forefront Threat Management Gateway (TMG) 2010.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-113">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010.</span></span> <span data-ttu-id="eb4fe-114">Se si usa un altro proxy inverso, le procedure sono simili, ma sarà necessario eseguirne il mapping alla documentazione relativa al prodotto di terze parti.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-114">If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="eb4fe-115">Per creare una regola di pubblicazione Web per l'URL di individuazione automatica esterna</span><span class="sxs-lookup"><span data-stu-id="eb4fe-115">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="eb4fe-116">Fare clic sul pulsante **Start**, scegliere **programmi**, **Microsoft Forefront TMG**e quindi fare clic su **gestione di Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-116">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="eb4fe-117">Nel riquadro sinistro espandere **nomeserver**, fare clic con il pulsante destro del mouse su **criteri firewall**, scegliere **nuovo**e quindi fare clic su **regola pubblicazione sito Web**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-117">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="eb4fe-118">Nella pagina **Welcome to the New Web Publishing Rule** Digitare un nome visualizzato per la nuova regola di pubblicazione, ad esempio LyncDiscoveryURL.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-118">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="eb4fe-119">Nella pagina **selezionare l'azione di regola** selezionare **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-119">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="eb4fe-120">Nella pagina **tipo di pubblicazione** selezionare **pubblica un singolo sito Web o bilanciamento del carico**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-120">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="eb4fe-121">Nella pagina **sicurezza connessione server** selezionare **Usa SSL per connettersi al server Web pubblicato o alla server farm**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-121">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="eb4fe-122">Nella pagina Internal **Publishing Details** , in **nome sito interno**, digitare il nome di dominio completo (FQDN) del pool di Director, ad esempio lyncdir01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-122">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="eb4fe-123">Se si sta creando una regola per l'URL dei servizi Web esterni nel pool Front-End, digitare l'indirizzo VIP del servizio di bilanciamento del carico hardware (HLB) davanti al pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-123">If you are creating a rule for the external Web Services URL on the Front End pool, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="eb4fe-124">Nella pagina **Dettagli pubblicazione interna** , in **percorso (facoltativo)**, digitare \*\* / \*\* il percorso della cartella da pubblicare e quindi selezionare **Inoltra l'intestazione host originale**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-124">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="eb4fe-125">Nella pagina **Dettagli nome pubblico** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb4fe-125">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="eb4fe-126">In **accetta richieste per**selezionare **questo nome di dominio**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-126">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="eb4fe-127">In **nome pubblico**Digitare **lyncdiscover.** \<SipDomain\> (l'URL del servizio di individuazione automatica esterna).</span><span class="sxs-lookup"><span data-stu-id="eb4fe-127">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span> <span data-ttu-id="eb4fe-128">Se si sta creando una regola per l'URL dei servizi Web esterni nel pool Front-End, digitare il nome di dominio completo per i servizi Web esterni nel pool Front-End, ad esempio lyncwebextpool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-128">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="eb4fe-129">In **percorso**Digitare \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-129">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="eb4fe-130">Nella pagina **Seleziona listener Web** , in **listener Web**, selezionare il listener SSL esistente con il certificato pubblico aggiornato.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-130">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="eb4fe-131">Nella pagina **Delega autenticazione** selezionare **Nessuna delega, ma il client può eseguire l'autenticazione direttamente**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-131">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="eb4fe-132">Nella pagina **set** utenti selezionare **tutti gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-132">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="eb4fe-133">Nella pagina **completamento della nuova creazione guidata regola Web Publishing** verificare che le impostazioni della regola di pubblicazione Web siano corrette e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-133">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="eb4fe-134">Nell'elenco Forefront TMG delle regole di pubblicazione Web fare doppio clic sulla nuova regola appena aggiunta per aprire le **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-134">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="eb4fe-135">Nella scheda **a** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb4fe-135">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="eb4fe-136">Selezionare **Inoltra l'intestazione host originale invece di quella effettiva**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-136">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="eb4fe-137">**Le richieste di selezione sembrano provenire dal computer Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-137">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="eb4fe-138">Nella scheda **bridging** configurare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb4fe-138">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="eb4fe-139">Selezionare **server Web**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-139">Select **Web server**.</span></span>
    
      - <span data-ttu-id="eb4fe-140">Selezionare **reindirizza le richieste alla porta http**e digitare **8080** per il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-140">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="eb4fe-141">Selezionare **reindirizza le richieste alla porta SSL**e digitare **4443** per il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-141">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="eb4fe-142">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-142">Click **OK**.</span></span>

18. <span data-ttu-id="eb4fe-143">Fare clic su **applica** nel riquadro dei dettagli per salvare le modifiche e aggiornare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-143">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="eb4fe-144">Fare clic su **regola test** per verificare che la nuova regola sia configurata correttamente.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-144">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="eb4fe-145">Per modificare una regola di pubblicazione Web esistente per aggiungere la SAN e l'URL di individuazione automatica esterna</span><span class="sxs-lookup"><span data-stu-id="eb4fe-145">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="eb4fe-146">Fare clic sul pulsante **Start**, scegliere **programmi**, **Microsoft Forefront TMG**e quindi fare clic su **gestione di Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-146">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="eb4fe-147">Si ripeterà la modifica per ogni regola di pubblicazione e listener che si ha.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-147">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="eb4fe-148">In genere, si tratta di una regola e di un listener per i pool Front-end e uno per i pool di direttori o di Director facoltativi, se sono stati distribuiti.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-148">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="eb4fe-149">Nel riquadro sinistro espandere **nomeserver**, fare clic con il pulsante destro del mouse su **criteri firewall**e scegliere la regola applicabile.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-149">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule.</span></span> <span data-ttu-id="eb4fe-150">Nella scheda **attività** fare clic su **Modifica regola selezionata**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-150">On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="eb4fe-151">Nella scheda **nome pubblico** , in **questa regola si applica a**, selezionare **richieste per i siti Web seguenti**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-151">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="eb4fe-152">Fare clic su **Aggiungi**, digitare il nome del nuovo sito di individuazione automatica, ad esempio "lyncdiscover.contoso.com", e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-152">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="eb4fe-153">Nella scheda **listener** fare clic su **Seleziona certificato** e assegnare il nuovo certificato alle voci San di individuazione automatica aggiunte.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-153">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries.</span></span> <span data-ttu-id="eb4fe-154">Chiudere le proprietà listener e Publishing Web.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-154">Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="eb4fe-155">Fare clic su **applica** nel riquadro dei dettagli per salvare le modifiche e aggiornare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-155">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="eb4fe-156">Fare clic su **regola test** per verificare che la nuova regola sia configurata correttamente.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-156">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="eb4fe-157">Per creare una regola di pubblicazione Web per la porta 80</span><span class="sxs-lookup"><span data-stu-id="eb4fe-157">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="eb4fe-158">Fare clic sul pulsante **Start**, scegliere **programmi**, **Microsoft Forefront TMG**e quindi fare clic su **gestione di Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-158">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="eb4fe-159">Nel riquadro sinistro espandere **nomeserver**, fare clic con il pulsante destro del mouse su **criteri firewall**, scegliere **nuovo**e quindi fare clic su **regola pubblicazione sito Web**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-159">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="eb4fe-160">Nella pagina **Welcome to the New Web Publishing Rule** Digitare un nome visualizzato per la nuova regola di pubblicazione, ad esempio Lync Autodiscover (http).</span><span class="sxs-lookup"><span data-stu-id="eb4fe-160">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="eb4fe-161">Nella pagina **selezionare l'azione di regola** selezionare **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-161">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="eb4fe-162">Nella pagina **tipo di pubblicazione** selezionare **pubblica un singolo sito Web o bilanciamento del carico**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-162">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="eb4fe-163">Nella pagina **sicurezza connessione server** selezionare **Usa connessioni non protette per connettersi al server Web pubblicato o alla server farm**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-163">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="eb4fe-164">Nella pagina Internal **Publishing Details** , in **nome sito interno**, digitare l'indirizzo VIP del bilanciamento del carico hardware (HLB) davanti al pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-164">On the **Internal Publishing Details** page, in **Internal Site name**, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="eb4fe-165">Nella pagina **Dettagli pubblicazione interna** , in **percorso (facoltativo)**, digitare \*\* / \*\* il percorso della cartella da pubblicare e quindi selezionare **Inoltra l'intestazione host originale invece di quella specificata nel campo nome sito interno**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-165">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="eb4fe-166">Nella pagina **Dettagli nome pubblico** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb4fe-166">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="eb4fe-167">In **accetta richieste per**selezionare **questo nome di dominio**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-167">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="eb4fe-168">In **nome pubblico**Digitare **lyncdiscover.** \<SipDomain\> (l'URL del servizio di individuazione automatica esterna).</span><span class="sxs-lookup"><span data-stu-id="eb4fe-168">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="eb4fe-169">In **percorso**Digitare \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-169">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="eb4fe-170">Nella pagina **Seleziona listener** Web, in **listener Web**, selezionare un listener Web o usare la creazione guidata nuova definizione listener Web per crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-170">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="eb4fe-171">Nella pagina **Delega autenticazione** selezionare **Nessuna delega e il client non può eseguire l'autenticazione direttamente**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-171">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="eb4fe-172">Nella pagina **set** utenti selezionare **tutti gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-172">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="eb4fe-173">Nella pagina **completamento della nuova creazione guidata regola Web Publishing** verificare che le impostazioni della regola di pubblicazione Web siano corrette e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-173">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="eb4fe-174">Nell'elenco Forefront TMG delle regole di pubblicazione Web fare doppio clic sulla nuova regola appena aggiunta per aprire le **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-174">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="eb4fe-175">Nella scheda **bridging** configurare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb4fe-175">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="eb4fe-176">Selezionare **server Web**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-176">Select **Web server**.</span></span>
    
      - <span data-ttu-id="eb4fe-177">Selezionare **reindirizza le richieste alla porta http**e digitare **8080** per il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-177">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="eb4fe-178">Verificare che l'opzione **Reindirizza richieste alla porta SSL** non sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-178">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="eb4fe-179">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-179">Click **OK**.</span></span>

17. <span data-ttu-id="eb4fe-180">Fare clic su **applica** nel riquadro dei dettagli per salvare le modifiche e aggiornare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-180">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="eb4fe-181">Fare clic su **regola test** per verificare che la nuova regola sia configurata correttamente.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-181">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="eb4fe-182">Verificare che l'URL del servizio di individuazione automatica esterna non sia definito in nessuna regola di pubblicazione Web.</span><span class="sxs-lookup"><span data-stu-id="eb4fe-182">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eb4fe-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb4fe-183">See Also</span></span>


[<span data-ttu-id="eb4fe-184">Configurare server proxy inversi per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb4fe-184">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
[<span data-ttu-id="eb4fe-185">Requisiti tecnici per i dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb4fe-185">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

