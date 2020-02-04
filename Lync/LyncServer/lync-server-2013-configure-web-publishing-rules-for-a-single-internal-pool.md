---
title: 'Lync Server 2013: Configurare le regole di pubblicazione Web per un singolo pool interno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ea798f3d5cefa3b65194eb8afcb6e9b35aaa9c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a><span data-ttu-id="90bb2-102">Configurare le regole di pubblicazione Web per un singolo pool interno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90bb2-102">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90bb2-103">_**Argomento Ultima modifica:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="90bb2-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="90bb2-104">Microsoft Forefront Threat Management Gateway 2010 e Internet Information Server Application Request Routing (IIS ARR) usa le regole di pubblicazione Web per pubblicare risorse interne, ad esempio un URL di riunione, per gli utenti su Internet.</span><span class="sxs-lookup"><span data-stu-id="90bb2-104">Microsoft Forefront Threat Management Gateway 2010 and Internet Information Server Application Request Routing (IIS ARR) uses web publishing rules to publish internal resources, such as a meeting URL, to users on the Internet.</span></span>

<span data-ttu-id="90bb2-105">Oltre agli URL dei servizi Web per le directory virtuali, devi anche creare regole di pubblicazione per URL semplici, l'URL LyncDiscover e il server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="90bb2-105">In addition to the Web Services URLs for the virtual directories, you must also create publishing rules for simple URLs, the LyncDiscover URL, and the Office Web Apps Server.</span></span> <span data-ttu-id="90bb2-106">Per ogni URL semplice, devi creare una singola regola nel proxy inverso che punta a tale URL semplice.</span><span class="sxs-lookup"><span data-stu-id="90bb2-106">For each simple URL, you must create an individual rule on the reverse proxy that points to that simple URL.</span></span>

<span data-ttu-id="90bb2-107">Se si sta distribuendo la mobilità e si usa l'individuazione automatica, è necessario creare una regola di pubblicazione per l'URL del servizio di rilevamento automatico esterno.</span><span class="sxs-lookup"><span data-stu-id="90bb2-107">If you are deploying mobility and using automatic discovery, you need to create a publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="90bb2-108">L'individuazione automatica richiede anche regole di pubblicazione per l'URL dei servizi Web Lync Server esterni per il pool di Director e per il pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="90bb2-108">Automatic discovery also requires publishing rules for the external Lync Server Web Services URL for your Director pool and Front End pool.</span></span> <span data-ttu-id="90bb2-109">Per informazioni dettagliate sulla creazione delle regole di pubblicazione Web per l'individuazione automatica, vedere [configurazione del proxy inverso per la mobilità in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="90bb2-109">For details about creating the web publishing rules for automatic discovery, see [Configuring the reverse proxy for mobility in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span></span>

<span data-ttu-id="90bb2-110">Usare le procedure seguenti per creare regole di pubblicazione Web.</span><span class="sxs-lookup"><span data-stu-id="90bb2-110">Use the following procedures to create web publishing rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="90bb2-111">Queste procedure presuppongono che sia stata installata la versione standard di Forefront Threat Management Gateway (TMG) 2010 o che sia stato installato e configurato Internet Information Server con l'estensione di IIS ARR (Application Request Routing).</span><span class="sxs-lookup"><span data-stu-id="90bb2-111">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010 or have installed and configured Internet Information Server with the Application request Routing (IIS ARR) extension.</span></span> <span data-ttu-id="90bb2-112">Si usa TMG o IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="90bb2-112">You use either TMG or IIS ARR.</span></span>



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a><span data-ttu-id="90bb2-113">Per creare una regola di pubblicazione del server Web nel computer che utilizza TMG 2010</span><span class="sxs-lookup"><span data-stu-id="90bb2-113">To create a web server publishing rule on the computer running TMG 2010</span></span>

1.  <span data-ttu-id="90bb2-114">Fare clic sul pulsante **Start**, selezionare **programmi**, **Microsoft Forefront TMG**e quindi fare clic su **gestione di Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-114">Click **Start**, select **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="90bb2-115">Nel riquadro sinistro espandere **nomeserver**, fare clic con il pulsante destro del mouse su **criteri firewall**, scegliere **nuovo**e quindi fare clic su **regola pubblicazione sito Web**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-115">In the left pane, expand **ServerName**, right-click **Firewall Policy**, select **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="90bb2-116">Nella pagina **Welcome to the New Web Publishing Rule** Digitare un nome visualizzato per la regola di pubblicazione, ad esempio LyncServerWebDownloadsRule.</span><span class="sxs-lookup"><span data-stu-id="90bb2-116">On the **Welcome to the New Web Publishing Rule** page, type a display name for the publishing rule (for example, LyncServerWebDownloadsRule).</span></span>

