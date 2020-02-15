---
title: 'Lync Server 2013: configurare le regole di pubblicazione Web per un singolo pool interno'
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
ms.openlocfilehash: 8d87e0096ee71fb08da396188d419e918f66e125
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a><span data-ttu-id="6e5cc-102">Configurare le regole di pubblicazione Web per un singolo pool interno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e5cc-102">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e5cc-103">_**Ultimo argomento modificato:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="6e5cc-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="6e5cc-104">Microsoft Forefront Threat Management Gateway 2010 e Internet Information Server Application Request Routing (IIS ARR) utilizza le regole di pubblicazione Web per pubblicare risorse interne, ad esempio un URL di riunione, per gli utenti su Internet.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-104">Microsoft Forefront Threat Management Gateway 2010 and Internet Information Server Application Request Routing (IIS ARR) uses web publishing rules to publish internal resources, such as a meeting URL, to users on the Internet.</span></span>

<span data-ttu-id="6e5cc-105">Oltre agli URL dei servizi Web per le directory virtuali, è inoltre necessario creare regole di pubblicazione per gli URL semplici, l'URL di LyncDiscover e il server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-105">In addition to the Web Services URLs for the virtual directories, you must also create publishing rules for simple URLs, the LyncDiscover URL, and the Office Web Apps Server.</span></span> <span data-ttu-id="6e5cc-106">Per ogni URL semplice, è necessario creare una singola regola nel proxy inverso che punti a tale URL semplice.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-106">For each simple URL, you must create an individual rule on the reverse proxy that points to that simple URL.</span></span>

<span data-ttu-id="6e5cc-107">Se si sta eseguendo la distribuzione per dispositivi mobili e si utilizza l'individuazione automatica, è necessario creare una regola di pubblicazione per l'URL esterno del servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-107">If you are deploying mobility and using automatic discovery, you need to create a publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="6e5cc-108">L'individuazione automatica richiede anche regole di pubblicazione per l'URL dei servizi Web di Lync Server esterno per il pool di Director e per il pool Front end.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-108">Automatic discovery also requires publishing rules for the external Lync Server Web Services URL for your Director pool and Front End pool.</span></span> <span data-ttu-id="6e5cc-109">Per informazioni dettagliate sulla creazione delle regole di pubblicazione Web per l'individuazione automatica, vedere [configurazione del proxy inverso per i dispositivi mobili in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="6e5cc-109">For details about creating the web publishing rules for automatic discovery, see [Configuring the reverse proxy for mobility in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span></span>

<span data-ttu-id="6e5cc-110">Per creare regole di pubblicazione Web, eseguire le procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-110">Use the following procedures to create web publishing rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e5cc-111">In queste procedure si presuppone che sia stata installata la versione Standard Edition di Forefront Threat Management Gateway (TMG) 2010 oppure che sia stato installato e configurato Internet Information Server con l'estensione del routing delle richieste di applicazioni (IIS ARR).</span><span class="sxs-lookup"><span data-stu-id="6e5cc-111">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010 or have installed and configured Internet Information Server with the Application request Routing (IIS ARR) extension.</span></span> <span data-ttu-id="6e5cc-112">Si utilizza TMG o IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-112">You use either TMG or IIS ARR.</span></span>



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a><span data-ttu-id="6e5cc-113">Per creare una regola di pubblicazione del server Web nel computer che esegue TMG 2010</span><span class="sxs-lookup"><span data-stu-id="6e5cc-113">To create a web server publishing rule on the computer running TMG 2010</span></span>

1.  <span data-ttu-id="6e5cc-114">Fare clic sul pulsante **Start**, selezionare **Programmi**, **Microsoft Forefront TMG** e quindi fare clic su **Gestione Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-114">Click **Start**, select **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="6e5cc-115">Nel riquadro sinistro espandere **NomeServer**, fare clic con il pulsante destro del mouse su **Criterio firewall**, selezionare **Nuovo** e quindi fare clic su **Regola di pubblicazione sito Web**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-115">In the left pane, expand **ServerName**, right-click **Firewall Policy**, select **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="6e5cc-116">Nella pagina **Nuova regola di pubblicazione Web** digitare un nome visualizzato per la regola di pubblicazione, ad esempio RegolaDownloadWebLyncServer.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-116">On the **Welcome to the New Web Publishing Rule** page, type a display name for the publishing rule (for example, LyncServerWebDownloadsRule).</span></span>

