---
title: 'Lync Server 2013: Configurare i certificati per i server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 303724fa705fa94e9bbacacb4764bba7b918c460
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a><span data-ttu-id="17e0e-102">Configurare i certificati per i server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17e0e-102">Configure certificates for servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17e0e-103">_**Argomento Ultima modifica:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="17e0e-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="17e0e-104">Per completare correttamente questa procedura, è necessario avere effettuato l'accesso come utente membro del gruppo RTCUniversalServerAdmins o avere le autorizzazioni corrette Delegate.</span><span class="sxs-lookup"><span data-stu-id="17e0e-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="17e0e-105">Per informazioni dettagliate sulla delega delle autorizzazioni, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="17e0e-105">For details about delegating permissions, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="17e0e-106">A seconda dell'organizzazione e dei requisiti per richiedere i certificati, è possibile che siano necessarie altre appartenenze ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="17e0e-106">Depending on your organization and requirements for requesting certificates, you may require other group memberships.</span></span> <span data-ttu-id="17e0e-107">Consultarsi con il gruppo che gestisce l'autorità di certificazione (PKI) dell'infrastruttura a chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="17e0e-107">Consult with the group that manages your public key infrastructure (PKI) certification authority (CA).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17e0e-108">Lync Server 2013 include il supporto per la famiglia SHA-2 (SHA-2 usa le lunghezze digest di 224, 256, 384 o 512 bit) dell'hash digest e gli algoritmi di firma per le connessioni dei client che usano Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista o Sistemi operativi Windows XP, oltre a Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="17e0e-108">Lync Server 2013 includes support for the SHA-2 suite (SHA-2 uses digest lengths of 224, 256, 384 or 512 bits) of digest hash and signing algorithms for connections from clients running the Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista, or Windows XP operating systems, in addition to Lync Phone Edition.</span></span> <span data-ttu-id="17e0e-109">Per supportare l'accesso esterno tramite la famiglia SHA-2, il certificato esterno viene emesso da un'autorità di certificazione pubblica che può anche emettere un certificato con lo stesso bit length digest.</span><span class="sxs-lookup"><span data-stu-id="17e0e-109">To support external access using the SHA-2 suite, the external certificate is issued by a public CA that also can issue a certificate with the same bit length digest.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="17e0e-110">La selezione dell'algoritmo di firma e del digest hash dipende dai client e dai server che utilizzeranno il certificato e da altri computer e dispositivi che i client e i server comunicheranno con chi deve anche sapere come usare gli algoritmi usati nella certificato.</span><span class="sxs-lookup"><span data-stu-id="17e0e-110">The selection of which hash digest and signing algorithm is dependent on the clients and the servers that will use the certificate, and other computers and devices that clients and servers will communicate with who must also know how to use the algorithms used in the certificate.</span></span> <span data-ttu-id="17e0e-111">Per informazioni sulle lunghezze del digest supportate nel sistema operativo e in alcune applicazioni client, vedere<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>.</span><span class="sxs-lookup"><span data-stu-id="17e0e-111">For information on which digest lengths are supported in the operating system and some client applications, see<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>.</span></span>



</div>

