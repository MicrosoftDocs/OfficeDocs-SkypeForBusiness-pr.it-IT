---
title: "Lync Server 2013: configurazione di un proxy inverso per l'individuazione automatica"
description: "Lync Server 2013: configurazione di un proxy inverso per l'individuazione automatica."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f7873df063c526b4e51678ded02ca11d27c5e01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553952"
---
# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="b2259-103">Configurazione di un proxy inverso per l'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2259-103">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2259-104">_**Ultimo argomento modificato:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="b2259-104">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="b2259-105">Il servizio di individuazione automatica e il supporto dei client che utilizzano l'individuazione automatica richiedono la modifica di una regola di pubblicazione Web esistente o la creazione di una nuova regola di pubblicazione Web per il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="b2259-105">Autodiscover and the support of clients using autodiscover requires modification of an existing web publishing rule or creating a new web publishing rule for the reverse proxy.</span></span> <span data-ttu-id="b2259-106">La modifica o la creazione di una nuova regola di pubblicazione non dipende dalla decisione di aggiornare o non aggiornare gli elenchi del nome alternativo del soggetto nei certificati del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="b2259-106">The modification or creation of a new publishing rule is not dependent on the decision to update or not update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="b2259-107">Se si decide di utilizzare HTTPS per le richieste iniziali del servizio di individuazione automatica di Lync Server 2013 e si aggiornano gli elenchi dei nomi alternativi del soggetto nei certificati del proxy inverso, è necessario assegnare il certificato pubblico aggiornato al listener SSL (Secure Sockets Layer) sul proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="b2259-107">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="b2259-108">L'aggiornamento necessario per il certificato esterno (pubblico) includerà la voce del nome alternativo soggetto (SAN) per Lyncdiscover \<domain name\> .</span><span class="sxs-lookup"><span data-stu-id="b2259-108">The required update to the external (public) certificate will include the subject alternate name (SAN) entry for lyncdiscover.\<domain name\>.</span></span> <span data-ttu-id="b2259-109">È quindi necessario modificare il listener esistente per i servizi Web esterni o creare una nuova regola di pubblicazione Web per l'URL del servizio di individuazione automatica esterno, ad esempio **lyncdiscover.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="b2259-109">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL, for example **lyncdiscover.contoso.com**.</span></span> <span data-ttu-id="b2259-110">Se non si dispone già di una regola di pubblicazione Web per l'URL dei servizi Web di Lync Server 2013 esterno per il pool Front end e il pool di Director (se sono stati distribuiti i direttori), è necessario pubblicare una regola per tale operazione.</span><span class="sxs-lookup"><span data-stu-id="b2259-110">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool and Director pool (if you have deployed Directors), you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b2259-111">Il listener e la regola di pubblicazione del proxy inverso possono essere utilizzati sia per i servizi Web esterni che per il servizio di individuazione automatica, purché il certificato assegnato al listener contenga il nome soggetto e i nomi alternativi del soggetto di entrambi.</span><span class="sxs-lookup"><span data-stu-id="b2259-111">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="b2259-112">Per informazioni dettagliate sulla configurazione predefinita del listener Web e della regola di pubblicazione, vedere <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span><span class="sxs-lookup"><span data-stu-id="b2259-112">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="b2259-113">Se si decide di utilizzare HTTP per le richieste iniziali del servizio di individuazione automatica in modo da non dover aggiornare i nomi alternativi del soggetto per il proxy inverso, sarà necessario creare o modificare una regola di pubblicazione Web per la porta 80.</span><span class="sxs-lookup"><span data-stu-id="b2259-113">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="b2259-114">Nelle procedure incluse in questa sezione viene descritto come creare o modificare le regole di pubblicazione Web in Microsoft Forefront Threat Management Gateway 2010 per l'individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="b2259-114">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b2259-p104">Tali procedure partono dal presupposto che sia stata installata la Standard Edition di Forefront Threat Management Gateway (TMG) 2010. Se si sta usando un altro proxy inverso, le procedure sono simili, ma devono essere associate alla documentazione del prodotto di terze parti.</span><span class="sxs-lookup"><span data-stu-id="b2259-p104">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010. If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="b2259-117">Per creare una regola di pubblicazione Web per l'URL del servizio di individuazione automatica esterno</span><span class="sxs-lookup"><span data-stu-id="b2259-117">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="b2259-118">Fare clic sul pulsante **Start**, scegliere **Programmi**, **Microsoft Forefront TMG** e quindi **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="b2259-118">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="b2259-119">Nel riquadro sinistro espandere **NomeServer**, fare clic con il pulsante destro del mouse su **Criterio firewall**, scegliere **Nuovo** e quindi fare clic su **Regola di pubblicazione sito Web**.</span><span class="sxs-lookup"><span data-stu-id="b2259-119">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="b2259-120">Nella pagina **Nuova regola di pubblicazione Web** digitare un nome visualizzato per la nuova regola di pubblicazione, ad esempio URLIndividuazioneLync.</span><span class="sxs-lookup"><span data-stu-id="b2259-120">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="b2259-121">Nella pagina **Seleziona azione regola** selezionare **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="b2259-121">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="b2259-122">Nella pagina **Tipo di pubblicazione** selezionare **Pubblica un singolo sito Web o un sistema di bilanciamento del carico**.</span><span class="sxs-lookup"><span data-stu-id="b2259-122">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="b2259-123">Nella pagina **Protezione connessione server** selezionare **Utilizzare SSL per connettersi al server Web pubblicato o alla server farm**.</span><span class="sxs-lookup"><span data-stu-id="b2259-123">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="b2259-124">In **nome sito interno**della pagina **Dettagli pubblicazione interna** Digitare il nome di dominio completo (FQDN) del pool di server Director, ad esempio lyncdir01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="b2259-124">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="b2259-125">Se si sta creando una regola per l'URL dei servizi Web esterni nel pool Front End, digitare il nome di dominio completo del pool Front End, ad esempio lyncpool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="b2259-125">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN of the Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="b2259-126">In **percorso (facoltativo)** nella pagina **Dettagli pubblicazione interna** Digitare **/\*** come percorso della cartella da pubblicare e quindi selezionare **Inoltra l'intestazione host originale**.</span><span class="sxs-lookup"><span data-stu-id="b2259-126">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="b2259-127">Nella pagina **Dettagli nome pubblico** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2259-127">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="b2259-128">In **Accetta richieste per** selezionare **Nome dominio**.</span><span class="sxs-lookup"><span data-stu-id="b2259-128">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="b2259-129">In **nome pubblico**Digitare **lyncdiscover.**\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="b2259-129">In **Public Name**, type **lyncdiscover.**\<sipdomain\></span></span> <span data-ttu-id="b2259-130">(l'URL del servizio di individuazione automatica esterno).</span><span class="sxs-lookup"><span data-stu-id="b2259-130">(the external Autodiscover Service URL).</span></span> <span data-ttu-id="b2259-131">Se si sta creando una regola per l'URL dei servizi Web esterni nel pool Front End, digitare il nome di dominio completo per i servizi Web esterni nel pool Front End (ad esempio, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b2259-131">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="b2259-132">In **percorso**Digitare **/\*** .</span><span class="sxs-lookup"><span data-stu-id="b2259-132">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="b2259-133">In **Listener Web** nella pagina **Scegliere Listener Web** selezionare il listener SSL esistente con il certificato pubblico aggiornato.</span><span class="sxs-lookup"><span data-stu-id="b2259-133">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="b2259-134">Nella pagina **Delega autenticazione** selezionare **Nessuna delega, ma il client può eseguire l'autenticazione direttamente**.</span><span class="sxs-lookup"><span data-stu-id="b2259-134">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="b2259-135">Nella pagina **Gruppo di utenti** selezionare **Tutti gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="b2259-135">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="b2259-136">Nella pagina **Completamento della Creazione guidata regola di pubblicazione sul Web** verificare che le impostazioni della regola di pubblicazione Web siano corrette e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="b2259-136">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="b2259-137">Nell'elenco delle regole di pubblicazione Web di Forefront TMG fare doppio clic sulla nuova regola appena aggiunta per aprire **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b2259-137">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="b2259-138">Nella scheda **Per** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2259-138">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="b2259-139">Selezionare **Inoltra l'intestazione host originale e non quella effettiva (nel campo Nome sito interno)**.</span><span class="sxs-lookup"><span data-stu-id="b2259-139">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="b2259-140">Selezionare **Le richieste sembrano provenire dal computer Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="b2259-140">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="b2259-141">Nella scheda **Bridging** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2259-141">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="b2259-142">Selezionare **Server Web**.</span><span class="sxs-lookup"><span data-stu-id="b2259-142">Select **Web server**.</span></span>
    
      - <span data-ttu-id="b2259-143">Selezionare **Reindirizza richieste alla porta HTTP** e quindi digitare **8080** come numero di porta.</span><span class="sxs-lookup"><span data-stu-id="b2259-143">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="b2259-144">Selezionare **Reindirizza richieste alla porta SSL** e digitare **4443** come numero di porta.</span><span class="sxs-lookup"><span data-stu-id="b2259-144">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="b2259-145">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2259-145">Click **OK**.</span></span>

