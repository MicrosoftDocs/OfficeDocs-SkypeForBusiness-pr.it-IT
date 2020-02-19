---
title: 'Lync Server 2013: configurare i certificati nel server che esegue la messaggistica unificata di Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bf3e665e0031596bc2db2273882aef379a96f2e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a><span data-ttu-id="79704-102">Configurare i certificati nel server che esegue la messaggistica unificata di Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="79704-102">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79704-103">_**Ultimo argomento modificato:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="79704-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="79704-104">Se la messaggistica unificata di Exchange è stata distribuita, come descritto in [pianificazione dell'integrazione della messaggistica unificata di Exchange in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) nella documentazione relativa alla pianificazione e si desidera fornire le funzionalità di messaggistica unificata di Exchange agli utenti di VoIP aziendale nell'organizzazione, è possibile utilizzare le procedure seguenti per configurare il certificato sul server che esegue la messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="79704-104">If you have deployed Exchange Unified Messaging (UM), as described in [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="79704-105">Per i certificati interni, entrambi i server che eseguono Lync Server 2013 e i server che eseguono Microsoft Exchange devono disporre di certificati autorità radice attendibili che sono mutuamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="79704-105">For internal certificates, both the servers running Lync Server 2013 and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="79704-106">L'autorità di certificazione (CA) può essere la stessa o un'autorità di certificazione diversa, purché i server dispongano del certificato radice dell'autorità di certificazione registrata nell'archivio certificati dell'autorità radice attendibile.</span><span class="sxs-lookup"><span data-stu-id="79704-106">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span>



</div>

<span data-ttu-id="79704-107">Il server di Exchange deve essere configurato con un certificato server per la connessione a Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="79704-107">The Exchange Server must be configured with a server certificate in order to connect to Lync Server 2013:</span></span>

1.  <span data-ttu-id="79704-108">Scaricare il certificato CA per Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="79704-108">Download the CA certificate for the Exchange Server.</span></span>

2.  <span data-ttu-id="79704-109">Installare il certificato CA per Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="79704-109">Install the CA certificate for the Exchange Server.</span></span>

3.  <span data-ttu-id="79704-110">Verificare che la CA sia inclusa nell'elenco delle CA radice attendibili di Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="79704-110">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>

4.  <span data-ttu-id="79704-111">Creare una richiesta di certificato per Exchange Server e installare il certificato.</span><span class="sxs-lookup"><span data-stu-id="79704-111">Create a certificate request for the Exchange Server and install the certificate.</span></span>

5.  <span data-ttu-id="79704-112">Assegnare il certificato per Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="79704-112">Assign the certificate for the Exchange Server.</span></span>

<div>

## <a name="to-download-the-ca-certificate"></a><span data-ttu-id="79704-113">Per scaricare il certificato CA</span><span class="sxs-lookup"><span data-stu-id="79704-113">To download the CA certificate</span></span>

1.  <span data-ttu-id="79704-114">Nel server che esegue la messaggistica unificata di Exchange, fare clic sul pulsante **Start**, scegliere **esegui**, digitare **\<http://\>nome del server CA emittente/certsrv**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="79704-114">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="79704-115">In **Selezionare un'attività** fare clic su **Scarica un certificato CA, la catena di certificati o un CRL**.</span><span class="sxs-lookup"><span data-stu-id="79704-115">Under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

3.  <span data-ttu-id="79704-116">In **Scarica un certificato CA, una catena di certificati o un CRL selezionare il** **metodo di codifica su base 64**e quindi fare clic su **Scarica certificato CA**.</span><span class="sxs-lookup"><span data-stu-id="79704-116">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="79704-117">È inoltre possibile specificare la codifica DER (Distinguished Encoding Rules) in questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="79704-117">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="79704-118">Se si seleziona la codifica DER, il tipo di file nel prossimo passaggio e nel passaggio 10 di <STRONG>Per installare il certificato CA</STRONG> è .p7b anziché .cer.</span><span class="sxs-lookup"><span data-stu-id="79704-118">If you select DER encoding, the file type in the next step of this procedure and in step 10 of <STRONG>To Install the CA certificate</STRONG> is .p7b rather than .cer.</span></span>

    
    </div>