4.  <span data-ttu-id="6e5cc-117">Nella pagina **Seleziona azione regola** selezionare **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-117">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="6e5cc-118">Nella pagina **Tipo di pubblicazione** selezionare **Pubblica un singolo sito Web o un sistema di bilanciamento del carico**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-118">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="6e5cc-119">Nella pagina **Protezione connessione server** selezionare **Utilizzare SSL per connettersi al server Web pubblicato o alla server farm**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-119">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="6e5cc-120">Nella pagina **Dettagli pubblicazione interna** digitare il nome di dominio completo (FQDN) della Web farm interna che ospita il contenuto delle riunioni e della Rubrica nella casella **Nome sito interno**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-120">On the **Internal Publishing Details** page, type the fully qualified domain name (FQDN) of the internal web farm that hosts your meeting content and Address Book content in the **Internal Site name** box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6e5cc-121">Se il server interno è un server Standard Edition, il nome di dominio completo corrisponde al nome di dominio completo del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-121">If your internal server is a Standard Edition server, this FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="6e5cc-122">Se il server interno è un pool Front End, il nome di dominio completo corrisponde a un indirizzo VIP (Virtual IP) del servizio di bilanciamento del carico hardware che si occupa del bilanciamento del carico dei server interni della Web farm.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-122">If your internal server is a Front End pool, this FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="6e5cc-123">Il server TMG deve essere in grado di risolvere il nome di dominio completo nell'indirizzo IP del server Web interno.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-123">The TMG server must be able to resolve the FQDN to the IP address of the internal web server.</span></span> <span data-ttu-id="6e5cc-124">Se il server TMG non è in grado di risolvere il nome di dominio completo con l'indirizzo IP appropriato, è possibile selezionare <STRONG>Usa un indirizzo IP o un computer per connettersi al server pubblicato</STRONG>e quindi digitare l'indirizzo IP del server Web interno nella casella <STRONG>nome computer o</STRONG> <STRONG>indirizzo IP</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="6e5cc-124">If the TMG server is not able to resolve the FQDN to the proper IP address, you can select <STRONG>Use a computer name or IP address to connect to the published server</STRONG>, and then in the <STRONG>Computer name or</STRONG> <STRONG>IP address</STRONG> box, type the IP address of the internal web server.</span></span> <span data-ttu-id="6e5cc-125">In tal caso, è necessario verificare che la porta 53 sia aperta nel server TMG e che sia possibile raggiungere un server DNS che si trova nella rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-125">If you do this, you must ensure that port 53 is open on the TMG server and that it can reach a DNS server that resides in the perimeter network.</span></span> <span data-ttu-id="6e5cc-126">È anche possibile utilizzare le voci nell'host locale per la risoluzione dei nomi.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-126">You can also use entries in the local hosts file to provide name resolution.</span></span>

    
    </div>

8.  <span data-ttu-id="6e5cc-127">Nella casella **percorso (facoltativo)** della pagina \*\* / \*\* **Dettagli pubblicazione interna** Digitare il percorso della cartella da pubblicare.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-127">On the **Internal Publishing Details** page, in the **Path (optional)** box, type **/\*** as the path of the folder to be published.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6e5cc-p105">Nella procedura guidata di pubblicazione del sito Web è possibile specificare solo un percorso. Per aggiungere altri percorsi, è necessario modificare le proprietà della regola.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-p105">In the website publishing wizard you can only specify one path. Additional paths can be added by modifying the properties of the rule.</span></span>

    
    </div>

9.  <span data-ttu-id="6e5cc-130">Nella pagina **Dettagli nome pubblico** verificare che sia selezionata l'opzione **Nome dominio** in **Accetta richieste per** e digitare il nome di dominio completo esterno dei Servizi Web nella casella **Nome pubblico**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-130">On the **Public Name Details** page, confirm that **This domain name** is selected under **Accept Requests for**, type the external Web Services FQDN, in the **Public Name** box.</span></span>

10. <span data-ttu-id="6e5cc-131">Nella pagina **Scegliere Listener Web** fare clic su **Nuovo** per aprire la Creazione guidata definizione listener Web.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-131">On **Select Web Listener** page, click **New** to open the New Web Listener Definition Wizard.</span></span>

11. <span data-ttu-id="6e5cc-132">Nella pagina **Creazione guidata listener Web** digitare un nome per il listener Web nella casella **Nome listener Web**, ad esempio ServerWebLyncServer.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-132">On the **Welcome to the New Web Listener Wizard** page, type a name for the web listener in the **Web listener name** box (for example, LyncServerWebServers).</span></span>

12. <span data-ttu-id="6e5cc-133">Nella pagina **Protezione di connessione client** selezionare **Richiedi connessioni SSL protette con i client**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-133">On the **Client Connection Security** page, select **Require SSL secured connections with clients**.</span></span>

13. <span data-ttu-id="6e5cc-134">Nella pagina **Indirizzi IP del listener Web** selezionare **Esterno** e quindi fare clic su **Seleziona indirizzi IP**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-134">On the **Web Listener IP Address** page, select **External**, and then click **Select IP Addresses**.</span></span>

14. <span data-ttu-id="6e5cc-135">Nella pagina **Selezione IP listener esterno** selezionare **Indirizzo IP specificato nel computer Forefront TMG nella rete selezionata**, selezionare l'indirizzo IP appropriato e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-135">On the **External Listener IP selection** page, select **Specified IP address on the Forefront TMG computer in the selected network**, select the appropriate IP address, click **Add**.</span></span>

15. <span data-ttu-id="6e5cc-136">Nella pagina **Certificati SSL listener** selezionare **Assegna un certificato a ciascun indirizzo IP**, selezionare l'indirizzo IP associato al nome FQDN Web esterno e quindi fare clic su **Seleziona certificato**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-136">On the **Listener SSL Certificates** page, select **Assign a certificate for each IP address**, select the IP address that is associated with the external web FQDN, and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="6e5cc-137">Nella pagina **Seleziona certificato** selezionare il certificato corrispondente ai nomi pubblici specificati al passaggio 9 e fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-137">On the **Select Certificate** page, select the certificate that matches the public names specified in step 9, click **Select**.</span></span>

17. <span data-ttu-id="6e5cc-138">Nella pagina **Impostazione di autenticazione** selezionare **Nessuna autenticazione**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-138">On the **Authentication Setting** page, select **No Authentication**.</span></span>