18. <span data-ttu-id="b2259-146">Nel riquadro dei dettagli fare clic su **Applica** per salvare le modifiche e aggiornare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="b2259-146">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="b2259-147">Fare clic su **Prova regola** per verificare che la nuova regola sia configurata correttamente.</span><span class="sxs-lookup"><span data-stu-id="b2259-147">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="b2259-148">Per modificare una regola di pubblicazione Web esistente e aggiungere un nome soggetto alternativo e un URL di individuazione automatica esterno</span><span class="sxs-lookup"><span data-stu-id="b2259-148">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="b2259-149">Fare clic sul pulsante **Start**, scegliere **Programmi**, **Microsoft Forefront TMG** e quindi **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="b2259-149">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b2259-150">Ripetere la modifica per ogni listener e regola di pubblicazione disponibile.</span><span class="sxs-lookup"><span data-stu-id="b2259-150">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="b2259-151">In genere, si tratta di una regola e di un listener per i pool Front end e uno per i pool di amministratori o di server Director facoltativi, se sono stati distribuiti.</span><span class="sxs-lookup"><span data-stu-id="b2259-151">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="b2259-p108">Nel riquadro sinistro espandere **NomeServer**, fare clic con il pulsante destro del mouse su **Criterio firewall** e quindi scegliere la regola applicabile. Nella scheda **Attività** fare clic su **Modifica regola selezionata**.</span><span class="sxs-lookup"><span data-stu-id="b2259-p108">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule. On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="b2259-154">Nella scheda **Nome pubblico**, nell'elenco **Questa regola di applica a** selezionare **Richieste per i seguenti siti Web**.</span><span class="sxs-lookup"><span data-stu-id="b2259-154">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="b2259-155">Fare clic su **Aggiungi**, digitare il nome del nuovo sito di individuazione automatica (ad esempio lyncdiscover.contoso.com) e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2259-155">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="b2259-p109">Nella scheda **Listener** fare clic su **Seleziona certificato** e assegnare il nuovo certificato con le voci SAN di individuazione automatica aggiunte. Chiudere le proprietà del listener e di pubblicazione Web.</span><span class="sxs-lookup"><span data-stu-id="b2259-p109">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries. Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="b2259-158">Fare clic su **Applica** nel riquadro dei dettagli per salvare le modifiche e aggiornare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="b2259-158">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="b2259-159">Fare clic su **Prova regola** per verificare che la nuova regola sia configurata correttamente.</span><span class="sxs-lookup"><span data-stu-id="b2259-159">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="b2259-160">Per creare una regola di pubblicazione Web per la porta 80</span><span class="sxs-lookup"><span data-stu-id="b2259-160">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="b2259-161">Fare clic sul pulsante **Start**, scegliere **Programmi**, **Microsoft Forefront TMG** e quindi fare clic su **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="b2259-161">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="b2259-162">Nel riquadro sinistro espandere **NomeServer**, fare clic con il pulsante destro del mouse su **Criterio firewall**, scegliere **Nuovo** e quindi fare clic su **Regola di pubblicazione sito Web**.</span><span class="sxs-lookup"><span data-stu-id="b2259-162">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="b2259-163">Nella pagina **Nuova regola di pubblicazione Web** digitare un nome visualizzato per la nuova regola di pubblicazione, ad esempio Individuazione automatica Lync (HTTP).</span><span class="sxs-lookup"><span data-stu-id="b2259-163">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="b2259-164">Nella pagina **Seleziona azione regola** selezionare **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="b2259-164">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="b2259-165">Nella pagina **Tipo di pubblicazione** selezionare **Pubblica un singolo sito Web o un sistema di bilanciamento del carico**.</span><span class="sxs-lookup"><span data-stu-id="b2259-165">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="b2259-166">Nella pagina **Protezione connessione server** selezionare **Utilizzare connessioni non protette per connettersi al server Web pubblicato o alla server farm**.</span><span class="sxs-lookup"><span data-stu-id="b2259-166">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="b2259-167">Nella pagina **Dettagli pubblicazione interna** , in **nome sito interno**digitare l'FQDN dei servizi Web interni per il pool Front End, ad esempio lyncpool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="b2259-167">On the **Internal Publishing Details** page, in **Internal Site name**, type the internal Web Services FQDN for your Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="b2259-168">In **percorso (facoltativo)** nella pagina **Dettagli pubblicazione interna** Digitare **/\*** come percorso della cartella da pubblicare e quindi selezionare **Inoltra l'intestazione host originale invece di quella specificata nel campo nome sito interno**.</span><span class="sxs-lookup"><span data-stu-id="b2259-168">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="b2259-169">Nella pagina **Dettagli nome pubblico** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2259-169">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="b2259-170">In **Accetta richieste per** selezionare **Nome dominio**.</span><span class="sxs-lookup"><span data-stu-id="b2259-170">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="b2259-171">In **nome pubblico**Digitare **lyncdiscover.**\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="b2259-171">In **Public Name**, type **lyncdiscover.**\<sipdomain\></span></span> <span data-ttu-id="b2259-172">(l'URL del servizio di individuazione automatica esterno).</span><span class="sxs-lookup"><span data-stu-id="b2259-172">(the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="b2259-173">In **percorso**Digitare **/\*** .</span><span class="sxs-lookup"><span data-stu-id="b2259-173">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="b2259-174">In **Listener Web** nella pagina **Scegliere Listener Web** selezionare un listener Web oppure utilizzare la Creazione guidata definizione listener Web per crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="b2259-174">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="b2259-175">Nella pagina **Delega autenticazione** selezionare **Nessuna delega, ma il client può eseguire l'autenticazione direttamente**.</span><span class="sxs-lookup"><span data-stu-id="b2259-175">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="b2259-176">Nella pagina **Gruppo di utenti** selezionare **Tutti gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="b2259-176">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="b2259-177">Nella pagina **Completamento della Creazione guidata regola di pubblicazione sul Web** verificare che le impostazioni della regola di pubblicazione Web siano corrette e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="b2259-177">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="b2259-178">Nell'elenco delle regole di pubblicazione Web di Forefront TMG fare doppio clic sulla nuova regola appena aggiunta per aprire **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b2259-178">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="b2259-179">Nella scheda **Bridging** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2259-179">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="b2259-180">Selezionare **Server Web**.</span><span class="sxs-lookup"><span data-stu-id="b2259-180">Select **Web server**.</span></span>
    
      - <span data-ttu-id="b2259-181">Selezionare **Reindirizza richieste alla porta HTTP** e digitare **8080** come numero di porta.</span><span class="sxs-lookup"><span data-stu-id="b2259-181">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="b2259-182">Verificare che l'opzione **Reindirizza richieste alla porta SSL** non sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="b2259-182">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="b2259-183">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2259-183">Click **OK**.</span></span>

17. <span data-ttu-id="b2259-184">Nel riquadro dei dettagli fare clic su **Applica** per salvare le modifiche e aggiornare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="b2259-184">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="b2259-185">Fare clic su **Prova regola** per verificare che la nuova regola sia configurata correttamente.</span><span class="sxs-lookup"><span data-stu-id="b2259-185">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="b2259-186">Verificare che l'URL del servizio di individuazione automatica esterno non sia definito in altre regole di pubblicazione Web.</span><span class="sxs-lookup"><span data-stu-id="b2259-186">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b2259-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2259-187">See Also</span></span>


[<span data-ttu-id="b2259-188">Configurazione dei server proxy inversi per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2259-188">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