4.  <span data-ttu-id="79704-p103">Nella finestra di dialogo **Download file** fare clic su **Salva** e quindi salvare il file nel disco rigido del server. Il file avrà estensione cer o p7b, a seconda della codifica selezionata nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="79704-p103">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

</div>

<div>

## <a name="to-install-the-ca-certificate"></a><span data-ttu-id="79704-121">Per installare il certificato CA</span><span class="sxs-lookup"><span data-stu-id="79704-121">To install the CA certificate</span></span>

1.  <span data-ttu-id="79704-122">Nel server che esegue la messaggistica unificata di Exchange, aprire Microsoft Management Console (MMC) facendo clic sul pulsante **Start**, scegliendo **Esegui**, digitando **MMC** nella casella **Apri** e quindi facendo clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="79704-122">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="79704-123">Scegliere **Aggiungi/Rimuovi snap-in** dal menu **File** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="79704-123">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="79704-124">Nella casella **Aggiungi snap-in autonomo** fare clic su **Certificati** e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="79704-124">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="79704-125">Nella finestra di dialogo **Snap-in certificati** fare clic su **Account del computer** e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="79704-125">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="79704-126">Nella finestra di dialogo **Seleziona computer** verificare che sia selezionata la casella di controllo computer **locale (il computer su cui è in esecuzione questa console)** e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="79704-126">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="79704-127">Fare clic su **Chiudi** e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="79704-127">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="79704-128">Nell'albero della console espandere **Certificati (computer locale)**, espandere **Autorità di certificazione radice attendibili** e quindi fare clic su **Certificati**.</span><span class="sxs-lookup"><span data-stu-id="79704-128">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

8.  <span data-ttu-id="79704-129">Fare clic con il pulsante destro del mouse su **Certificati**, scegliere **Tutte le attività** e quindi **Importa**.</span><span class="sxs-lookup"><span data-stu-id="79704-129">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>

9.  <span data-ttu-id="79704-130">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="79704-130">Click **Next**.</span></span>

10. <span data-ttu-id="79704-p104">Fare clic su **Sfoglia** per individuare il file e quindi fare clic su **Avanti**. Il file avrà estensione cer o p7b, a seconda della codifica selezionata nel passaggio 3 di **Per scaricare il certificato CA**.</span><span class="sxs-lookup"><span data-stu-id="79704-p104">Click **Browse** to locate the file, and then click **Next**. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>

11. <span data-ttu-id="79704-133">Fare clic su **Mettere tutti i certificati nel seguente archivio**.</span><span class="sxs-lookup"><span data-stu-id="79704-133">Click **Place All Certificates in the following store**.</span></span>

12. <span data-ttu-id="79704-134">Fare clic su **Sfoglia** e quindi selezionare **Autorità di certificazione radice attendibili**.</span><span class="sxs-lookup"><span data-stu-id="79704-134">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span>

13. <span data-ttu-id="79704-135">Fare clic su **Avanti** per verificare le impostazioni e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="79704-135">Click **Next** to verify the settings, and then click **Finish**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a><span data-ttu-id="79704-136">Per verificare che la CA sia inclusa nell'elenco delle CA radice attendibili</span><span class="sxs-lookup"><span data-stu-id="79704-136">To verify that the CA is in the list of trusted root CAs</span></span>

1.  <span data-ttu-id="79704-137">Nel server che esegue la messaggistica unificata di Exchange, in MMC espandere **certificati (computer locale)**, espandere **autorità di certificazione radice attendibili**e quindi fare clic su **certificati**.</span><span class="sxs-lookup"><span data-stu-id="79704-137">On the server running Exchange UM, in MMC expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