18. <span data-ttu-id="6e5cc-139">Nella pagina **Impostazioni Single Sign-On** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-139">On the **Single Sign On Setting** page, click **Next**.</span></span>

19. <span data-ttu-id="6e5cc-140">Nella pagina **Completamento della Creazione guidata listener Web** verificare che le impostazioni specificate in **Listener Web** siano corrette e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-140">On the **Completing the Web Listener Wizard** page, verify that the **Web listener** settings are correct, and then click **Finish**.</span></span>

20. <span data-ttu-id="6e5cc-141">Nella pagina **Delega autenticazione** selezionare **Nessuna delega, ma il client può eseguire l'autenticazione direttamente**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-141">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

21. <span data-ttu-id="6e5cc-142">Nella pagina **Gruppo di utenti** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-142">On the **User Set** page, click **Next**.</span></span>

22. <span data-ttu-id="6e5cc-143">Nella pagina **Completamento della Creazione guidata regola di pubblicazione Web** verificare che le impostazioni della regola di pubblicazione Web siano corrette e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-143">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

23. <span data-ttu-id="6e5cc-144">Nel riquadro dei dettagli fare clic su **Applica** per salvare le modifiche e aggiornare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a><span data-ttu-id="6e5cc-145">Per creare una regola di pubblicazione del server Web nel computer in cui è in esecuzione IIS ARR</span><span class="sxs-lookup"><span data-stu-id="6e5cc-145">To create a web server publishing rule on the computer running IIS ARR</span></span>

1.  <span data-ttu-id="6e5cc-146">Associare il certificato che verrà utilizzato per il proxy inverso al protocollo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-146">Bind the certificate that you will use for the reverse proxy to the HTTPS protocol.</span></span> <span data-ttu-id="6e5cc-147">Fare clic sul pulsante **Start**, scegliere **programmi**, **strumenti di amministrazione**e quindi fare clic su **Gestione Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-147">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6e5cc-148">Ulteriori informazioni, schermate e linee guida per la distribuzione e la configurazione di IIS ARR sono disponibili nell'articolo di NextHop <A href="http://go.microsoft.com/fwlink/?linkid=293391">che utilizza IIS ARR come proxy inverso per Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-148">Additional help, screen shots and guidance on deploying and configuring IIS ARR can be found in the NextHop article <A href="http://go.microsoft.com/fwlink/?linkid=293391">Using IIS ARR as a Reverse Proxy for Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="6e5cc-149">Se non è stato ancora fatto, importare il certificato che verrà utilizzato per il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-149">If you have not already done so, import the certificate that you will use for the reverse proxy.</span></span> <span data-ttu-id="6e5cc-150">In **Gestione Internet Information Services (IIS)** fare clic sul nome del server proxy inverso sul lato sinistro della console.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-150">In **Internet Information Services (IIS) Manager**, click the reverse proxy server name on the left-hand size of the console.</span></span> <span data-ttu-id="6e5cc-151">Al centro della console in **IIS** individuare i **certificati del server**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-151">In the middle of the console under **IIS** locate **Server Certificates**.</span></span> <span data-ttu-id="6e5cc-152">Fare clic con il pulsante destro del mouse su **certificati server** e scegliere **Apri funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-152">Right-click **Server Certificates** and select **Open feature**.</span></span>

3.  <span data-ttu-id="6e5cc-153">Sul lato destro della console, fare clic su **Importa...**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-153">On the right hand side of the console, click **Import…**.</span></span> <span data-ttu-id="6e5cc-154">Digitare il percorso e il nome del file del certificato con l'estensione oppure fare clic su **...**</span><span class="sxs-lookup"><span data-stu-id="6e5cc-154">Type the path and filename of the certificate with the extension, or click **…**</span></span> <span data-ttu-id="6e5cc-155">per cercare il certificato.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-155">to browse for the certificate.</span></span> <span data-ttu-id="6e5cc-156">Selezionare il certificato e fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-156">Select the certificate and click **Open**.</span></span> <span data-ttu-id="6e5cc-157">Fornire la password utilizzata per proteggere la chiave privata (se è stata assegnata una password quando si esporta il certificato e la chiave privata).</span><span class="sxs-lookup"><span data-stu-id="6e5cc-157">Supply the password used to protect the private key (if you assigned a password when exporting the certificate and private key).</span></span> <span data-ttu-id="6e5cc-158">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-158">Click **OK**.</span></span> <span data-ttu-id="6e5cc-159">Se l'importazione del certificato ha avuto esito positivo, il certificato verrà visualizzato come voce al centro della console come voce nei **certificati del server**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-159">If the certificate import was successful, the certificate will appear as an entry in the middle of the console as an entry in **Server Certificates**.</span></span>