4.  <span data-ttu-id="90bb2-117">Nella pagina **selezionare l'azione di regola** selezionare **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-117">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="90bb2-118">Nella pagina **tipo di pubblicazione** selezionare **pubblica un singolo sito Web o bilanciamento del carico**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-118">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="90bb2-119">Nella pagina **sicurezza connessione server** selezionare **Usa SSL per connettersi al server Web pubblicato o alla server farm**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-119">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="90bb2-120">Nella pagina **Internal Publishing Details** Digitare il nome di dominio completo (FQDN) della Web farm interna che ospita il contenuto della riunione e la Rubrica nella casella **nome sito interno** .</span><span class="sxs-lookup"><span data-stu-id="90bb2-120">On the **Internal Publishing Details** page, type the fully qualified domain name (FQDN) of the internal web farm that hosts your meeting content and Address Book content in the **Internal Site name** box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90bb2-121">Se il server interno è un server Standard Edition, il nome completo è il nome di dominio completo del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="90bb2-121">If your internal server is a Standard Edition server, this FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="90bb2-122">Se il server interno è un pool Front-End, il nome completo è un IP virtuale (VIP) di bilanciamento del carico hardware che bilancia il carico dei server della Web farm interna.</span><span class="sxs-lookup"><span data-stu-id="90bb2-122">If your internal server is a Front End pool, this FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="90bb2-123">Il server TMG deve essere in grado di risolvere il nome di dominio completo nell'indirizzo IP del server Web interno.</span><span class="sxs-lookup"><span data-stu-id="90bb2-123">The TMG server must be able to resolve the FQDN to the IP address of the internal web server.</span></span> <span data-ttu-id="90bb2-124">Se il server TMG non è in grado di risolvere il nome di dominio completo con l'indirizzo IP corretto, è possibile selezionare Usa l'indirizzo <STRONG>IP del computer per connettersi al server pubblicato</STRONG>e quindi digitare l'indirizzo IP del server Web interno nella casella <STRONG>nome computer o</STRONG> <STRONG>indirizzo IP</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="90bb2-124">If the TMG server is not able to resolve the FQDN to the proper IP address, you can select <STRONG>Use a computer name or IP address to connect to the published server</STRONG>, and then in the <STRONG>Computer name or</STRONG> <STRONG>IP address</STRONG> box, type the IP address of the internal web server.</span></span> <span data-ttu-id="90bb2-125">In questo caso, devi assicurarti che la porta 53 sia aperta nel server TMG e che possa raggiungere un server DNS che risiede nella rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="90bb2-125">If you do this, you must ensure that port 53 is open on the TMG server and that it can reach a DNS server that resides in the perimeter network.</span></span> <span data-ttu-id="90bb2-126">È anche possibile usare le voci nel file hosts locale per specificare la risoluzione dei nomi.</span><span class="sxs-lookup"><span data-stu-id="90bb2-126">You can also use entries in the local hosts file to provide name resolution.</span></span>

    
    </div>

8.  <span data-ttu-id="90bb2-127">Nella casella **percorso (facoltativo)** della pagina \*\* / \*\* **Internal Publishing Details** Digitare il percorso della cartella da pubblicare.</span><span class="sxs-lookup"><span data-stu-id="90bb2-127">On the **Internal Publishing Details** page, in the **Path (optional)** box, type **/\*** as the path of the folder to be published.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90bb2-128">Nella pubblicazione guidata sito Web è possibile specificare solo un percorso.</span><span class="sxs-lookup"><span data-stu-id="90bb2-128">In the website publishing wizard you can only specify one path.</span></span> <span data-ttu-id="90bb2-129">I percorsi aggiuntivi possono essere aggiunti modificando le proprietà della regola.</span><span class="sxs-lookup"><span data-stu-id="90bb2-129">Additional paths can be added by modifying the properties of the rule.</span></span>

    
    </div>

9.  <span data-ttu-id="90bb2-130">Nella pagina **Public Name Details** verificare che il **nome di dominio** sia selezionato in **accetta richieste per**digitare l'FQDN dei servizi Web esterni nella casella **nome pubblico** .</span><span class="sxs-lookup"><span data-stu-id="90bb2-130">On the **Public Name Details** page, confirm that **This domain name** is selected under **Accept Requests for**, type the external Web Services FQDN, in the **Public Name** box.</span></span>

10. <span data-ttu-id="90bb2-131">Nella pagina **Seleziona listener Web** fare clic su **nuovo** per aprire la creazione guidata nuova definizione listener Web.</span><span class="sxs-lookup"><span data-stu-id="90bb2-131">On **Select Web Listener** page, click **New** to open the New Web Listener Definition Wizard.</span></span>

11. <span data-ttu-id="90bb2-132">Nella pagina **Introduzione alla creazione guidata nuovo listener Web** Digitare un nome per il listener Web nella casella **nome listener Web** , ad esempio LyncServerWebServers.</span><span class="sxs-lookup"><span data-stu-id="90bb2-132">On the **Welcome to the New Web Listener Wizard** page, type a name for the web listener in the **Web listener name** box (for example, LyncServerWebServers).</span></span>

12. <span data-ttu-id="90bb2-133">Nella pagina **sicurezza connessione client** selezionare **Richiedi connessioni protette SSL con i client**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-133">On the **Client Connection Security** page, select **Require SSL secured connections with clients**.</span></span>

13. <span data-ttu-id="90bb2-134">Nella pagina **indirizzo IP del listener Web** selezionare **esterno**e quindi fare clic su **Seleziona indirizzi IP**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-134">On the **Web Listener IP Address** page, select **External**, and then click **Select IP Addresses**.</span></span>

14. <span data-ttu-id="90bb2-135">Nella pagina di **Selezione IP del listener esterno** selezionare l' **indirizzo IP specificato nel computer Forefront TMG nella rete selezionata**, selezionare l'indirizzo IP appropriato, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-135">On the **External Listener IP selection** page, select **Specified IP address on the Forefront TMG computer in the selected network**, select the appropriate IP address, click **Add**.</span></span>

15. <span data-ttu-id="90bb2-136">Nella pagina **certificati SSL listener** selezionare **assegna un certificato per ogni indirizzo IP**, selezionare l'indirizzo IP associato al nome FQDN Web esterno e quindi fare clic su **Seleziona certificato**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-136">On the **Listener SSL Certificates** page, select **Assign a certificate for each IP address**, select the IP address that is associated with the external web FQDN, and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="90bb2-137">Nella pagina **Seleziona certificato** selezionare il certificato che corrisponde ai nomi pubblici specificati nel passaggio 9, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-137">On the **Select Certificate** page, select the certificate that matches the public names specified in step 9, click **Select**.</span></span>