2.  <span data-ttu-id="79704-138">Nel riquadro dei dettagli verificare che la CA sia inclusa nell'elenco delle CA attendibili.</span><span class="sxs-lookup"><span data-stu-id="79704-138">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a><span data-ttu-id="79704-139">Per configurare la messaggistica unificata di Exchange Server 2013 con Lync Server</span><span class="sxs-lookup"><span data-stu-id="79704-139">To configure Exchange Server 2013 UM with Lync Server</span></span>

1.  <span data-ttu-id="79704-140">Per informazioni dettagliate, vedere la sezione relativa alla messaggistica unificata di Exchange 2013 con Lync Server nella [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372)documentazione di Exchange Server all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="79704-140">For details, see "Integrate Exchange 2013 UM with Lync Server" in the Exchange Server documentation at [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="79704-141">Per creare una richiesta di certificato e installare il certificato in Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="79704-141">To create a certificate request and install the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="79704-142">Nel server che esegue la messaggistica unificata di Exchange, fare clic sul pulsante **Start**, scegliere **Esegui**, digitare **\<http://** nome del server**\>** CA emittente/certsrv e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="79704-142">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<** name of your Issuing CA Server**\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="79704-143">In **Selezionare un'attività** fare clic su **Richiedi un certificato**.</span><span class="sxs-lookup"><span data-stu-id="79704-143">Under **Select a task**, click **Request a Certificate**.</span></span>

3.  <span data-ttu-id="79704-144">In **Richiedi un certificato** fare clic su **Richiesta avanzata di certificati**.</span><span class="sxs-lookup"><span data-stu-id="79704-144">Under **Request a Certificate**, click **Advanced certificate request**.</span></span>

4.  <span data-ttu-id="79704-145">In **Richiesta avanzata certificati** fare clic su **Creare e inviare una richiesta a questa CA**.</span><span class="sxs-lookup"><span data-stu-id="79704-145">Under **Advanced Certificate Request**, click **Create and submit a request to this CA**.</span></span>

5.  <span data-ttu-id="79704-146">In **Richiesta avanzata di certificati** selezionare **Server Web** o un altro modello di certificato server configurato per l'autenticazione server.</span><span class="sxs-lookup"><span data-stu-id="79704-146">Under **Advanced Certificate Request**, select **Web server** or another server certificate template configured for server authentication.</span></span>

6.  <span data-ttu-id="79704-147">In **informazioni di identificazione per modello**non in linea, nella casella **nome** digitare il nome di dominio completo (FQDN) del server Exchange.</span><span class="sxs-lookup"><span data-stu-id="79704-147">Under **Identifying Information for Offline Template**, in the **Name** box, type the fully qualified domain name (FQDN) of the Exchange Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="79704-148">È necessario immettere l'FQDN di Exchange Server per garantire il funzionamento delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="79704-148">You must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

7.  <span data-ttu-id="79704-149">In **Opzioni chiave** selezionare la casella di controllo **Archivia certificato nell'archivio certificati del computer locale**.</span><span class="sxs-lookup"><span data-stu-id="79704-149">Under **Key Options**, click the **Store certificate in the local computer certificate store** check box.</span></span>

8.  <span data-ttu-id="79704-150">Fare clic sul pulsante **Invia** nella parte inferiore della pagina Web.</span><span class="sxs-lookup"><span data-stu-id="79704-150">Click the **Submit** button in the bottom of the webpage.</span></span>

9.  <span data-ttu-id="79704-151">Nella finestra di dialogo visualizzata in cui viene richiesto di confermare l'operazione, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="79704-151">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

10. <span data-ttu-id="79704-152">Nella pagina Certificato emesso fare clic su **Installa questo certificato** in **Certificato emesso**.</span><span class="sxs-lookup"><span data-stu-id="79704-152">On the Certificate Issued page, under **Certificate Issued**, click **Install this certificate**.</span></span>

11. <span data-ttu-id="79704-153">Nella finestra di dialogo visualizzata in cui viene richiesto di confermare l'operazione, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="79704-153">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

12. <span data-ttu-id="79704-154">Verificare che venga visualizzato il messaggio indicante il completamento dell'installazione del nuovo certificato.</span><span class="sxs-lookup"><span data-stu-id="79704-154">Verify that the message "Your new certificate has been successfully installed" appears.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a><span data-ttu-id="79704-155">Per creare un certificato in Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="79704-155">To create a certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="79704-156">Accedere al server che esegue la messaggistica unificata di Exchange con diritti utente adeguati.</span><span class="sxs-lookup"><span data-stu-id="79704-156">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="79704-157">Per informazioni dettagliate, vedere "autorizzazioni di accesso client [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499)" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="79704-157">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="79704-158">Per creare il certificato, fare riferimento alle procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="79704-158">Refer to the following procedures to create the certificate:</span></span>
    
    1.  <span data-ttu-id="79704-159">"Creare un nuovo certificato di Exchange" all'indirizzo[https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span><span class="sxs-lookup"><span data-stu-id="79704-159">"Create a New Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span></span>
    
    2.  <span data-ttu-id="79704-160">"Importazione di un certificato di Exchange" all'indirizzo[https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span><span class="sxs-lookup"><span data-stu-id="79704-160">"Import an Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="79704-161">Per l'opzione <STRONG>Nome soggetto</STRONG> del certificato, è necessario immettere l'FQDN di Exchange Server per garantire il funzionamento delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="79704-161">For the certificate <STRONG>Subject Name</STRONG>, you must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="79704-162">Per assegnare il certificato in Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="79704-162">To assign the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="79704-163">Nel server che esegue la messaggistica unificata di Exchange, aprire MMC.</span><span class="sxs-lookup"><span data-stu-id="79704-163">On the server running Exchange UM, open MMC.</span></span>

2.  <span data-ttu-id="79704-164">Nell'albero della console espandere **Personale** e quindi fare clic su **Certificati**.</span><span class="sxs-lookup"><span data-stu-id="79704-164">In the console tree, expand **Personal** and then click **Certificates**.</span></span>

3.  <span data-ttu-id="79704-165">Nel riquadro dei dettagli verificare che il certificato personale sia visualizzato.</span><span class="sxs-lookup"><span data-stu-id="79704-165">In the details pane, verify that personal certificate is displayed.</span></span>

4.  <span data-ttu-id="79704-166">Fare doppio clic sul certificato per leggere i dettagli e verificare che sia valido.</span><span class="sxs-lookup"><span data-stu-id="79704-166">Double-click the certificate to read its details and verify that it is valid.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="79704-167">Prima che il certificato venga visualizzato come valido potrebbero essere necessari alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="79704-167">It may take a few minutes before the certificate displays as valid.</span></span>

    
    </div>

5.  <span data-ttu-id="79704-168">Riavviare il servizio di messaggistica unificata di Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="79704-168">Restart the Microsoft Exchange Unified Messaging service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="79704-169">Il certificato corretto viene automaticamente recuperato dal server che esegue la messaggistica unificata di Exchange Server 2007 SP1.</span><span class="sxs-lookup"><span data-stu-id="79704-169">The server running Exchange Server 2007 SP1 Unified Messaging automatically retrieves the correct certificate.</span></span>

    
    </div>

6.  <span data-ttu-id="79704-170">Aprire il Visualizzatore eventi e cercare l'ID evento 1112, che specifica il certificato recuperato dal server che esegue la messaggistica unificata di Exchange Server 2007 SP1.</span><span class="sxs-lookup"><span data-stu-id="79704-170">Open Event Viewer and look for Event ID 1112, which specifies what certificate the server running Exchange Server 2007 SP1 Unified Messaging has retrieved.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a><span data-ttu-id="79704-171">Per assegnare il certificato in Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="79704-171">To assign the certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="79704-172">Accedere al server che esegue la messaggistica unificata di Exchange con diritti utente adeguati.</span><span class="sxs-lookup"><span data-stu-id="79704-172">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="79704-173">Per informazioni dettagliate, vedere "autorizzazioni di accesso client [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499)" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="79704-173">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="79704-174">Per la procedura per assegnare il certificato, vedere la sezione "assegnare servizi a un certificato [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497)" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="79704-174">For the procedure to assign the certificate, see "Assign Services to a Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