4.  <span data-ttu-id="6e5cc-160">Assegnare il certificato per l'utilizzo da parte di HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-160">Assign the certificate for use by HTTPS.</span></span> <span data-ttu-id="6e5cc-161">Sul lato sinistro della console, selezionare il **sito Web predefinito** del server IIS.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-161">On the left-hand side of the console, select the **Default Web Site** of the IIS server.</span></span> <span data-ttu-id="6e5cc-162">Sul lato destro fare clic su **Binding.**</span><span class="sxs-lookup"><span data-stu-id="6e5cc-162">On the right-hand side, click **Bindings…**.</span></span> <span data-ttu-id="6e5cc-163">Nella finestra di dialogo **binding sito** fare clic su **Aggiungi...**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-163">In the **Site Bindings** dialog, click **Add…**.</span></span> <span data-ttu-id="6e5cc-164">Nella finestra di dialogo **Aggiungi binding sito** in **tipo:** Selezionare **https**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-164">On the **Add Site Binding** dialog under **Type:**, select **https**.</span></span> <span data-ttu-id="6e5cc-165">Se si seleziona HTTPS, sarà possibile selezionare il certificato da utilizzare per HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-165">Selecting https will allow you to select the certificate to use for https.</span></span> <span data-ttu-id="6e5cc-166">In **certificato SSL:** selezionare il certificato importato per il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-166">Under **SSL certificate:**, select the certificate that you imported for the reverse proxy.</span></span> <span data-ttu-id="6e5cc-167">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-167">Click **OK**.</span></span> <span data-ttu-id="6e5cc-168">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-168">Then, click **Close**.</span></span> <span data-ttu-id="6e5cc-169">Il certificato è ora associato al proxy inverso per Secure Socket Layer (SSL) e Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="6e5cc-169">The certificate is now bound to the reverse proxy for secure socket layer (SSL) and transport layer security (TLS).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6e5cc-170">Se viene visualizzato un messaggio di avviso durante la chiusura delle finestre di dialogo Binding che mancano i certificati intermedi, è necessario individuare e importare il certificato dell'autorità radice della CA pubblica e gli eventuali certificati intermedi della CA.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-170">If you receive a warning when closing the Bindings dialogs that intermediate certificates are missing, you need to locate and import the public CA root authority certificate and any intermediate CA certificates.</span></span> <span data-ttu-id="6e5cc-171">Consultare le istruzioni all'autorità di certificazione pubblica di cui è stato richiesto il certificato e seguire le istruzioni per richiedere e importare una catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-171">Consult the instructions at the public CA that you requested your certificate from and follow the instructions to request and import a certificate chain.</span></span> <span data-ttu-id="6e5cc-172">Se il certificato è stato esportato dal server perimetrale, è possibile esportare il certificato della CA radice e tutti i certificati di CA intermedi associati al server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-172">If you exported the certificate from your Edge Server, you can export the root CA certificate and any intermediate CA certificates associated with the Edge Server.</span></span> <span data-ttu-id="6e5cc-173">Importare il certificato della CA radice nel computer (da non confondere con l'archivio utente) archiviare le autorità di certificazione radice attendibili e i certificati intermedi nell'archivio delle autorità di certificazione intermedie del computer.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-173">Import the root CA certificate into the Computer’s (not to be confused with the User store) Trusted Root Certification Authorities store and intermediate certificates into the Computer’s Intermediate Certification Authorities store.</span></span>

    
    </div>