17. <span data-ttu-id="90bb2-138">Nella pagina **impostazione autenticazione** selezionare **Nessuna autenticazione**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-138">On the **Authentication Setting** page, select **No Authentication**.</span></span>

18. <span data-ttu-id="90bb2-139">Nella pagina **Single Sign on setting** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-139">On the **Single Sign On Setting** page, click **Next**.</span></span>

19. <span data-ttu-id="90bb2-140">Nella pagina **completamento della creazione guidata listener Web** verificare che le impostazioni del **listener Web** siano corrette e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-140">On the **Completing the Web Listener Wizard** page, verify that the **Web listener** settings are correct, and then click **Finish**.</span></span>

20. <span data-ttu-id="90bb2-141">Nella pagina **Delega autenticazione** selezionare **Nessuna delega, ma il client può eseguire l'autenticazione direttamente**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-141">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

21. <span data-ttu-id="90bb2-142">Nella pagina **set di utenti** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-142">On the **User Set** page, click **Next**.</span></span>

22. <span data-ttu-id="90bb2-143">Nella pagina **completamento della nuova creazione guidata regola Web Publishing** verificare che le impostazioni della regola di pubblicazione Web siano corrette e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-143">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

23. <span data-ttu-id="90bb2-144">Fare clic su **applica** nel riquadro dei dettagli per salvare le modifiche e aggiornare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="90bb2-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a><span data-ttu-id="90bb2-145">Per creare una regola di pubblicazione del server Web nel computer in cui è in uso IIS ARR</span><span class="sxs-lookup"><span data-stu-id="90bb2-145">To create a web server publishing rule on the computer running IIS ARR</span></span>

1.  <span data-ttu-id="90bb2-146">Associa il certificato che userai per il proxy inverso al protocollo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="90bb2-146">Bind the certificate that you will use for the reverse proxy to the HTTPS protocol.</span></span> <span data-ttu-id="90bb2-147">Fare clic sul pulsante **Start**, selezionare **programmi**, **strumenti di amministrazione**e quindi fare clic su **Gestione Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-147">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90bb2-148">Ulteriori informazioni, schermate e indicazioni per la distribuzione e la configurazione di IIS ARR sono disponibili nell'articolo NextHop <A href="http://go.microsoft.com/fwlink/?linkid=293391">con IIS ARR come proxy inverso per Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="90bb2-148">Additional help, screen shots and guidance on deploying and configuring IIS ARR can be found in the NextHop article <A href="http://go.microsoft.com/fwlink/?linkid=293391">Using IIS ARR as a Reverse Proxy for Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="90bb2-149">Se non è già stato fatto, importare il certificato che verrà usato per il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="90bb2-149">If you have not already done so, import the certificate that you will use for the reverse proxy.</span></span> <span data-ttu-id="90bb2-150">In **Gestione Internet Information Services (IIS)** fare clic sul nome del server proxy inverso nella dimensione sinistra della console.</span><span class="sxs-lookup"><span data-stu-id="90bb2-150">In **Internet Information Services (IIS) Manager**, click the reverse proxy server name on the left-hand size of the console.</span></span> <span data-ttu-id="90bb2-151">Al centro della console in **IIS** individuare i **certificati server**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-151">In the middle of the console under **IIS** locate **Server Certificates**.</span></span> <span data-ttu-id="90bb2-152">Fare clic con il pulsante destro del mouse su **certificati server** e scegliere **Apri funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-152">Right-click **Server Certificates** and select **Open feature**.</span></span>