<span data-ttu-id="17e0e-112">Ogni server Standard Edition o front end server richiede fino a quattro certificati: il certificato oAuthTokenIssuer, un certificato predefinito, un certificato interno Web e un certificato esterno Web.</span><span class="sxs-lookup"><span data-stu-id="17e0e-112">Each Standard Edition server or Front End Server requires up to four certificates: the oAuthTokenIssuer certificate, a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="17e0e-113">Tuttavia, è possibile richiedere e assegnare un singolo certificato predefinito con le voci di nome alternativo soggetto appropriato e il certificato oAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="17e0e-113">However, it is possible to request and assign a single default certificate with appropriate subject alternative name entries as well as the oAuthTokenIssuer certificate.</span></span> <span data-ttu-id="17e0e-114">Per informazioni dettagliate sui requisiti dei certificati, vedere [requisiti per i certificati per i server interni in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span><span class="sxs-lookup"><span data-stu-id="17e0e-114">For details about the certificate requirements, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span></span> <span data-ttu-id="17e0e-115">Per informazioni dettagliate sulla richiesta, l'assegnazione e l'installazione del certificato oAuthTokenIssuer, vedere [gestione dell'autenticazione server-Server (OAuth) e delle applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="17e0e-115">For details about requesting, assigning and installing the oAuthTokenIssuer certificate, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

<span data-ttu-id="17e0e-116">Usare la procedura seguente per richiedere, assegnare e installare il server Standard Edition o i certificati del server front-end.</span><span class="sxs-lookup"><span data-stu-id="17e0e-116">Use the following procedure to request, assign, and install the Standard Edition server or Front End Server certificates.</span></span> <span data-ttu-id="17e0e-117">Ripetere la procedura per ogni server front-end.</span><span class="sxs-lookup"><span data-stu-id="17e0e-117">Repeat the procedure for each Front End Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="17e0e-118">La procedura seguente descrive come configurare i certificati da una PKI aziendale interna distribuita dall'organizzazione e con l'elaborazione delle richieste offline.</span><span class="sxs-lookup"><span data-stu-id="17e0e-118">The following procedure describes how to configure certificates from an internal enterprise PKI deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="17e0e-119">Per informazioni su come ottenere certificati da una CA pubblica, vedere <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">requisiti dei certificati per i server interni in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="17e0e-119">For information about obtaining certificates from a public CA, see <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate requirements for internal servers in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="17e0e-120">Questa procedura descrive inoltre come richiedere, assegnare e installare i certificati durante la configurazione del server front-end.</span><span class="sxs-lookup"><span data-stu-id="17e0e-120">Also, this procedure describes how to request, assign, and install certificates during set up of the Front End Server.</span></span> <span data-ttu-id="17e0e-121">Se i certificati sono stati richiesti in anticipo, come descritto nella sezione <A href="lync-server-2013-request-certificates-in-advance-optional.md">richieste di certificati in anticipo (facoltativo) per Lync Server 2013</A> di questa documentazione di distribuzione oppure non si usa una PKI aziendale interna distribuita nell'organizzazione per ottenere i certificati, è necessario modificare questa procedura in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="17e0e-121">If you requested certificates in advance, as described in the <A href="lync-server-2013-request-certificates-in-advance-optional.md">Request certificates in advance (optional) for Lync Server 2013</A> section of this Deployment documentation, or you do not use an internal enterprise PKI deployed in your organization to obtain certificates, you must modify this procedure as appropriate.</span></span>



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a><span data-ttu-id="17e0e-122">Per configurare i certificati per un server front-end</span><span class="sxs-lookup"><span data-stu-id="17e0e-122">To configure certificates for a Front End Server</span></span>

1.  <span data-ttu-id="17e0e-123">Nella distribuzione guidata di Lync Server fare clic su **Esegui** accanto al **passaggio 3: richiedere, installare o assegnare certificati**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-123">In the Lync Server Deployment Wizard, click **Run** next to **Step 3: Request, Install or Assign Certificates**.</span></span>

2.  <span data-ttu-id="17e0e-124">Nella pagina **creazione guidata certificato** fare clic su **Richiedi**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-124">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="17e0e-125">Nella pagina **richiesta certificato** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-125">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="17e0e-126">Nella pagina **richieste immediate o posticipate** è possibile accettare l'impostazione predefinita **Invia immediatamente la richiesta a un'autorità di certificazione online** facendo clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-126">On the **Delayed or Immediate Requests** page, you can accept the default **Send the request immediately to an online certification authority** option by clicking **Next**.</span></span> <span data-ttu-id="17e0e-127">La CA interna con registrazione automatica online deve essere disponibile se si seleziona questa opzione.</span><span class="sxs-lookup"><span data-stu-id="17e0e-127">The internal CA with automatic online enrollment must be available if you select this option.</span></span> <span data-ttu-id="17e0e-128">Se si sceglie l'opzione per rinviare la richiesta, verrà chiesto di specificare un nome e un percorso per salvare il file di richiesta del certificato.</span><span class="sxs-lookup"><span data-stu-id="17e0e-128">If you choose the option to delay the request, you will be prompted for a name and location to save the certificate request file.</span></span> <span data-ttu-id="17e0e-129">La richiesta di certificato deve essere presentata ed elaborata da una CA all'interno dell'organizzazione o da una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="17e0e-129">The certificate request must be presented and processed by a CA either inside your organization, or by a public CA.</span></span> <span data-ttu-id="17e0e-130">Sarà quindi necessario importare la risposta del certificato e assegnarla al ruolo di certificato corretto.</span><span class="sxs-lookup"><span data-stu-id="17e0e-130">You will then need to import the certificate response and assign it to the proper certificate role.</span></span>

5.  <span data-ttu-id="17e0e-131">Nella pagina **scegliere una autorità di certificazione (CA)** selezionare l'opzione **Seleziona una CA dall'elenco rilevato nell'ambiente** e quindi selezionare una CA nota (tramite registrazione in servizi di dominio Active Directory) nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="17e0e-131">On the **Choose a Certificate Authority (CA)** page, select the **Select a CA from the list detected in your environment** option, and then select a known (through registration in Active Directory Domain Services) CA from the list.</span></span> <span data-ttu-id="17e0e-132">In alternativa, selezionare l'opzione **specifica un'altra autorità di certificazione** , immettere il nome di un'altra CA nella casella e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-132">Or, select the **Specify another certification authority** option, enter the name of another CA in the box, and then click **Next**.</span></span>

6.  <span data-ttu-id="17e0e-133">Nella pagina **account Authority Certificate** vengono chieste le credenziali per richiedere ed elaborare la richiesta di certificato presso la CA.</span><span class="sxs-lookup"><span data-stu-id="17e0e-133">On the **Certificate Authority Account** page, you are prompted for credentials to request and process the certificate request at the CA.</span></span> <span data-ttu-id="17e0e-134">Si sarebbe dovuto determinare se è necessario un nome utente e una password per richiedere un certificato in anticipo.</span><span class="sxs-lookup"><span data-stu-id="17e0e-134">You should have determined if a user name and password is necessary to request a certificate in advance.</span></span> <span data-ttu-id="17e0e-135">L'amministratore della CA avrà le informazioni necessarie e potrebbe essere necessario per assisterti in questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="17e0e-135">Your CA administrator will have the required information and may have to assist you in this step.</span></span> <span data-ttu-id="17e0e-136">Se è necessario fornire credenziali alternative, selezionare la casella di controllo, specificare un nome utente e una password nelle caselle di testo e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-136">If you need to supply alternate credentials, select the check box, provide a user name and password in the text boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="17e0e-137">Nella pagina **Specifica modello di certificato alternativo** , per usare il modello predefinito del server Web, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-137">On the **Specify Alternate Certificate Template** page, to use the default Web Server template, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="17e0e-138">Se l'organizzazione ha creato un modello da usare come alternativa per il modello di CA del server Web predefinito, selezionare la casella di controllo e quindi immettere il nome del modello alternativo.</span><span class="sxs-lookup"><span data-stu-id="17e0e-138">If your organization has created a template for use as an alternative for the default Web server CA template, select the check box, and then enter the name of the alternate template.</span></span> <span data-ttu-id="17e0e-139">Sarà necessario il nome del modello definito dall'amministratore della CA.</span><span class="sxs-lookup"><span data-stu-id="17e0e-139">You will need the template name as defined by the CA administrator.</span></span>

    
    </div>

8.  <span data-ttu-id="17e0e-140">Nella pagina **Impostazioni nome e sicurezza** specificare un **nome descrittivo** che consenta di identificare il certificato e lo scopo.</span><span class="sxs-lookup"><span data-stu-id="17e0e-140">On the **Name and Security Settings** page, specify a **Friendly Name** that should allow you to identify the certificate and purpose.</span></span> <span data-ttu-id="17e0e-141">Se si lascia vuoto, verrà generato automaticamente un nome.</span><span class="sxs-lookup"><span data-stu-id="17e0e-141">If you leave it blank, a name will be generated automatically.</span></span> <span data-ttu-id="17e0e-142">Impostare la **lunghezza del bit** della chiave o accettare l'impostazione predefinita di 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="17e0e-142">Set the **Bit length** of the key, or accept the default of 2048 bits.</span></span> <span data-ttu-id="17e0e-143">Selezionare il **contrassegno della chiave privata del certificato come esportabile** se si determina che il certificato e la chiave privata devono essere spostati o copiati in altri sistemi e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-143">Select the **Mark the certificate’s private key as exportable** if you determine that the certificate and private key needs to be moved or copied to other systems, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="17e0e-144">Lync Server 2013 offre requisiti minimi per una chiave privata esportabile.</span><span class="sxs-lookup"><span data-stu-id="17e0e-144">Lync Server 2013 has minimal requirements for an exportable private key.</span></span> <span data-ttu-id="17e0e-145">Una di queste posizioni si trova negli Edge Server in un pool, in cui il servizio di autenticazione dell'inoltro multimediale USA copie del certificato, invece dei singoli certificati per ogni istanza del pool.</span><span class="sxs-lookup"><span data-stu-id="17e0e-145">One such place is on the Edge Servers in a pool, where the Media Relay Authentication Service uses copies of the certificate, rather than individual certificates for each instance in the pool.</span></span>

    
    </div>

9.  <span data-ttu-id="17e0e-146">Nella pagina **informazioni organizzazione** facoltativamente specificare le informazioni sull'organizzazione e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-146">On the **Organization Information** page, optionally provide organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="17e0e-147">Nella pagina **informazioni geografiche** specificare facoltativamente informazioni geografiche e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-147">On the **Geographical Information** page, optionally provide geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="17e0e-148">Nella pagina **nome oggetto/nomi oggetto alternativo** esaminare i nomi alternativi oggetto che verranno aggiunti e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-148">On the **Subject Name / Subject Alternate Names** page, review the subject alternative names that will be added, and then click **Next**.</span></span>

12. <span data-ttu-id="17e0e-149">Nella pagina **Impostazioni dominio SIP** selezionare il **dominio SIP**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-149">On the **SIP Domain setting** page, select the **SIP Domain**, and then click **Next**.</span></span>

13. <span data-ttu-id="17e0e-150">Nella pagina **Configura altri nomi alternativi oggetto** aggiungere eventuali nomi alternativi di altri soggetti necessari, inclusi quelli eventualmente necessari per altri domini SIP in futuro e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-150">On the **Configure Additional Subject Alternate Names** page, add any additional required subject alternative names, including any that might be required for additional SIP domains in the future, and then click **Next**.</span></span>

14. <span data-ttu-id="17e0e-151">Nella pagina **Riepilogo richiesta di certificato** esaminare le informazioni nel riepilogo.</span><span class="sxs-lookup"><span data-stu-id="17e0e-151">On the **Certificate Request Summary** page, review the information in the summary.</span></span> <span data-ttu-id="17e0e-152">Se le informazioni sono corrette, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-152">If the information is correct, click **Next**.</span></span> <span data-ttu-id="17e0e-153">Se è necessario correggere o modificare un'impostazione, fare clic su **Torna** alla pagina appropriata per apportare la correzione o la modifica.</span><span class="sxs-lookup"><span data-stu-id="17e0e-153">If you need to correct or modify a setting, click **Back** to the proper page to make the correction or modification.</span></span>

15. <span data-ttu-id="17e0e-154">Nella pagina **esecuzione dei comandi** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-154">On the **Executing Commands** page, click **Next**.</span></span>

16. <span data-ttu-id="17e0e-155">Nella pagina di **stato della richiesta di certificato online** verificare le informazioni restituite.</span><span class="sxs-lookup"><span data-stu-id="17e0e-155">On the **Online Certificate Request Status** page, review the information returned.</span></span> <span data-ttu-id="17e0e-156">Tenere presente che il certificato è stato emesso e installato nell'archivio certificati locale.</span><span class="sxs-lookup"><span data-stu-id="17e0e-156">You should note that the certificate was issued and installed into the local certificate store.</span></span> <span data-ttu-id="17e0e-157">Se viene segnalato come rilasciato e installato, ma non è valido, verificare che il certificato radice della CA sia stato installato nell'archivio della CA radice attendibile del server.</span><span class="sxs-lookup"><span data-stu-id="17e0e-157">If it is reported as having been issued and installed, but is not valid, make sure that the CA root certificate has been installed in the server’s Trusted Root CA store.</span></span> <span data-ttu-id="17e0e-158">Vedere la documentazione della CA su come recuperare un certificato CA radice attendibile.</span><span class="sxs-lookup"><span data-stu-id="17e0e-158">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span></span> <span data-ttu-id="17e0e-159">Se è necessario visualizzare il certificato recuperato, fare clic su **Visualizza dettagli certificato**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-159">If you need to view the retrieved certificate, click **View Certificate Details**.</span></span> <span data-ttu-id="17e0e-160">Per impostazione predefinita, la casella di controllo **assegna il certificato agli usi dei certificati di Lync Server** è selezionata.</span><span class="sxs-lookup"><span data-stu-id="17e0e-160">By default, the check box for **Assign the certificate to Lync Server certificate usages** is checked.</span></span> <span data-ttu-id="17e0e-161">Se si vuole assegnare manualmente il certificato, deselezionare la casella di controllo e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-161">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span></span>

17. <span data-ttu-id="17e0e-162">Se è stata deselezionata la casella di controllo **assegna il certificato agli usi dei certificati di Lync Server** nella pagina precedente, verrà visualizzata la pagina **assegnazione certificato** .</span><span class="sxs-lookup"><span data-stu-id="17e0e-162">If you cleared the check box for **Assign the certificate to Lync Server certificate usages** on the previous page, you will be presented with the **Certificate Assignment** page.</span></span> <span data-ttu-id="17e0e-163">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-163">Click **Next**.</span></span>

18. <span data-ttu-id="17e0e-164">Nella pagina **archivio certificati** selezionare il certificato richiesto.</span><span class="sxs-lookup"><span data-stu-id="17e0e-164">On the **Certificate Store** page, select the certificate that you requested.</span></span> <span data-ttu-id="17e0e-165">Se si vuole visualizzare il certificato, fare clic su **Visualizza dettagli certificato**e quindi su **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="17e0e-165">If you want to view the certificate, click **View Certificate Details**, and then click **Next** to continue.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="17e0e-166">Se la pagina di <STRONG>stato della richiesta di certificato online</STRONG> segnala un problema con il certificato, ad esempio il certificato non è valido, la visualizzazione del certificato effettivo può aiutare a risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="17e0e-166">If the <STRONG>Online Certificate Request Status</STRONG> page reported an issue with the certificate, such as the certificate not being valid, viewing the actual certificate can assist in resolving the issue.</span></span> <span data-ttu-id="17e0e-167">Due problemi specifici che possono causare un certificato non valido sono il certificato della CA radice attendibile mancante menzionato in precedenza e una chiave privata mancante associata al certificato.</span><span class="sxs-lookup"><span data-stu-id="17e0e-167">Two specific issues that can cause a certificate to not be valid is the previously mentioned missing Trusted Root CA certificate, and a missing private key that is associated with the certificate.</span></span> <span data-ttu-id="17e0e-168">Fare riferimento alla documentazione della CA per risolvere questi due problemi.</span><span class="sxs-lookup"><span data-stu-id="17e0e-168">Refer to your CA documentation to resolve these two issues.</span></span>

    
    </div>

19. <span data-ttu-id="17e0e-169">Nella pagina **Riepilogo assegnazione certificati** esaminare le informazioni presentate per verificare che si tratta del certificato da assegnare e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-169">On the **Certificate Assignment Summary** page, review the information presented to make sure that this is the certificate that should be assigned, and then click **Next**.</span></span>

20. <span data-ttu-id="17e0e-170">Nella pagina **esecuzione dei comandi** esaminare l'output del comando.</span><span class="sxs-lookup"><span data-stu-id="17e0e-170">On the **Executing Commands** page, review the output of the command.</span></span> <span data-ttu-id="17e0e-171">Fare clic su **Visualizza log** se si vuole rivedere il processo di assegnazione o se è stato emesso un errore o un avviso.</span><span class="sxs-lookup"><span data-stu-id="17e0e-171">Click **View Log** if you want to review the assignment process or if there was an error or warning issued.</span></span> <span data-ttu-id="17e0e-172">Al termine della revisione, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-172">When you are finished with your review, click **Finish**.</span></span>

21. <span data-ttu-id="17e0e-173">Nella pagina **creazione guidata certificato** verificare che lo **stato** del certificato sia "assegnato", quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-173">On the **Certificate Wizard** page, verify that the **Status** of the certificate is “Assigned,” and then click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="17e0e-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17e0e-174">See Also</span></span>


[<span data-ttu-id="17e0e-175">Requisiti dell'infrastruttura dei certificati per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17e0e-175">Certificate infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

