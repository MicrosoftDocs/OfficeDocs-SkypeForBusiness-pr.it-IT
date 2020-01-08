---
title: "Lync Server 2013: configurazione di un proxy inverso per l'individuazione automatica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5445a9ce81835863b610ef32ecc51ccac5331c3f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="05490-102">Configurazione di un proxy inverso per l'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05490-102">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05490-103">_**Argomento Ultima modifica:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="05490-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="05490-104">L'individuazione automatica e il supporto dei client che usano l'individuazione automatica richiedono la modifica di una regola di pubblicazione Web esistente o la creazione di una nuova regola di pubblicazione Web per il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="05490-104">Autodiscover and the support of clients using autodiscover requires modification of an existing web publishing rule or creating a new web publishing rule for the reverse proxy.</span></span> <span data-ttu-id="05490-105">La modifica o la creazione di una nuova regola di pubblicazione non dipende dalla decisione di aggiornare o non aggiornare gli elenchi di nomi alternativi oggetto nei certificati proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="05490-105">The modification or creation of a new publishing rule is not dependent on the decision to update or not update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="05490-106">Se si decide di usare HTTPS per le richieste di servizio di individuazione automatica di Lync Server 2013 e aggiornare gli elenchi di nomi alternativi oggetto nei certificati proxy inverso, è necessario assegnare il certificato pubblico aggiornato al listener SSL (Secure Sockets Layer) il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="05490-106">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="05490-107">L'aggiornamento necessario al certificato esterno (pubblico) includerà la voce di nome alternativo oggetto (SAN) per lyncdiscover. \<nome\>di dominio.</span><span class="sxs-lookup"><span data-stu-id="05490-107">The required update to the external (public) certificate will include the subject alternate name (SAN) entry for lyncdiscover.\<domain name\>.</span></span> <span data-ttu-id="05490-108">Devi quindi modificare il listener esistente per i servizi Web esterni o creare una nuova regola di pubblicazione Web per l'URL del servizio di individuazione automatica esterna, ad esempio **lyncdiscover.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="05490-108">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL, for example **lyncdiscover.contoso.com**.</span></span> <span data-ttu-id="05490-109">Se non si dispone già di una regola di pubblicazione Web per l'URL dei servizi Web di Lync Server 2013 esterno per il pool di front-end e per quello del direttore (se sono stati distribuiti i direttori), è anche necessario pubblicare una regola.</span><span class="sxs-lookup"><span data-stu-id="05490-109">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool and Director pool (if you have deployed Directors), you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="05490-110">La regola di pubblicazione del proxy inverso e il listener possono servire sia i servizi Web esterni che il servizio di individuazione automatica, purché il certificato assegnato al listener contenga il nome dell'oggetto e i nomi alternativi oggetto per entrambi.</span><span class="sxs-lookup"><span data-stu-id="05490-110">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="05490-111">Per informazioni dettagliate sulla configurazione predefinita del listener Web e della regola di pubblicazione, vedere <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configurare i server proxy inversi per Lync Server 2013</A> per ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="05490-111">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="05490-112">Se si decide di usare HTTP per le richieste di servizio di individuazione automatica iniziali in modo che non sia necessario aggiornare i nomi alternativi dell'oggetto per il proxy inverso, è necessario creare o modificare una regola di pubblicazione Web per la porta 80.</span><span class="sxs-lookup"><span data-stu-id="05490-112">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="05490-113">Le procedure descritte in questa sezione illustrano come creare o modificare le regole di pubblicazione Web in Microsoft Forefront Threat Management Gateway 2010 per l'individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="05490-113">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="05490-114">Queste procedure presuppongono che sia stata installata la versione standard di Forefront Threat Management Gateway (TMG) 2010.</span><span class="sxs-lookup"><span data-stu-id="05490-114">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010.</span></span> <span data-ttu-id="05490-115">Se si usa un altro proxy inverso, le procedure sono simili, ma sarà necessario eseguirne il mapping alla documentazione relativa al prodotto di terze parti.</span><span class="sxs-lookup"><span data-stu-id="05490-115">If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="05490-116">Per creare una regola di pubblicazione Web per l'URL di individuazione automatica esterna</span><span class="sxs-lookup"><span data-stu-id="05490-116">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="05490-117">Fare clic sul pulsante **Start**, scegliere **programmi**, **Microsoft Forefront TMG**e quindi fare clic su **gestione di Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="05490-117">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="05490-118">Nel riquadro sinistro espandere **nomeserver**, fare clic con il pulsante destro del mouse su **criteri firewall**, scegliere **nuovo**e quindi fare clic su **regola pubblicazione sito Web**.</span><span class="sxs-lookup"><span data-stu-id="05490-118">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="05490-119">Nella pagina **Welcome to the New Web Publishing Rule** Digitare un nome visualizzato per la nuova regola di pubblicazione, ad esempio LyncDiscoveryURL.</span><span class="sxs-lookup"><span data-stu-id="05490-119">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="05490-120">Nella pagina **selezionare l'azione di regola** selezionare **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="05490-120">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="05490-121">Nella pagina **tipo di pubblicazione** selezionare **pubblica un singolo sito Web o bilanciamento del carico**.</span><span class="sxs-lookup"><span data-stu-id="05490-121">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="05490-122">Nella pagina **sicurezza connessione server** selezionare **Usa SSL per connettersi al server Web pubblicato o alla server farm**.</span><span class="sxs-lookup"><span data-stu-id="05490-122">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="05490-123">Nella pagina Internal **Publishing Details** , in **nome sito interno**, digitare il nome di dominio completo (FQDN) del pool di Director, ad esempio lyncdir01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="05490-123">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="05490-124">Se si sta creando una regola per l'URL dei servizi Web esterni nel pool Front End, digitare il nome di dominio completo del pool Front-End, ad esempio lyncpool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="05490-124">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN of the Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="05490-125">Nella pagina **Dettagli pubblicazione interna** , in **percorso (facoltativo)**, digitare \*\* / \*\* il percorso della cartella da pubblicare e quindi selezionare **Inoltra l'intestazione host originale**.</span><span class="sxs-lookup"><span data-stu-id="05490-125">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="05490-126">Nella pagina **Dettagli nome pubblico** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="05490-126">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="05490-127">In **accetta richieste per**selezionare **questo nome di dominio**.</span><span class="sxs-lookup"><span data-stu-id="05490-127">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="05490-128">In **nome pubblico**Digitare **lyncdiscover.** \<SipDomain\> (l'URL del servizio di individuazione automatica esterna).</span><span class="sxs-lookup"><span data-stu-id="05490-128">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span> <span data-ttu-id="05490-129">Se si sta creando una regola per l'URL dei servizi Web esterni nel pool Front-End, digitare il nome di dominio completo per i servizi Web esterni nel pool Front-End, ad esempio lyncwebextpool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="05490-129">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="05490-130">In **percorso**Digitare \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="05490-130">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="05490-131">Nella pagina **Seleziona listener Web** , in **listener Web**, selezionare il listener SSL esistente con il certificato pubblico aggiornato.</span><span class="sxs-lookup"><span data-stu-id="05490-131">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="05490-132">Nella pagina **Delega autenticazione** selezionare **Nessuna delega, ma il client può eseguire l'autenticazione direttamente**.</span><span class="sxs-lookup"><span data-stu-id="05490-132">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="05490-133">Nella pagina **set** utenti selezionare **tutti gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="05490-133">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="05490-134">Nella pagina **completamento della nuova creazione guidata regola Web Publishing** verificare che le impostazioni della regola di pubblicazione Web siano corrette e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="05490-134">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="05490-135">Nell'elenco Forefront TMG delle regole di pubblicazione Web fare doppio clic sulla nuova regola appena aggiunta per aprire le **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="05490-135">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="05490-136">Nella scheda **a** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="05490-136">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="05490-137">Selezionare **Inoltra l'intestazione host originale invece di quella effettiva**.</span><span class="sxs-lookup"><span data-stu-id="05490-137">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="05490-138">**Le richieste di selezione sembrano provenire dal computer Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="05490-138">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="05490-139">Nella scheda **bridging** configurare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="05490-139">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="05490-140">Selezionare **server Web**.</span><span class="sxs-lookup"><span data-stu-id="05490-140">Select **Web server**.</span></span>
    
      - <span data-ttu-id="05490-141">Selezionare **reindirizza le richieste alla porta http**e digitare **8080** per il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="05490-141">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="05490-142">Selezionare **reindirizza le richieste alla porta SSL**e digitare **4443** per il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="05490-142">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="05490-143">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="05490-143">Click **OK**.</span></span>

18. <span data-ttu-id="05490-144">Fare clic su **applica** nel riquadro dei dettagli per salvare le modifiche e aggiornare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="05490-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="05490-145">Fare clic su **regola test** per verificare che la nuova regola sia configurata correttamente.</span><span class="sxs-lookup"><span data-stu-id="05490-145">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="05490-146">Per modificare una regola di pubblicazione Web esistente per aggiungere la SAN e l'URL di individuazione automatica esterna</span><span class="sxs-lookup"><span data-stu-id="05490-146">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="05490-147">Fare clic sul pulsante **Start**, scegliere **programmi**, **Microsoft Forefront TMG**e quindi fare clic su **gestione di Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="05490-147">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="05490-148">Si ripeterà la modifica per ogni regola di pubblicazione e listener che si ha.</span><span class="sxs-lookup"><span data-stu-id="05490-148">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="05490-149">In genere, si tratta di una regola e di un listener per i pool Front-end e uno per i pool di direttori o di Director facoltativi, se sono stati distribuiti.</span><span class="sxs-lookup"><span data-stu-id="05490-149">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="05490-150">Nel riquadro sinistro espandere **nomeserver**, fare clic con il pulsante destro del mouse su **criteri firewall**e scegliere la regola applicabile.</span><span class="sxs-lookup"><span data-stu-id="05490-150">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule.</span></span> <span data-ttu-id="05490-151">Nella scheda **attività** fare clic su **Modifica regola selezionata**.</span><span class="sxs-lookup"><span data-stu-id="05490-151">On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="05490-152">Nella scheda **nome pubblico** , in **questa regola si applica a**, selezionare **richieste per i siti Web seguenti**.</span><span class="sxs-lookup"><span data-stu-id="05490-152">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="05490-153">Fare clic su **Aggiungi**, digitare il nome del nuovo sito di individuazione automatica, ad esempio "lyncdiscover.contoso.com", e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="05490-153">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="05490-154">Nella scheda **listener** fare clic su **Seleziona certificato** e assegnare il nuovo certificato alle voci San di individuazione automatica aggiunte.</span><span class="sxs-lookup"><span data-stu-id="05490-154">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries.</span></span> <span data-ttu-id="05490-155">Chiudere le proprietà listener e Publishing Web.</span><span class="sxs-lookup"><span data-stu-id="05490-155">Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="05490-156">Fare clic su **applica** nel riquadro dei dettagli per salvare le modifiche e aggiornare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="05490-156">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="05490-157">Fare clic su **regola test** per verificare che la nuova regola sia configurata correttamente.</span><span class="sxs-lookup"><span data-stu-id="05490-157">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="05490-158">Per creare una regola di pubblicazione Web per la porta 80</span><span class="sxs-lookup"><span data-stu-id="05490-158">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="05490-159">Fare clic sul pulsante **Start**, scegliere **programmi**, **Microsoft Forefront TMG**e quindi fare clic su **gestione di Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="05490-159">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="05490-160">Nel riquadro sinistro espandere **nomeserver**, fare clic con il pulsante destro del mouse su **criteri firewall**, scegliere **nuovo**e quindi fare clic su **regola pubblicazione sito Web**.</span><span class="sxs-lookup"><span data-stu-id="05490-160">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="05490-161">Nella pagina **Welcome to the New Web Publishing Rule** Digitare un nome visualizzato per la nuova regola di pubblicazione, ad esempio Lync Autodiscover (http).</span><span class="sxs-lookup"><span data-stu-id="05490-161">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="05490-162">Nella pagina **selezionare l'azione di regola** selezionare **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="05490-162">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="05490-163">Nella pagina **tipo di pubblicazione** selezionare **pubblica un singolo sito Web o bilanciamento del carico**.</span><span class="sxs-lookup"><span data-stu-id="05490-163">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="05490-164">Nella pagina **sicurezza connessione server** selezionare **Usa connessioni non protette per connettersi al server Web pubblicato o alla server farm**.</span><span class="sxs-lookup"><span data-stu-id="05490-164">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="05490-165">Nella pagina Internal **Publishing Details** , in **nome sito interno**, digitare l'FQDN dei servizi Web interni per il pool Front-End, ad esempio lyncpool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="05490-165">On the **Internal Publishing Details** page, in **Internal Site name**, type the internal Web Services FQDN for your Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="05490-166">Nella pagina **Dettagli pubblicazione interna** , in **percorso (facoltativo)**, digitare \*\* / \*\* il percorso della cartella da pubblicare e quindi selezionare **Inoltra l'intestazione host originale invece di quella specificata nel campo nome sito interno**.</span><span class="sxs-lookup"><span data-stu-id="05490-166">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="05490-167">Nella pagina **Dettagli nome pubblico** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="05490-167">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="05490-168">In **accetta richieste per**selezionare **questo nome di dominio**.</span><span class="sxs-lookup"><span data-stu-id="05490-168">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="05490-169">In **nome pubblico**Digitare **lyncdiscover.** \<SipDomain\> (l'URL del servizio di individuazione automatica esterna).</span><span class="sxs-lookup"><span data-stu-id="05490-169">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="05490-170">In **percorso**Digitare \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="05490-170">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="05490-171">Nella pagina **Seleziona listener** Web, in **listener Web**, selezionare un listener Web o usare la creazione guidata nuova definizione listener Web per crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="05490-171">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="05490-172">Nella pagina **Delega autenticazione** selezionare **Nessuna delega e il client non può eseguire l'autenticazione direttamente**.</span><span class="sxs-lookup"><span data-stu-id="05490-172">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="05490-173">Nella pagina **set** utenti selezionare **tutti gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="05490-173">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="05490-174">Nella pagina **completamento della nuova creazione guidata regola Web Publishing** verificare che le impostazioni della regola di pubblicazione Web siano corrette e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="05490-174">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="05490-175">Nell'elenco Forefront TMG delle regole di pubblicazione Web fare doppio clic sulla nuova regola appena aggiunta per aprire le **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="05490-175">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="05490-176">Nella scheda **bridging** configurare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="05490-176">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="05490-177">Selezionare **server Web**.</span><span class="sxs-lookup"><span data-stu-id="05490-177">Select **Web server**.</span></span>
    
      - <span data-ttu-id="05490-178">Selezionare **reindirizza le richieste alla porta http**e digitare **8080** per il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="05490-178">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="05490-179">Verificare che l'opzione **Reindirizza richieste alla porta SSL** non sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="05490-179">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="05490-180">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="05490-180">Click **OK**.</span></span>

17. <span data-ttu-id="05490-181">Fare clic su **applica** nel riquadro dei dettagli per salvare le modifiche e aggiornare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="05490-181">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="05490-182">Fare clic su **regola test** per verificare che la nuova regola sia configurata correttamente.</span><span class="sxs-lookup"><span data-stu-id="05490-182">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="05490-183">Verificare che l'URL del servizio di individuazione automatica esterna non sia definito in nessuna regola di pubblicazione Web.</span><span class="sxs-lookup"><span data-stu-id="05490-183">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="05490-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05490-184">See Also</span></span>


[<span data-ttu-id="05490-185">Configurare server proxy inversi per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05490-185">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

