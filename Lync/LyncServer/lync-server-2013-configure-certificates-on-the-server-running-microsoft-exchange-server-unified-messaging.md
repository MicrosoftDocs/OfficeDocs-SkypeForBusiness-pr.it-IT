---
title: 'Lync Server 2013: configurare i certificati nel server in cui è in uso la messaggistica unificata di Microsoft Exchange Server'
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
ms.openlocfilehash: 6d31ed8b750d0162a2c09d49ca8a350731896086
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a><span data-ttu-id="d59a2-102">Configurare i certificati nel server in cui è in uso la messaggistica unificata di Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="d59a2-102">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d59a2-103">_**Argomento Ultima modifica:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="d59a2-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="d59a2-104">Se è stata distribuita la messaggistica unificata di Exchange, come descritto in [pianificazione dell'integrazione della messaggistica unificata di Exchange in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) nella documentazione relativa alla pianificazione e si desidera specificare le caratteristiche di messaggistica unificata di Exchange per gli utenti di VoIP aziendale nell'organizzazione, è possibile usare le procedure seguenti per configurare il certificato nel server che usa la messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="d59a2-104">If you have deployed Exchange Unified Messaging (UM), as described in [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d59a2-105">Per i certificati interni, sia i server che esegue Lync Server 2013 che i server che esegue Microsoft Exchange devono avere certificati di autorità radice attendibili che sono mutuamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="d59a2-105">For internal certificates, both the servers running Lync Server 2013 and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="d59a2-106">L'autorità di certificazione (CA) può essere uguale o un'autorità di certificazione diversa, purché i server dispongano del certificato radice dell'autorità di certificazione registrato nell'archivio certificati dell'autorità radice attendibile.</span><span class="sxs-lookup"><span data-stu-id="d59a2-106">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span>



</div>

<span data-ttu-id="d59a2-107">Il server Exchange deve essere configurato con un certificato server per la connessione a Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="d59a2-107">The Exchange Server must be configured with a server certificate in order to connect to Lync Server 2013:</span></span>

1.  <span data-ttu-id="d59a2-108">Scaricare il certificato CA per il server Exchange.</span><span class="sxs-lookup"><span data-stu-id="d59a2-108">Download the CA certificate for the Exchange Server.</span></span>

2.  <span data-ttu-id="d59a2-109">Installare il certificato CA per il server Exchange.</span><span class="sxs-lookup"><span data-stu-id="d59a2-109">Install the CA certificate for the Exchange Server.</span></span>

3.  <span data-ttu-id="d59a2-110">Verificare che la CA si trovi nell'elenco delle autorità di certificazione radice attendibili del server Exchange.</span><span class="sxs-lookup"><span data-stu-id="d59a2-110">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>

4.  <span data-ttu-id="d59a2-111">Creare una richiesta di certificato per il server Exchange e installare il certificato.</span><span class="sxs-lookup"><span data-stu-id="d59a2-111">Create a certificate request for the Exchange Server and install the certificate.</span></span>

5.  <span data-ttu-id="d59a2-112">Assegnare il certificato per il server Exchange.</span><span class="sxs-lookup"><span data-stu-id="d59a2-112">Assign the certificate for the Exchange Server.</span></span>

<div>

## <a name="to-download-the-ca-certificate"></a><span data-ttu-id="d59a2-113">Per scaricare il certificato CA</span><span class="sxs-lookup"><span data-stu-id="d59a2-113">To download the CA certificate</span></span>

1.  <span data-ttu-id="d59a2-114">Nel server che esegue la messaggistica unificata di Exchange fare clic sul pulsante **Start**, scegliere **esegui**, digitare **http://\<nome\>del server della CA emittente/certsrv**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-114">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="d59a2-115">In **selezionare un'attività**fare clic su **Scarica un certificato CA, una catena di certificati o un CRL**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-115">Under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

3.  <span data-ttu-id="d59a2-116">In **scaricare un certificato CA, una catena di certificati o un CRL**selezionare **metodo di codifica per base 64**e quindi fare clic su **Scarica certificato CA**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-116">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d59a2-117">È anche possibile specificare la codifica DER (Distinguished Encoding Rules) in questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="d59a2-117">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="d59a2-118">Se si seleziona la codifica DER, il tipo di file nel passaggio successivo di questa procedura e nel passaggio 10 di <STRONG>per installare il certificato della CA</STRONG> è. p7b anziché. cer.</span><span class="sxs-lookup"><span data-stu-id="d59a2-118">If you select DER encoding, the file type in the next step of this procedure and in step 10 of <STRONG>To Install the CA certificate</STRONG> is .p7b rather than .cer.</span></span>

    
    </div>

4.  <span data-ttu-id="d59a2-119">Nella finestra di dialogo **Download file** fare clic su **Salva**e quindi salvare il file nel disco rigido nel server.</span><span class="sxs-lookup"><span data-stu-id="d59a2-119">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server.</span></span> <span data-ttu-id="d59a2-120">In base alla codifica selezionata nel passaggio precedente, il file includerà un file con estensione cer o. p7b.</span><span class="sxs-lookup"><span data-stu-id="d59a2-120">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

</div>

<div>

## <a name="to-install-the-ca-certificate"></a><span data-ttu-id="d59a2-121">Per installare il certificato CA</span><span class="sxs-lookup"><span data-stu-id="d59a2-121">To install the CA certificate</span></span>

1.  <span data-ttu-id="d59a2-122">Nel server che esegue la messaggistica unificata di Exchange aprire Microsoft Management Console (MMC) facendo clic sul pulsante **Start**, scegliendo **Esegui**, digitando **MMC** nella casella **Apri** e quindi facendo clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-122">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="d59a2-123">Nel menu **file** fare clic su **Aggiungi/Rimuovi snap-in**e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-123">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="d59a2-124">Nella casella **Add standalone snap-** in fare clic su **certificati**e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-124">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="d59a2-125">Nella finestra di dialogo di **snap-in certificato** fare clic su **account computer**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-125">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="d59a2-126">Nella finestra di dialogo **Seleziona computer** verificare che la casella di controllo computer **locale: (il computer in cui è in uso questa console)** sia selezionata e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-126">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="d59a2-127">Fare clic su **Chiudi**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-127">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="d59a2-128">Nell'albero della console espandere **certificati (computer locale)**, espandere **autorità di certificazione radice attendibili**e quindi fare clic su **certificati**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-128">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

8.  <span data-ttu-id="d59a2-129">Fare clic con il pulsante destro del mouse su **certificati**, scegliere **tutte le attività**e fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-129">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>

9.  <span data-ttu-id="d59a2-130">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-130">Click **Next**.</span></span>

10. <span data-ttu-id="d59a2-131">Fare clic su **Sfoglia** per individuare il file e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-131">Click **Browse** to locate the file, and then click **Next**.</span></span> <span data-ttu-id="d59a2-132">Il file includerà un'estensione cer o p7b, a seconda della codifica selezionata nel passaggio 3 di **per scaricare il certificato della CA**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-132">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>

11. <span data-ttu-id="d59a2-133">Fare clic su **Inserisci tutti i certificati nello Store seguente**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-133">Click **Place All Certificates in the following store**.</span></span>

12. <span data-ttu-id="d59a2-134">Fare clic su **Sfoglia**e quindi selezionare **autorità di certificazione radice attendibili**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-134">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span>

13. <span data-ttu-id="d59a2-135">Fare clic su **Avanti** per verificare le impostazioni e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-135">Click **Next** to verify the settings, and then click **Finish**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a><span data-ttu-id="d59a2-136">Per verificare che la CA si trovi nell'elenco delle autorità di certificazione radice attendibili</span><span class="sxs-lookup"><span data-stu-id="d59a2-136">To verify that the CA is in the list of trusted root CAs</span></span>

1.  <span data-ttu-id="d59a2-137">Nel server che gestisce la messaggistica unificata di Exchange, in MMC Espandi **certificati (computer locale)**, Espandi **autorità di certificazione radice attendibili**e quindi fai clic su **certificati**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-137">On the server running Exchange UM, in MMC expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

2.  <span data-ttu-id="d59a2-138">Nel riquadro dei dettagli verificare che la CA sia nell'elenco delle CA attendibili.</span><span class="sxs-lookup"><span data-stu-id="d59a2-138">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a><span data-ttu-id="d59a2-139">Per configurare la messaggistica unificata di Exchange Server 2013 con Lync Server</span><span class="sxs-lookup"><span data-stu-id="d59a2-139">To configure Exchange Server 2013 UM with Lync Server</span></span>

1.  <span data-ttu-id="d59a2-140">Per informazioni dettagliate, vedere "integrare la messaggistica unificata di Exchange 2013 con Lync Server" nella [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)documentazione di Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="d59a2-140">For details, see "Integrate Exchange 2013 UM with Lync Server" in the Exchange Server documentation at [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="d59a2-141">Per creare una richiesta di certificato e installare il certificato in Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="d59a2-141">To create a certificate request and install the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="d59a2-142">Nel server che esegue la messaggistica unificata di Exchange fare clic sul pulsante **Start**, scegliere **Esegui**, digitare **\<http://** nome del server**\>** della CA emittente/certsrv e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-142">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<** name of your Issuing CA Server**\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="d59a2-143">In **Seleziona un'attività**fare clic su **Richiedi un certificato**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-143">Under **Select a task**, click **Request a Certificate**.</span></span>

3.  <span data-ttu-id="d59a2-144">In **Richiedi un certificato**fare clic su **richiesta di certificato avanzata**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-144">Under **Request a Certificate**, click **Advanced certificate request**.</span></span>

4.  <span data-ttu-id="d59a2-145">In **richiesta di certificato avanzato**fare clic su **Crea e inviare una richiesta alla CA**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-145">Under **Advanced Certificate Request**, click **Create and submit a request to this CA**.</span></span>

5.  <span data-ttu-id="d59a2-146">In **richiesta di certificato avanzato**selezionare **server Web** o un altro modello di certificato server configurato per l'autenticazione del server.</span><span class="sxs-lookup"><span data-stu-id="d59a2-146">Under **Advanced Certificate Request**, select **Web server** or another server certificate template configured for server authentication.</span></span>

6.  <span data-ttu-id="d59a2-147">In **informazioni di identificazione per il modello offline**Digitare il nome di dominio completo (FQDN) del server Exchange nella casella **nome** .</span><span class="sxs-lookup"><span data-stu-id="d59a2-147">Under **Identifying Information for Offline Template**, in the **Name** box, type the fully qualified domain name (FQDN) of the Exchange Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d59a2-148">È necessario immettere il nome di dominio completo del server Exchange per le comunicazioni per il lavoro.</span><span class="sxs-lookup"><span data-stu-id="d59a2-148">You must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

7.  <span data-ttu-id="d59a2-149">In **Opzioni chiave**fare clic sulla casella di controllo Archivia **certificato nell'archivio certificati del computer locale** .</span><span class="sxs-lookup"><span data-stu-id="d59a2-149">Under **Key Options**, click the **Store certificate in the local computer certificate store** check box.</span></span>

8.  <span data-ttu-id="d59a2-150">Fare clic sul pulsante **Invia** nella parte inferiore della pagina Web.</span><span class="sxs-lookup"><span data-stu-id="d59a2-150">Click the **Submit** button in the bottom of the webpage.</span></span>

9.  <span data-ttu-id="d59a2-151">Nella finestra di dialogo che apre la richiesta di conferma fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-151">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

10. <span data-ttu-id="d59a2-152">Nella pagina certificato rilasciato, in **certificato emesso**, fare clic su **installa questo certificato**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-152">On the Certificate Issued page, under **Certificate Issued**, click **Install this certificate**.</span></span>

11. <span data-ttu-id="d59a2-153">Nella finestra di dialogo che apre la richiesta di conferma fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-153">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

12. <span data-ttu-id="d59a2-154">Verificare che venga visualizzato il messaggio "il nuovo certificato è stato installato correttamente".</span><span class="sxs-lookup"><span data-stu-id="d59a2-154">Verify that the message "Your new certificate has been successfully installed" appears.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a><span data-ttu-id="d59a2-155">Per creare un certificato in Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="d59a2-155">To create a certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="d59a2-156">Accedere al server che gestisce la messaggistica unificata di Exchange con i diritti utente appropriati.</span><span class="sxs-lookup"><span data-stu-id="d59a2-156">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="d59a2-157">Per informazioni dettagliate, vedere "autorizzazioni di [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)accesso client".</span><span class="sxs-lookup"><span data-stu-id="d59a2-157">For details, see "Client Access Permissions" at [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="d59a2-158">Per creare il certificato, vedere le procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="d59a2-158">Refer to the following procedures to create the certificate:</span></span>
    
    1.  <span data-ttu-id="d59a2-159">"Creare un nuovo certificato di Exchange" in[http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)</span><span class="sxs-lookup"><span data-stu-id="d59a2-159">"Create a New Exchange Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)</span></span>
    
    2.  <span data-ttu-id="d59a2-160">"Importare un certificato di Exchange" in[http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)</span><span class="sxs-lookup"><span data-stu-id="d59a2-160">"Import an Exchange Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d59a2-161">Per il <STRONG>nome del soggetto</STRONG>del certificato, è necessario immettere l'FQDN del server Exchange per le comunicazioni per il lavoro.</span><span class="sxs-lookup"><span data-stu-id="d59a2-161">For the certificate <STRONG>Subject Name</STRONG>, you must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="d59a2-162">Per assegnare il certificato in Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="d59a2-162">To assign the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="d59a2-163">Nel server che gestisce la messaggistica unificata di Exchange aprire MMC.</span><span class="sxs-lookup"><span data-stu-id="d59a2-163">On the server running Exchange UM, open MMC.</span></span>

2.  <span data-ttu-id="d59a2-164">Nell'albero della console espandere **Personal** e quindi fare clic su **certificati**.</span><span class="sxs-lookup"><span data-stu-id="d59a2-164">In the console tree, expand **Personal** and then click **Certificates**.</span></span>

3.  <span data-ttu-id="d59a2-165">Nel riquadro dei dettagli verificare che venga visualizzato il certificato personale.</span><span class="sxs-lookup"><span data-stu-id="d59a2-165">In the details pane, verify that personal certificate is displayed.</span></span>

4.  <span data-ttu-id="d59a2-166">Fare doppio clic sul certificato per leggere i dettagli e verificare che sia valido.</span><span class="sxs-lookup"><span data-stu-id="d59a2-166">Double-click the certificate to read its details and verify that it is valid.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d59a2-167">Potrebbe essere necessario attendere alcuni minuti prima che il certificato venga visualizzato come valido.</span><span class="sxs-lookup"><span data-stu-id="d59a2-167">It may take a few minutes before the certificate displays as valid.</span></span>

    
    </div>

5.  <span data-ttu-id="d59a2-168">Riavviare il servizio di messaggistica unificata di Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="d59a2-168">Restart the Microsoft Exchange Unified Messaging service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d59a2-169">Il server che gestisce la messaggistica unificata di Exchange Server 2007 SP1 recupera automaticamente il certificato corretto.</span><span class="sxs-lookup"><span data-stu-id="d59a2-169">The server running Exchange Server 2007 SP1 Unified Messaging automatically retrieves the correct certificate.</span></span>

    
    </div>

6.  <span data-ttu-id="d59a2-170">Aprire il Visualizzatore eventi e cercare l'ID evento 1112, che specifica quale certificato è stato recuperato dal server che ha eseguito la messaggistica unificata di Exchange Server 2007 SP1.</span><span class="sxs-lookup"><span data-stu-id="d59a2-170">Open Event Viewer and look for Event ID 1112, which specifies what certificate the server running Exchange Server 2007 SP1 Unified Messaging has retrieved.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a><span data-ttu-id="d59a2-171">Per assegnare il certificato in Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="d59a2-171">To assign the certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="d59a2-172">Accedere al server che gestisce la messaggistica unificata di Exchange con i diritti utente appropriati.</span><span class="sxs-lookup"><span data-stu-id="d59a2-172">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="d59a2-173">Per informazioni dettagliate, vedere "autorizzazioni di [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)accesso client".</span><span class="sxs-lookup"><span data-stu-id="d59a2-173">For details, see "Client Access Permissions" at [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="d59a2-174">Per la procedura per l'assegnazione del certificato, vedere "assegnare servizi a un certificato" [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497).</span><span class="sxs-lookup"><span data-stu-id="d59a2-174">For the procedure to assign the certificate, see "Assign Services to a Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