5.  <span data-ttu-id="6e5cc-174">Sul lato sinistro della console sotto il nome del server IIS, fare clic con il pulsante destro del mouse su **Server** farm e quindi scegliere **Crea server farm...**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-174">On the left-hand side of the console below the IIS server name, right-click **Server Farms** then click **Create Server Farm…**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6e5cc-175">Se il nodo <STRONG>server farm</STRONG> non è visualizzato, è necessario installare il routing delle richieste di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-175">If you do not see the <STRONG>Server Farms</STRONG> node, you need to install Application Request Routing.</span></span> <span data-ttu-id="6e5cc-176">Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-176">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="6e5cc-177">Nella finestra di dialogo **Crea server farm** in **nome server farm**digitare il nome (può essere un nome descrittivo ai fini dell'identificazione) per il primo URL.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-177">On the **Create Server Farm** dialog in **Server farm name**, type the a name (this can be a friendly name for identification purposes) for the first URL.</span></span> <span data-ttu-id="6e5cc-178">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-178">Click **Next**.</span></span>

6.  <span data-ttu-id="6e5cc-179">Nella finestra di dialogo **Aggiungi server** nell' **indirizzo del server**, digitare il nome di dominio completo (FQDN) dei servizi Web esterni nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-179">On the **Add Server** dialog in **Server Address**, type the fully qualified domain name (FQDN) of the external web services on your Front End Server.</span></span> <span data-ttu-id="6e5cc-180">I nomi da utilizzare qui ad esempio sono gli stessi utilizzati nella sezione pianificazione per il proxy inverso, il [Riepilogo dei certificati-proxy inverso in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="6e5cc-180">The names that will be used here for example purposes are the same that are used in the Planning section for the reverse proxy, [Certificate summary - Reverse proxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span></span> <span data-ttu-id="6e5cc-181">Facendo riferimento alla pianificazione del proxy inverso, è necessario digitare il `webext.contoso.com`nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-181">Referring to the reverse proxy planning, we type the FQDN `webext.contoso.com`.</span></span> <span data-ttu-id="6e5cc-182">Verificare che sia selezionata la casella di controllo accanto a **online** .</span><span class="sxs-lookup"><span data-stu-id="6e5cc-182">Confirm that the checkbox next to **Online** is selected.</span></span> <span data-ttu-id="6e5cc-183">Fare clic su **Aggiungi** per aggiungere il server al pool di server Web per la configurazione.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-183">Click **Add** to add the server to the pool of web servers for this configuration.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="6e5cc-184">Lync Server utilizza dispositivi di bilanciamento del carico hardware per il pool di server Director e front end per il traffico HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-184">Lync Server uses hardware load balancers to pool Director and Front End Servers for HTTP and HTTPS traffic.</span></span> <span data-ttu-id="6e5cc-185">Si fornirà un solo FQDN quando si aggiunge un server alla server farm di IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-185">You will only supply one FQDN when adding a server to the IIS ARR Server Farm.</span></span> <span data-ttu-id="6e5cc-186">Il nome di dominio completo sarà il front end server o il Director nelle configurazioni del server non in pool o il nome di dominio completo del dispositivo di bilanciamento del carico hardware configurato per i pool di server.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-186">The FQDN will be the Front End Server or Director in non-pooled server configurations, or the FQDN of the configured hardware load balancer for server pools.</span></span> <span data-ttu-id="6e5cc-187">L'unico metodo supportato per il bilanciamento del carico del traffico HTTP e HTTPS consiste nell'utilizzo di dispositivi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-187">The only supported method to load balance HTTP and HTTPS traffic is by using hardware load balancers.</span></span>

    
    </div>

7.  <span data-ttu-id="6e5cc-188">Nella finestra di dialogo **Aggiungi server** fare clic su **Impostazioni avanzate.**</span><span class="sxs-lookup"><span data-stu-id="6e5cc-188">On the **Add Server** dialog, click **Advanced settings…**.</span></span> <span data-ttu-id="6e5cc-189">In questo modo viene aperta una finestra di dialogo per definire il routing delle richieste di applicazioni per l'FQDN configurato.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-189">This opens a dialog to define application request routing for requests to the configured FQDN.</span></span> <span data-ttu-id="6e5cc-190">Lo scopo è quello di ridefinire la porta utilizzata quando la richiesta viene elaborata da IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-190">The purpose is to redefine what port is used when the request is processed by IIS ARR.</span></span>
    
    <span data-ttu-id="6e5cc-191">Per impostazione predefinita, la porta HTTP di destinazione deve essere definita come 8080.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-191">By default, the destination HTTP port must be defined as 8080.</span></span> <span data-ttu-id="6e5cc-192">Fare clic su Avanti per il **httpPort 80** corrente e impostare il valore su **8080**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-192">Click next to the current **httpPort 80** and set the value to **8080**.</span></span> <span data-ttu-id="6e5cc-193">Fare clic su Avanti per il **httpsPort 443** corrente e impostare il valore su **4443**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-193">Click next to the current **httpsPort 443** and set the value to **4443**.</span></span> <span data-ttu-id="6e5cc-194">Lasciare il parametro **Weight** su 100.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-194">Leave the **weight** parameter at 100.</span></span> <span data-ttu-id="6e5cc-195">Se necessario, è possibile ridefinire i pesi per una regola specificata una volta che si dispone di statistiche di base.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-195">If needed, you can redefine weights for a given rule once you have baseline statistics.</span></span> <span data-ttu-id="6e5cc-196">Fare clic su **fine** per completare questa parte della configurazione della regola.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-196">Click **Finish** to complete this part of the rule configuration.</span></span>

8.  <span data-ttu-id="6e5cc-197">È possibile che venga visualizzata una finestra di dialogo di riscrittura delle regole che informa che il responsabile di IIS può creare una regola di riscrittura degli URL per instradare automaticamente tutte le richieste in arrivo alla server farm.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-197">You may see a dialog Rewrite Rules that informs you that IIS Manager can create a URL rewrite rule to route all incoming requests to the server farm automatically.</span></span> <span data-ttu-id="6e5cc-198">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-198">Click **Yes**.</span></span> <span data-ttu-id="6e5cc-199">Le regole verranno adattate manualmente, ma se si seleziona Sì, verrà impostata la configurazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-199">You will adjust the rules manually, but selecting Yes sets the initial configuration..</span></span>

9.  <span data-ttu-id="6e5cc-200">Fare clic sul nome della server farm appena creato.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-200">Click the name of the server farm that you have just created.</span></span> <span data-ttu-id="6e5cc-201">In **server farm** in visualizzazione funzionalità di gestione IIS fare doppio clic su **memorizzazione nella cache**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-201">Under **Server Farm** in IIS Manager Features View, you double-click **Caching**.</span></span> <span data-ttu-id="6e5cc-202">Deselezionare **Abilita cache del disco**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-202">Deselect **Enable disk cache**.</span></span> <span data-ttu-id="6e5cc-203">Fare clic su **applica** sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-203">Click **Apply** on the right-hand side.</span></span>

10. <span data-ttu-id="6e5cc-204">Fare clic sul nome della server farm.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-204">Click the name of the server farm.</span></span> <span data-ttu-id="6e5cc-205">In **server farm** in visualizzazione funzionalità di gestione IIS fare doppio clic su **proxy**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-205">Under **Server Farm** in IIS Manager Features View, you double-click **Proxy**.</span></span> <span data-ttu-id="6e5cc-206">Nella pagina impostazioni proxy modificare il valore di **timeout (secondi)** su un valore appropriato per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-206">On the Proxy settings page change the value for **Time-out (seconds)** to a value appropriate for your deployment.</span></span> <span data-ttu-id="6e5cc-207">Fare clic su **applica** per salvare la modifica.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-207">Click **Apply** to save the change.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6e5cc-208">Il valore di timeout del proxy è un numero che può variare dalla distribuzione alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-208">The Proxy Time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="6e5cc-209">È necessario monitorare la distribuzione e modificare il valore per la migliore esperienza per i client.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-209">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="6e5cc-210">Potrebbe essere possibile impostare il valore come minimo di 200.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-210">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="6e5cc-211">Se si supportano client mobili Lync nell'ambiente, è necessario impostare il valore su 960 per consentire il timeout per le notifiche push da Office 365 che hanno un valore di timeout di 900.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-211">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notifications timeout from Office 365 which have a time-out value of 900.</span></span> <span data-ttu-id="6e5cc-212">È molto probabile che sia necessario aumentare il valore di timeout per evitare che il client si disconnetta quando il valore è troppo basso o diminuisce il numero se le connessioni tramite il proxy non si disconnettono e si cancellano a lungo dopo la disconnessione del client.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-212">It is very likely that you will need to increase the time-out value to avoid client disconnects when the value is too low or decrease the number if connections through the proxy do not disconnect and clear long after the client has disconnected.</span></span> <span data-ttu-id="6e5cc-213">Monitoring and base-Lining ciò che è normale per l'ambiente è l'unico mezzo accurato per determinare la posizione corretta per questo valore.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-213">Monitoring and base-lining what is normal for your environment is the only accurate means to determine where the right setting is for this value.</span></span>

    
    </div>

11. <span data-ttu-id="6e5cc-214">Fare clic sul nome della server farm.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-214">Click the name of the server farm.</span></span> <span data-ttu-id="6e5cc-215">In **server farm** in visualizzazione funzionalità di gestione IIS fare doppio clic su **regole di routing**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-215">Under **Server Farm** in IIS Manager Features View, you double-click **Routing Rules**.</span></span> <span data-ttu-id="6e5cc-216">Nella finestra di dialogo regole di routing in routing, deseleziona la casella di controllo accanto a attiva la ripartizione del carico di protezione SSL.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-216">On the Routing Rules dialog under Routing, clear the checkbox next to Enable SSL offloading.</span></span> <span data-ttu-id="6e5cc-217">Se la possibilità di deselezionare la casella di controllo non è disponibile, selezionare la casella di spunta per **utilizzare la riscrittura URL per esaminare le richieste in arrivo**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-217">If the ability to clear the checkbox is not available, select the checkbox for **Use URL Rewrite to inspect incoming requests**.</span></span> <span data-ttu-id="6e5cc-218">Fare clic su **applica** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-218">Click **Apply** to save your changes.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="6e5cc-219">La ripartizione del carico di inversione SSL tramite il proxy inverso non è supportata.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-219">SSL Offloading by the reverse proxy is not supported.</span></span>

    
    </div>

12. <span data-ttu-id="6e5cc-220">Ripetere i passaggi 5-11 per ogni URL che deve passare attraverso il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-220">Repeat Steps 5-11 for each URL that must pass through the reverse proxy.</span></span> <span data-ttu-id="6e5cc-221">Un elenco comune è il seguente:</span><span class="sxs-lookup"><span data-stu-id="6e5cc-221">A common list would be the following:</span></span>
    
      - <span data-ttu-id="6e5cc-222">Servizi Web front end server esterni: webext.contoso.com (già configurato tramite la passeggiata iniziale)</span><span class="sxs-lookup"><span data-stu-id="6e5cc-222">Front End Server Web services external: webext.contoso.com (already configured by initial walk through)</span></span>
    
      - <span data-ttu-id="6e5cc-223">Servizi Web Director esterni per il server Director: webdirext.contoso.com (facoltativo se è stato distribuito un server Director)</span><span class="sxs-lookup"><span data-stu-id="6e5cc-223">Director Web services external for Director: webdirext.contoso.com (Optional if a Director is deployed)</span></span>
    
      - <span data-ttu-id="6e5cc-224">URL semplice meet: meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6e5cc-224">Simple URL meet: meet.contoso.com</span></span>
    
      - <span data-ttu-id="6e5cc-225">Dialin URL semplice: dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6e5cc-225">Simple URL dialin: dialin.contoso.com</span></span>
    
      - <span data-ttu-id="6e5cc-226">URL di individuazione automatica di Lync: lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6e5cc-226">Lync Autodiscover URL: lyncdiscover.contoso.com</span></span>
    
      - <span data-ttu-id="6e5cc-227">URL del server Office Web Apps: officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6e5cc-227">Office Web Apps Server URL: officewebapps01.contoso.com</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="6e5cc-228">L'URL per il server Office Web Apps utilizzerà un indirizzo httpsPort diverso.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-228">The URL for the Office Web Apps Server will use a different httpsPort address.</span></span> <span data-ttu-id="6e5cc-229">Nel passaggio 7 è possibile definire la <STRONG>httpsPort</STRONG> come <STRONG>443</STRONG> e la <STRONG>httpport</STRONG> come porta <STRONG>80</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-229">In step 7, you define the <STRONG>httpsPort</STRONG> as <STRONG>443</STRONG> and the <STRONG>httpPort</STRONG> as port <STRONG>80</STRONG>.</span></span> <span data-ttu-id="6e5cc-230">Tutte le altre impostazioni di configurazione sono uguali.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-230">All other configuration settings are the same.</span></span>

        
        </div>

13. <span data-ttu-id="6e5cc-231">Sul lato sinistro della console, fare clic sul nome del server IIS.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-231">On the left-hand side of the console, click the IIS server name.</span></span> <span data-ttu-id="6e5cc-232">Al centro della console, individuare la **riscrittura degli URL** in **IIS**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-232">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="6e5cc-233">Fare doppio clic su URL Rewrite per aprire la configurazione delle regole di riscrittura degli URL.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-233">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span> <span data-ttu-id="6e5cc-234">È necessario visualizzare le regole per ogni server farm creata nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-234">You should see rules for each Server Farm that you created in the previous steps.</span></span> <span data-ttu-id="6e5cc-235">In caso contrario, verificare di aver fatto clic sul nome del **server IIS** subito sotto il nodo **pagina iniziale** nella console di Internet Information Server Manager.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-235">If you do not, confirm that you clicked on the **IIS Server** name immediately below the **Start Page** node in the Internet Information Server Manager console.</span></span>

14. <span data-ttu-id="6e5cc-236">Nella finestra di dialogo di **riscrittura degli URL** , usando webext.contoso.com come esempio, il nome completo della regola come visualizzato **è\_arr\_webext.contoso.com\_loadbalance SSL**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-236">In the **URL Rewrite** dialog, using webext.contoso.com as an example, the full name of the rule as displayed is **ARR\_webext.contoso.com\_loadbalance\_SSL**.</span></span>
    
      - <span data-ttu-id="6e5cc-237">Fare doppio clic sulla regola per aprire la finestra di dialogo **Modifica regola in ingresso** .</span><span class="sxs-lookup"><span data-stu-id="6e5cc-237">Double-click the rule to open the **Edit Inbound Rule** dialog.</span></span>
    
      - <span data-ttu-id="6e5cc-238">Fare clic su **Aggiungi...**</span><span class="sxs-lookup"><span data-stu-id="6e5cc-238">Click **Add…**</span></span> <span data-ttu-id="6e5cc-239">nella finestra di dialogo **condizioni** .</span><span class="sxs-lookup"><span data-stu-id="6e5cc-239">on the **Conditions** dialog.</span></span>
    
      - <span data-ttu-id="6e5cc-240">Nella condizione **Add** nella **condizione input:** type **{http\_host}**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-240">On the **Add Condition** in **Condition input:** type **{HTTP\_HOST}**.</span></span> <span data-ttu-id="6e5cc-241">(Durante la digitazione, viene visualizzata una finestra di dialogo che consente di selezionare la condizione).</span><span class="sxs-lookup"><span data-stu-id="6e5cc-241">(As you type, a dialog appears that will let you select the condition).</span></span> <span data-ttu-id="6e5cc-242">in **Controlla se stringa di input:** seleziona **corrisponde al motivo**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-242">under **Check if input string:** select **Matches the Pattern**.</span></span> <span data-ttu-id="6e5cc-243">Nel tipo \*\*\*\* **\*** di input del modello.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-243">In the **Pattern input** type **\***.</span></span> <span data-ttu-id="6e5cc-244">L'opzione **Ignora caso** deve essere selezionata.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-244">**Ignore case** should be selected.</span></span> <span data-ttu-id="6e5cc-245">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-245">Click **OK**.</span></span>
    
      - <span data-ttu-id="6e5cc-246">Scorrere verso il basso nella finestra di dialogo **Modifica regola in ingresso** per individuare la finestra di dialogo **azione** .</span><span class="sxs-lookup"><span data-stu-id="6e5cc-246">Scroll down in the **Edit Inbound Rule** dialog to locate the **Action** dialog.</span></span> <span data-ttu-id="6e5cc-247">**Tipo di azione:** deve essere impostato su **route to server farm**, **Scheme:** impostare su **https://**, **server farm:** impostare l'URL a cui è applicata la regola.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-247">**Action Type:** should be set to **Route to Server Farm**, **Scheme:** set to **https://**, **Server farm:** set to the URL that this rule applies to.</span></span> <span data-ttu-id="6e5cc-248">Per questo esempio, questa impostazione deve essere impostata su **webext.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-248">For this example, this should be set to **webext.contoso.com**.</span></span> <span data-ttu-id="6e5cc-249">**Percorso:** è impostato su **/{R: 0}**</span><span class="sxs-lookup"><span data-stu-id="6e5cc-249">**Path:** is set to **/{R:0}**</span></span>
    
      - <span data-ttu-id="6e5cc-250">Fare clic su **applica** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-250">Click **Apply** to save your changes.</span></span> <span data-ttu-id="6e5cc-251">Fare clic su **back to Rules** to return to the URL Rewrite rules.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-251">Click **Back to Rules** to return to the URL Rewrite rules.</span></span>

15. <span data-ttu-id="6e5cc-252">Ripetere la procedura definita nel passaggio 14 per ognuna delle regole di riscrittura SSL definite, una per ogni URL della server farm.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-252">Repeat the procedure defined in Step 14 for each of the SSL rewrite rules that you have defined, one per Server Farm URL.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="6e5cc-253">Per impostazione predefinita, vengono create anche le regole HTTP e sono denotate dalla denominazione simile alle regole SSL.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-253">By default, HTTP rules are created as well and are denoted by the similar naming to the SSL rules.</span></span> <span data-ttu-id="6e5cc-254">Per l'esempio corrente, la regola HTTP verrebbe denominata <STRONG>ARR_webext. contoso. com_loadbalance</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-254">For our current example, the HTTP rule would be named <STRONG>ARR_webext.contoso.com_loadbalance</STRONG>.</span></span> <span data-ttu-id="6e5cc-255">Per queste regole non sono necessarie modifiche e possono essere ignorate in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-255">No modifications are needed to these rules and they can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a><span data-ttu-id="6e5cc-256">Per modificare le proprietà della regola di pubblicazione Web in TMG 2010</span><span class="sxs-lookup"><span data-stu-id="6e5cc-256">To modify the properties of the web publishing rule in TMG 2010</span></span>

1.  <span data-ttu-id="6e5cc-257">Fare clic sul pulsante **Start**, scegliere **programmi**, **Microsoft Forefront TMG**e quindi fare clic su **gestione Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-257">Click **Start**, point to **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="6e5cc-258">Nel riquadro sinistro espandere **NomeServer** e quindi fare clic su **Criterio firewall**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-258">In the left pane, expand **ServerName**, and then click **Firewall Policy**.</span></span>

3.  <span data-ttu-id="6e5cc-259">Nel riquadro dei dettagli fare clic con il pulsante destro del mouse sulla regola di pubblicazione server Web creata nella procedura precedente, ad esempio RegolaEsternaLyncServer e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-259">In the details pane, right-click the web server publishing rule that you created in the previous procedure (for example, LyncServerExternalRule), and then click **Properties**.</span></span>

4.  <span data-ttu-id="6e5cc-260">Nella scheda **Da** della pagina **Proprietà** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6e5cc-260">On the **Properties** page, on the **From** tab, do the following:</span></span>
    
      - <span data-ttu-id="6e5cc-261">Nell'elenco **Questa regola si applica al traffico prodotto dalle seguenti origini** fare clic su **Ovunque** e quindi su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-261">In the **This rule applies to traffic from these sources** list, click **Anywhere**, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="6e5cc-262">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-262">Click **Add**.</span></span>
    
      - <span data-ttu-id="6e5cc-263">In **Aggiungi entità di rete** espandere **Reti**, fare clic su **Esterno**, **Aggiungi** e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-263">In **Add Network Entities**, expand **Networks**, click **External**, click **Add**, and then click **Close**.</span></span>

5.  <span data-ttu-id="6e5cc-264">Nella scheda **Per** verificare che la casella di controllo **Inoltra l'intestazione host originale e non quella effettiva** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-264">On the **To** tab, ensure that the **Forward the original host header instead of the actual one** check box is selected.</span></span>

6.  <span data-ttu-id="6e5cc-265">Nella scheda **Bridging** selezionare la casella di controllo **Reindirizza richiesta a porta SSL** e quindi specificare la porta **4443**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-265">On the **Bridging** tab, select the **Redirect request to SSL port** check box, and then specify port **4443**.</span></span>

7.  <span data-ttu-id="6e5cc-266">Nella scheda **Nome pubblico** aggiungere gli URL semplici, ad esempio meet.contoso.com e dialin.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-266">On the **Public Name** tab, add the simple URLs (for example, meet.contoso.com and dialin.contoso.com).</span></span>

8.  <span data-ttu-id="6e5cc-267">Fare clic su **Applica** per salvare le modifiche e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-267">Click **Apply** to save changes, and then click **OK**.</span></span>

9.  <span data-ttu-id="6e5cc-268">Nel riquadro dei dettagli fare clic su **Applica** per salvare le modifiche e aggiornare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-268">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a><span data-ttu-id="6e5cc-269">Per modificare le proprietà della regola di pubblicazione Web in IIS ARR</span><span class="sxs-lookup"><span data-stu-id="6e5cc-269">To modify the properties of the web publishing rule in IIS ARR</span></span>

1.  <span data-ttu-id="6e5cc-270">Fare clic sul pulsante **Start**, scegliere **programmi**, **strumenti di amministrazione**e quindi fare clic su **Gestione Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-270">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="6e5cc-271">Sul lato sinistro della console, fare clic sul nome del server IIS.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-271">On the left-hand side of the console, click the IIS server name.</span></span>

3.  <span data-ttu-id="6e5cc-272">Al centro della console, individuare la **riscrittura degli URL** in **IIS**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-272">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="6e5cc-273">Fare doppio clic su URL Rewrite per aprire la configurazione delle regole di riscrittura degli URL.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-273">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span>

4.  <span data-ttu-id="6e5cc-274">Fare doppio clic sulla regola che è necessario modificare.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-274">Double-click the rule that you need to modify.</span></span> <span data-ttu-id="6e5cc-275">Apportare le modifiche apportate, in base alle esigenze, in **URL**, **condizioni**, **variabili server** o **azione**.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-275">Make your modifications, as needed, in **Match URL**, **Conditions**, **Server Variables** or **Action**.</span></span>

5.  <span data-ttu-id="6e5cc-276">Fare clic su **applica** per eseguire il commit delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-276">Click **Apply** to commit your changes.</span></span> <span data-ttu-id="6e5cc-277">Fare clic su **Torna alle regole** per modificare altre regole o chiudere la console di **Gestione IIS** se si ha a che fare con le modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="6e5cc-277">Click **Back to Rules** to modify other rules, or close the **IIS Manager** console if you are done with your changes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