3.  <span data-ttu-id="90bb2-153">Sul lato destro della console fare clic su **Importa...**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-153">On the right hand side of the console, click **Import…**.</span></span> <span data-ttu-id="90bb2-154">Digitare il percorso e il nome del file del certificato con l'estensione oppure fare clic su **...**</span><span class="sxs-lookup"><span data-stu-id="90bb2-154">Type the path and filename of the certificate with the extension, or click **…**</span></span> <span data-ttu-id="90bb2-155">per cercare il certificato.</span><span class="sxs-lookup"><span data-stu-id="90bb2-155">to browse for the certificate.</span></span> <span data-ttu-id="90bb2-156">Selezionare il certificato e fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-156">Select the certificate and click **Open**.</span></span> <span data-ttu-id="90bb2-157">Specificare la password usata per proteggere la chiave privata (se è stata assegnata una password durante l'esportazione del certificato e della chiave privata).</span><span class="sxs-lookup"><span data-stu-id="90bb2-157">Supply the password used to protect the private key (if you assigned a password when exporting the certificate and private key).</span></span> <span data-ttu-id="90bb2-158">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-158">Click **OK**.</span></span> <span data-ttu-id="90bb2-159">Se l'importazione del certificato è stata eseguita correttamente, il certificato verrà visualizzato come voce nel centro della console come voce in **certificati server**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-159">If the certificate import was successful, the certificate will appear as an entry in the middle of the console as an entry in **Server Certificates**.</span></span>

4.  <span data-ttu-id="90bb2-160">Assegnare il certificato per l'uso da parte di HTTPS.</span><span class="sxs-lookup"><span data-stu-id="90bb2-160">Assign the certificate for use by HTTPS.</span></span> <span data-ttu-id="90bb2-161">Sul lato sinistro della console selezionare il **sito Web predefinito** del server IIS.</span><span class="sxs-lookup"><span data-stu-id="90bb2-161">On the left-hand side of the console, select the **Default Web Site** of the IIS server.</span></span> <span data-ttu-id="90bb2-162">Sul lato destro fare clic su **Binding...**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-162">On the right-hand side, click **Bindings…**.</span></span> <span data-ttu-id="90bb2-163">Nella finestra di dialogo **Associazioni sito** fare clic su **Aggiungi...**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-163">In the **Site Bindings** dialog, click **Add…**.</span></span> <span data-ttu-id="90bb2-164">Nella finestra di dialogo **Aggiungi binding sito** in **tipo:** Selezionare **https**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-164">On the **Add Site Binding** dialog under **Type:**, select **https**.</span></span> <span data-ttu-id="90bb2-165">La selezione di HTTPS consente di selezionare il certificato da usare per HTTPS.</span><span class="sxs-lookup"><span data-stu-id="90bb2-165">Selecting https will allow you to select the certificate to use for https.</span></span> <span data-ttu-id="90bb2-166">In **certificato SSL:** selezionare il certificato importato per il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="90bb2-166">Under **SSL certificate:**, select the certificate that you imported for the reverse proxy.</span></span> <span data-ttu-id="90bb2-167">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-167">Click **OK**.</span></span> <span data-ttu-id="90bb2-168">Quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-168">Then, click **Close**.</span></span> <span data-ttu-id="90bb2-169">Il certificato è ora associato al proxy inverso per Secure Socket Layer (SSL) e Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="90bb2-169">The certificate is now bound to the reverse proxy for secure socket layer (SSL) and transport layer security (TLS).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="90bb2-170">Se viene visualizzato un messaggio di avviso quando si chiudono le finestre di dialogo Binding che mancano ai certificati intermedi, è necessario individuare e importare il certificato autorità di certificazione radice pubblica e gli eventuali certificati intermedi della CA.</span><span class="sxs-lookup"><span data-stu-id="90bb2-170">If you receive a warning when closing the Bindings dialogs that intermediate certificates are missing, you need to locate and import the public CA root authority certificate and any intermediate CA certificates.</span></span> <span data-ttu-id="90bb2-171">Consultare le istruzioni della CA pubblica a cui è stato richiesto il certificato e seguire le istruzioni per richiedere e importare una catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="90bb2-171">Consult the instructions at the public CA that you requested your certificate from and follow the instructions to request and import a certificate chain.</span></span> <span data-ttu-id="90bb2-172">Se il certificato è stato esportato dall'Edge Server, è possibile esportare il certificato della CA radice e gli eventuali certificati intermedi della CA associati al server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="90bb2-172">If you exported the certificate from your Edge Server, you can export the root CA certificate and any intermediate CA certificates associated with the Edge Server.</span></span> <span data-ttu-id="90bb2-173">Importare il certificato della CA radice nel computer (da non confondere con l'archivio degli utenti) archiviare le autorità di certificazione radice attendibili e i certificati intermedi nell'archivio delle autorità di certificazione intermedi del computer.</span><span class="sxs-lookup"><span data-stu-id="90bb2-173">Import the root CA certificate into the Computer’s (not to be confused with the User store) Trusted Root Certification Authorities store and intermediate certificates into the Computer’s Intermediate Certification Authorities store.</span></span>

    
    </div>

5.  <span data-ttu-id="90bb2-174">Sul lato sinistro della console sotto il nome del server IIS fare clic con il pulsante destro del mouse su **Server** Farms e quindi scegliere **Crea server farm...**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-174">On the left-hand side of the console below the IIS server name, right-click **Server Farms** then click **Create Server Farm…**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90bb2-175">Se il nodo <STRONG>Server Farms</STRONG> non è visibile, è necessario installare il routing delle richieste di applicazione.</span><span class="sxs-lookup"><span data-stu-id="90bb2-175">If you do not see the <STRONG>Server Farms</STRONG> node, you need to install Application Request Routing.</span></span> <span data-ttu-id="90bb2-176">Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configurazione di server proxy inversa per Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="90bb2-176">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="90bb2-177">Nella finestra di dialogo **Crea server farm** in **nome server farm**digitare il nome (può essere un nome descrittivo per scopi di identificazione) per il primo URL.</span><span class="sxs-lookup"><span data-stu-id="90bb2-177">On the **Create Server Farm** dialog in **Server farm name**, type the a name (this can be a friendly name for identification purposes) for the first URL.</span></span> <span data-ttu-id="90bb2-178">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-178">Click **Next**.</span></span>

6.  <span data-ttu-id="90bb2-179">Nella finestra di dialogo **Aggiungi server** in **Indirizzo server**digitare il nome di dominio completo (FQDN) dei servizi Web esterni nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="90bb2-179">On the **Add Server** dialog in **Server Address**, type the fully qualified domain name (FQDN) of the external web services on your Front End Server.</span></span> <span data-ttu-id="90bb2-180">I nomi che verranno usati qui ad esempio per scopi sono gli stessi usati nella sezione pianificazione per il proxy inverso, il [proxy di riepilogo del certificato in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="90bb2-180">The names that will be used here for example purposes are the same that are used in the Planning section for the reverse proxy, [Certificate summary - Reverse proxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span></span> <span data-ttu-id="90bb2-181">Facendo riferimento alla pianificazione del proxy inverso, digitiamo il nome `webext.contoso.com`di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="90bb2-181">Referring to the reverse proxy planning, we type the FQDN `webext.contoso.com`.</span></span> <span data-ttu-id="90bb2-182">Verificare che la casella di controllo accanto a **online** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="90bb2-182">Confirm that the checkbox next to **Online** is selected.</span></span> <span data-ttu-id="90bb2-183">Fare clic su **Aggiungi** per aggiungere il server al pool di server Web per questa configurazione.</span><span class="sxs-lookup"><span data-stu-id="90bb2-183">Click **Add** to add the server to the pool of web servers for this configuration.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="90bb2-184">Lync Server usa i dispositivi di bilanciamento del carico hardware per il pool Director e i server front end per il traffico HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="90bb2-184">Lync Server uses hardware load balancers to pool Director and Front End Servers for HTTP and HTTPS traffic.</span></span> <span data-ttu-id="90bb2-185">Verrà fornito un nome di dominio completo solo quando si aggiunge un server alla server farm di IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="90bb2-185">You will only supply one FQDN when adding a server to the IIS ARR Server Farm.</span></span> <span data-ttu-id="90bb2-186">Il nome di dominio completo sarà il server front-end o il Director nelle configurazioni del server non in pool o il nome di dominio completo del bilanciamento del carico hardware configurato per i pool di server.</span><span class="sxs-lookup"><span data-stu-id="90bb2-186">The FQDN will be the Front End Server or Director in non-pooled server configurations, or the FQDN of the configured hardware load balancer for server pools.</span></span> <span data-ttu-id="90bb2-187">L'unico metodo supportato per caricare il traffico HTTP e HTTPS tramite il bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="90bb2-187">The only supported method to load balance HTTP and HTTPS traffic is by using hardware load balancers.</span></span>

    
    </div>

7.  <span data-ttu-id="90bb2-188">Nella finestra di dialogo **Aggiungi server** fare clic su **Impostazioni avanzate.**</span><span class="sxs-lookup"><span data-stu-id="90bb2-188">On the **Add Server** dialog, click **Advanced settings…**.</span></span> <span data-ttu-id="90bb2-189">Verrà aperta una finestra di dialogo che consente di definire il routing delle richieste di applicazioni per il nome di dominio completo configurato.</span><span class="sxs-lookup"><span data-stu-id="90bb2-189">This opens a dialog to define application request routing for requests to the configured FQDN.</span></span> <span data-ttu-id="90bb2-190">Lo scopo è quello di ridefinire quale porta viene usata quando la richiesta viene elaborata da IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="90bb2-190">The purpose is to redefine what port is used when the request is processed by IIS ARR.</span></span>
    
    <span data-ttu-id="90bb2-191">Per impostazione predefinita, la porta HTTP di destinazione deve essere definita come 8080.</span><span class="sxs-lookup"><span data-stu-id="90bb2-191">By default, the destination HTTP port must be defined as 8080.</span></span> <span data-ttu-id="90bb2-192">Fare clic su accanto alla corrente **httpPort 80** e impostare il valore su **8080**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-192">Click next to the current **httpPort 80** and set the value to **8080**.</span></span> <span data-ttu-id="90bb2-193">Fare clic su accanto alla corrente **httpsPort 443** e impostare il valore su **4443**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-193">Click next to the current **httpsPort 443** and set the value to **4443**.</span></span> <span data-ttu-id="90bb2-194">Abbandonare il parametro **Weight** in 100.</span><span class="sxs-lookup"><span data-stu-id="90bb2-194">Leave the **weight** parameter at 100.</span></span> <span data-ttu-id="90bb2-195">Se necessario, è possibile ridefinire i pesi per una determinata regola dopo avere statistiche di base.</span><span class="sxs-lookup"><span data-stu-id="90bb2-195">If needed, you can redefine weights for a given rule once you have baseline statistics.</span></span> <span data-ttu-id="90bb2-196">Fare clic su **fine** per completare questa parte della configurazione della regola.</span><span class="sxs-lookup"><span data-stu-id="90bb2-196">Click **Finish** to complete this part of the rule configuration.</span></span>

8.  <span data-ttu-id="90bb2-197">Potrebbe essere visualizzata una finestra di dialogo di riscrittura delle regole che informa che Gestione IIS può creare una regola di riscrittura URL per instradare automaticamente tutte le richieste in arrivo alla server farm.</span><span class="sxs-lookup"><span data-stu-id="90bb2-197">You may see a dialog Rewrite Rules that informs you that IIS Manager can create a URL rewrite rule to route all incoming requests to the server farm automatically.</span></span> <span data-ttu-id="90bb2-198">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-198">Click **Yes**.</span></span> <span data-ttu-id="90bb2-199">Le regole verranno modificate manualmente, ma selezionando Sì viene impostata la configurazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="90bb2-199">You will adjust the rules manually, but selecting Yes sets the initial configuration..</span></span>

9.  <span data-ttu-id="90bb2-200">Fare clic sul nome della server farm appena creato.</span><span class="sxs-lookup"><span data-stu-id="90bb2-200">Click the name of the server farm that you have just created.</span></span> <span data-ttu-id="90bb2-201">In **server farm** in visualizzazione funzionalità di gestione IIS fare doppio clic su **memorizzazione nella cache**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-201">Under **Server Farm** in IIS Manager Features View, you double-click **Caching**.</span></span> <span data-ttu-id="90bb2-202">Deselezionare **Attiva cache disco**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-202">Deselect **Enable disk cache**.</span></span> <span data-ttu-id="90bb2-203">Fare clic su **applica** sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="90bb2-203">Click **Apply** on the right-hand side.</span></span>

10. <span data-ttu-id="90bb2-204">Fare clic sul nome della server farm.</span><span class="sxs-lookup"><span data-stu-id="90bb2-204">Click the name of the server farm.</span></span> <span data-ttu-id="90bb2-205">In **server farm** in visualizzazione funzionalità di gestione IIS fare doppio clic su **proxy**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-205">Under **Server Farm** in IIS Manager Features View, you double-click **Proxy**.</span></span> <span data-ttu-id="90bb2-206">Nella pagina impostazioni proxy modificare il valore per il **timeout (secondi)** in un valore appropriato per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="90bb2-206">On the Proxy settings page change the value for **Time-out (seconds)** to a value appropriate for your deployment.</span></span> <span data-ttu-id="90bb2-207">Fare clic su **applica** per salvare la modifica.</span><span class="sxs-lookup"><span data-stu-id="90bb2-207">Click **Apply** to save the change.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="90bb2-208">Il valore di timeout del proxy è un numero che può variare dalla distribuzione alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="90bb2-208">The Proxy Time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="90bb2-209">È consigliabile monitorare la distribuzione e modificare il valore per l'esperienza ottimale per i client.</span><span class="sxs-lookup"><span data-stu-id="90bb2-209">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="90bb2-210">Potresti essere in grado di impostare il valore in basso come 200.</span><span class="sxs-lookup"><span data-stu-id="90bb2-210">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="90bb2-211">Se si supportano client mobili Lync nell'ambiente, è necessario impostare il valore su 960 per consentire il timeout delle notifiche push da Office 365 che hanno un valore di timeout di 900.</span><span class="sxs-lookup"><span data-stu-id="90bb2-211">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notifications timeout from Office 365 which have a time-out value of 900.</span></span> <span data-ttu-id="90bb2-212">È molto probabile che sia necessario aumentare il valore di timeout per evitare la disconnessione del client quando il valore è troppo basso o ridurre il numero se le connessioni tramite il proxy non si disconnettono e si cancellano molto dopo la disconnessione del client.</span><span class="sxs-lookup"><span data-stu-id="90bb2-212">It is very likely that you will need to increase the time-out value to avoid client disconnects when the value is too low or decrease the number if connections through the proxy do not disconnect and clear long after the client has disconnected.</span></span> <span data-ttu-id="90bb2-213">Il monitoraggio e la fodera di base ciò che è normale per l'ambiente è l'unico mezzo preciso per determinare la posizione corretta per questo valore.</span><span class="sxs-lookup"><span data-stu-id="90bb2-213">Monitoring and base-lining what is normal for your environment is the only accurate means to determine where the right setting is for this value.</span></span>

    
    </div>

11. <span data-ttu-id="90bb2-214">Fare clic sul nome della server farm.</span><span class="sxs-lookup"><span data-stu-id="90bb2-214">Click the name of the server farm.</span></span> <span data-ttu-id="90bb2-215">In **server farm** in visualizzazione funzionalità di gestione IIS fare doppio clic su **regole di routing**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-215">Under **Server Farm** in IIS Manager Features View, you double-click **Routing Rules**.</span></span> <span data-ttu-id="90bb2-216">Nella finestra di dialogo regole di routing in routing deselezionare la casella di controllo accanto a Consenti ripartizione del carico SSL.</span><span class="sxs-lookup"><span data-stu-id="90bb2-216">On the Routing Rules dialog under Routing, clear the checkbox next to Enable SSL offloading.</span></span> <span data-ttu-id="90bb2-217">Se la possibilità di deselezionare la casella di controllo non è disponibile, selezionare l'opzione per l' **uso della riscrittura URL per esaminare le richieste in arrivo**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-217">If the ability to clear the checkbox is not available, select the checkbox for **Use URL Rewrite to inspect incoming requests**.</span></span> <span data-ttu-id="90bb2-218">Fare clic su **applica** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="90bb2-218">Click **Apply** to save your changes.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="90bb2-219">La ripartizione dello scarico SSL tramite il proxy inverso non è supportata.</span><span class="sxs-lookup"><span data-stu-id="90bb2-219">SSL Offloading by the reverse proxy is not supported.</span></span>

    
    </div>

12. <span data-ttu-id="90bb2-220">Ripetere i passaggi 5-11 per ogni URL che deve passare tramite il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="90bb2-220">Repeat Steps 5-11 for each URL that must pass through the reverse proxy.</span></span> <span data-ttu-id="90bb2-221">Un elenco comune dovrebbe essere il seguente:</span><span class="sxs-lookup"><span data-stu-id="90bb2-221">A common list would be the following:</span></span>
    
      - <span data-ttu-id="90bb2-222">Servizi Web front-end server esterni: webext.contoso.com (già configurato tramite la passeggiata iniziale)</span><span class="sxs-lookup"><span data-stu-id="90bb2-222">Front End Server Web services external: webext.contoso.com (already configured by initial walk through)</span></span>
    
      - <span data-ttu-id="90bb2-223">Director Web Services esterni per Director: webdirext.contoso.com (facoltativo se un amministratore è distribuito)</span><span class="sxs-lookup"><span data-stu-id="90bb2-223">Director Web services external for Director: webdirext.contoso.com (Optional if a Director is deployed)</span></span>
    
      - <span data-ttu-id="90bb2-224">URL semplice riunione: meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90bb2-224">Simple URL meet: meet.contoso.com</span></span>
    
      - <span data-ttu-id="90bb2-225">Dialin URL semplice: dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90bb2-225">Simple URL dialin: dialin.contoso.com</span></span>
    
      - <span data-ttu-id="90bb2-226">URL di individuazione automatica di Lync: lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90bb2-226">Lync Autodiscover URL: lyncdiscover.contoso.com</span></span>
    
      - <span data-ttu-id="90bb2-227">URL del server Office Web Apps: officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90bb2-227">Office Web Apps Server URL: officewebapps01.contoso.com</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="90bb2-228">L'URL per il server Office Web Apps userà un indirizzo httpsPort diverso.</span><span class="sxs-lookup"><span data-stu-id="90bb2-228">The URL for the Office Web Apps Server will use a different httpsPort address.</span></span> <span data-ttu-id="90bb2-229">Nel passaggio 7 Definisci <STRONG>httpsPort</STRONG> come <STRONG>443</STRONG> e <STRONG>httpport</STRONG> come porta <STRONG>80</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="90bb2-229">In step 7, you define the <STRONG>httpsPort</STRONG> as <STRONG>443</STRONG> and the <STRONG>httpPort</STRONG> as port <STRONG>80</STRONG>.</span></span> <span data-ttu-id="90bb2-230">Tutte le altre impostazioni di configurazione sono le stesse.</span><span class="sxs-lookup"><span data-stu-id="90bb2-230">All other configuration settings are the same.</span></span>

        
        </div>

13. <span data-ttu-id="90bb2-231">Sul lato sinistro della console fare clic sul nome del server IIS.</span><span class="sxs-lookup"><span data-stu-id="90bb2-231">On the left-hand side of the console, click the IIS server name.</span></span> <span data-ttu-id="90bb2-232">Al centro della console individuare la **riscrittura URL** in **IIS**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-232">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="90bb2-233">Fare doppio clic su Riscrivi URL per aprire la configurazione delle regole di riscrittura degli URL.</span><span class="sxs-lookup"><span data-stu-id="90bb2-233">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span> <span data-ttu-id="90bb2-234">Dovresti vedere le regole per ogni server farm creata nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="90bb2-234">You should see rules for each Server Farm that you created in the previous steps.</span></span> <span data-ttu-id="90bb2-235">In caso contrario, verificare di aver fatto clic sul nome del **server IIS** immediatamente sotto il nodo **pagina iniziale** nella console Internet Information Server Manager.</span><span class="sxs-lookup"><span data-stu-id="90bb2-235">If you do not, confirm that you clicked on the **IIS Server** name immediately below the **Start Page** node in the Internet Information Server Manager console.</span></span>

14. <span data-ttu-id="90bb2-236">Nella finestra di dialogo **URL riscrittura** , usando webext.contoso.com come esempio, il nome completo della regola visualizzata è **\_arr webext.contoso.com\_loadbalance\_SSL**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-236">In the **URL Rewrite** dialog, using webext.contoso.com as an example, the full name of the rule as displayed is **ARR\_webext.contoso.com\_loadbalance\_SSL**.</span></span>
    
      - <span data-ttu-id="90bb2-237">Fare doppio clic sulla regola per aprire la finestra di dialogo **Modifica regola in ingresso** .</span><span class="sxs-lookup"><span data-stu-id="90bb2-237">Double-click the rule to open the **Edit Inbound Rule** dialog.</span></span>
    
      - <span data-ttu-id="90bb2-238">Fare clic su **Aggiungi...**</span><span class="sxs-lookup"><span data-stu-id="90bb2-238">Click **Add…**</span></span> <span data-ttu-id="90bb2-239">nella finestra di dialogo **condizioni** .</span><span class="sxs-lookup"><span data-stu-id="90bb2-239">on the **Conditions** dialog.</span></span>
    
      - <span data-ttu-id="90bb2-240">Nella condizione **Add** in **input Condition:** digitare **{http\_host}**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-240">On the **Add Condition** in **Condition input:** type **{HTTP\_HOST}**.</span></span> <span data-ttu-id="90bb2-241">(Durante la digitazione viene visualizzata una finestra di dialogo che consente di selezionare la condizione).</span><span class="sxs-lookup"><span data-stu-id="90bb2-241">(As you type, a dialog appears that will let you select the condition).</span></span> <span data-ttu-id="90bb2-242">in **Controlla se stringa di input:** seleziona **corrisponde allo schema**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-242">under **Check if input string:** select **Matches the Pattern**.</span></span> <span data-ttu-id="90bb2-243">Nel tipo **\*** di **input pattern** .</span><span class="sxs-lookup"><span data-stu-id="90bb2-243">In the **Pattern input** type **\***.</span></span> <span data-ttu-id="90bb2-244">La **distinzione tra maiuscole e minuscole** deve essere selezionata.</span><span class="sxs-lookup"><span data-stu-id="90bb2-244">**Ignore case** should be selected.</span></span> <span data-ttu-id="90bb2-245">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-245">Click **OK**.</span></span>
    
      - <span data-ttu-id="90bb2-246">Scorrere verso il basso nella finestra di dialogo **Modifica regola in entrata** per individuare la finestra di dialogo **azione** .</span><span class="sxs-lookup"><span data-stu-id="90bb2-246">Scroll down in the **Edit Inbound Rule** dialog to locate the **Action** dialog.</span></span> <span data-ttu-id="90bb2-247">**Tipo di azione:** deve essere impostato su **route to server farm**, **Scheme:** set to **https://**, **server farm:** impostato sull'URL a cui è applicata la regola.</span><span class="sxs-lookup"><span data-stu-id="90bb2-247">**Action Type:** should be set to **Route to Server Farm**, **Scheme:** set to **https://**, **Server farm:** set to the URL that this rule applies to.</span></span> <span data-ttu-id="90bb2-248">Per questo esempio, questo deve essere impostato su **webext.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-248">For this example, this should be set to **webext.contoso.com**.</span></span> <span data-ttu-id="90bb2-249">**Path:** è impostato su **/{R: 0}**</span><span class="sxs-lookup"><span data-stu-id="90bb2-249">**Path:** is set to **/{R:0}**</span></span>
    
      - <span data-ttu-id="90bb2-250">Fare clic su **applica** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="90bb2-250">Click **Apply** to save your changes.</span></span> <span data-ttu-id="90bb2-251">Fare clic su **Torna alle regole** per tornare alle regole di riscrittura degli URL.</span><span class="sxs-lookup"><span data-stu-id="90bb2-251">Click **Back to Rules** to return to the URL Rewrite rules.</span></span>

15. <span data-ttu-id="90bb2-252">Ripetere la procedura definita nel passaggio 14 per ognuna delle regole di riscrittura SSL definite, una per ogni URL della farm server.</span><span class="sxs-lookup"><span data-stu-id="90bb2-252">Repeat the procedure defined in Step 14 for each of the SSL rewrite rules that you have defined, one per Server Farm URL.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="90bb2-253">Per impostazione predefinita, vengono create anche le regole HTTP e sono contrassegnate dalla denominazione simile alle regole SSL.</span><span class="sxs-lookup"><span data-stu-id="90bb2-253">By default, HTTP rules are created as well and are denoted by the similar naming to the SSL rules.</span></span> <span data-ttu-id="90bb2-254">Per l'esempio corrente, la regola HTTP sarà denominata <STRONG>ARR_webext. contoso. com_loadbalance</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="90bb2-254">For our current example, the HTTP rule would be named <STRONG>ARR_webext.contoso.com_loadbalance</STRONG>.</span></span> <span data-ttu-id="90bb2-255">Per queste regole non sono necessarie modifiche e possono essere ignorate in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="90bb2-255">No modifications are needed to these rules and they can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a><span data-ttu-id="90bb2-256">Per modificare le proprietà della regola di pubblicazione Web in TMG 2010</span><span class="sxs-lookup"><span data-stu-id="90bb2-256">To modify the properties of the web publishing rule in TMG 2010</span></span>

1.  <span data-ttu-id="90bb2-257">Fare clic sul pulsante **Start**, scegliere **programmi**, **Microsoft Forefront TMG**e quindi fare clic su **gestione di Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-257">Click **Start**, point to **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="90bb2-258">Nel riquadro sinistro espandere **nomeserver**e quindi fare clic su **criteri firewall**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-258">In the left pane, expand **ServerName**, and then click **Firewall Policy**.</span></span>

3.  <span data-ttu-id="90bb2-259">Nel riquadro dei dettagli fare clic con il pulsante destro del mouse sulla regola di pubblicazione del server Web creata nella procedura precedente, ad esempio LyncServerExternalRule, e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-259">In the details pane, right-click the web server publishing rule that you created in the previous procedure (for example, LyncServerExternalRule), and then click **Properties**.</span></span>

4.  <span data-ttu-id="90bb2-260">Nella scheda **da** della pagina **Proprietà** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="90bb2-260">On the **Properties** page, on the **From** tab, do the following:</span></span>
    
      - <span data-ttu-id="90bb2-261">In **questa regola si applica al traffico proveniente da questi** elenchi di origini, fare clic in un **punto qualsiasi**e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-261">In the **This rule applies to traffic from these sources** list, click **Anywhere**, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="90bb2-262">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-262">Click **Add**.</span></span>
    
      - <span data-ttu-id="90bb2-263">In **Aggiungi entità di rete**espandere **reti**, fare clic su **esterno**, fare clic su **Aggiungi**e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-263">In **Add Network Entities**, expand **Networks**, click **External**, click **Add**, and then click **Close**.</span></span>

5.  <span data-ttu-id="90bb2-264">Nella scheda **a** verificare che la casella di controllo **Inoltra l'intestazione host originale invece di quella effettiva** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="90bb2-264">On the **To** tab, ensure that the **Forward the original host header instead of the actual one** check box is selected.</span></span>

6.  <span data-ttu-id="90bb2-265">Nella scheda **bridging** selezionare la casella di controllo **reindirizza la richiesta alla porta SSL** e quindi specificare la porta **4443**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-265">On the **Bridging** tab, select the **Redirect request to SSL port** check box, and then specify port **4443**.</span></span>

7.  <span data-ttu-id="90bb2-266">Nella scheda **nome pubblico** aggiungere gli URL semplici, ad esempio meet.contoso.com e dialin.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="90bb2-266">On the **Public Name** tab, add the simple URLs (for example, meet.contoso.com and dialin.contoso.com).</span></span>

8.  <span data-ttu-id="90bb2-267">Fare clic su **applica** per salvare le modifiche e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-267">Click **Apply** to save changes, and then click **OK**.</span></span>

9.  <span data-ttu-id="90bb2-268">Fare clic su **applica** nel riquadro dei dettagli per salvare le modifiche e aggiornare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="90bb2-268">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a><span data-ttu-id="90bb2-269">Per modificare le proprietà della regola di pubblicazione Web in IIS ARR</span><span class="sxs-lookup"><span data-stu-id="90bb2-269">To modify the properties of the web publishing rule in IIS ARR</span></span>

1.  <span data-ttu-id="90bb2-270">Fare clic sul pulsante **Start**, selezionare **programmi**, **strumenti di amministrazione**e quindi fare clic su **Gestione Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-270">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="90bb2-271">Sul lato sinistro della console fare clic sul nome del server IIS.</span><span class="sxs-lookup"><span data-stu-id="90bb2-271">On the left-hand side of the console, click the IIS server name.</span></span>

3.  <span data-ttu-id="90bb2-272">Al centro della console individuare la **riscrittura URL** in **IIS**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-272">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="90bb2-273">Fare doppio clic su Riscrivi URL per aprire la configurazione delle regole di riscrittura degli URL.</span><span class="sxs-lookup"><span data-stu-id="90bb2-273">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span>

4.  <span data-ttu-id="90bb2-274">Fare doppio clic sulla regola che è necessario modificare.</span><span class="sxs-lookup"><span data-stu-id="90bb2-274">Double-click the rule that you need to modify.</span></span> <span data-ttu-id="90bb2-275">Apportare le modifiche necessarie, in corrispondenza di **URL**, **condizioni**, **variabili del server** o **azione**.</span><span class="sxs-lookup"><span data-stu-id="90bb2-275">Make your modifications, as needed, in **Match URL**, **Conditions**, **Server Variables** or **Action**.</span></span>

5.  <span data-ttu-id="90bb2-276">Fare clic su **applica** per eseguire il commit delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="90bb2-276">Click **Apply** to commit your changes.</span></span> <span data-ttu-id="90bb2-277">Fare clic su **Torna alle regole** per modificare altre regole oppure chiudere la console di **Gestione IIS** , se è stata completata la modifica.</span><span class="sxs-lookup"><span data-stu-id="90bb2-277">Click **Back to Rules** to modify other rules, or close the **IIS Manager** console if you are done with your changes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

