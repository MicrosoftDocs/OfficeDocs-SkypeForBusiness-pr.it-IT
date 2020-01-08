---
title: "Lync Server 2013: Impostare i certificati per l'interfaccia perimetrale interna"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53ba11db5d2c9fc727b7720a1a10d5da547075c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a><span data-ttu-id="32f6c-102">Impostare i certificati per l'interfaccia perimetrale interna in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32f6c-102">Set up certificates for the internal edge interface in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32f6c-103">_**Argomento Ultima modifica:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="32f6c-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="32f6c-104">Quando si esegue la creazione guidata certificato, verificare di avere effettuato l'accesso con un account membro di un gruppo a cui sono state assegnate le autorizzazioni appropriate per il tipo di modello di certificato che verrà usato.</span><span class="sxs-lookup"><span data-stu-id="32f6c-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="32f6c-105">Per impostazione predefinita, una richiesta di certificato di Lync Server 2013 utilizzerà il modello di certificato del server Web.</span><span class="sxs-lookup"><span data-stu-id="32f6c-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="32f6c-106">Se si usa un account che è un membro del gruppo RTCUniversalServerAdmins per richiedere un certificato con questo modello, verificare che al gruppo siano state assegnate le autorizzazioni di registrazione necessarie per l'uso di tale modello.</span><span class="sxs-lookup"><span data-stu-id="32f6c-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="32f6c-107">È necessario un singolo certificato nell'interfaccia interna di ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="32f6c-107">A single certificate is required on the internal interface of each Edge Server.</span></span> <span data-ttu-id="32f6c-108">I certificati per l'interfaccia interna possono essere emessi da un'autorità di certificazione (CA) aziendale interna o da una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="32f6c-108">Certificates for the internal interface can be issued by an internal enterprise certification authority (CA) or a public CA.</span></span> <span data-ttu-id="32f6c-109">Se l'organizzazione ha una CA interna distribuita, è possibile salvarla a spese dell'uso di certificati pubblici usando la CA interna per emettere il certificato per l'interfaccia interna.</span><span class="sxs-lookup"><span data-stu-id="32f6c-109">If your organization has an internal CA deployed you can save on the expense of using public certificates by using the internal CA to issue the certificate for the internal interface.</span></span> <span data-ttu-id="32f6c-110">Per creare questi certificati, è possibile usare una CA interna di Windows Server 2008 o una CA Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="32f6c-110">You can use an internal Windows Server 2008 CA or Windows Server 2008 R2 CA to create these certificates.</span></span>

<span data-ttu-id="32f6c-111">Per informazioni dettagliate su questo e altri requisiti per i certificati, vedere [requisiti di certificato per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="32f6c-111">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="32f6c-112">Per configurare i certificati sull'interfaccia Edge interna di un sito, usare le procedure descritte in questa sezione per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="32f6c-112">To set up certificates on the internal edge interface at a site, use the procedures in this section to do the following:</span></span>

1.  <span data-ttu-id="32f6c-113">Scaricare la catena di certificazione CA per l'interfaccia interna di ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="32f6c-113">Download the CA certification chain for the internal interface to each Edge Server.</span></span>

2.  <span data-ttu-id="32f6c-114">Importare la catena di certificazione CA per l'interfaccia interna in ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="32f6c-114">Import the CA certification chain for the internal interface, on each Edge Server.</span></span>

3.  <span data-ttu-id="32f6c-115">Creare la richiesta di certificato per l'interfaccia interna, in un server perimetrale, denominata First Edge Server.</span><span class="sxs-lookup"><span data-stu-id="32f6c-115">Create the certificate request for the internal interface, on one Edge Server, called the first Edge Server.</span></span>

4.  <span data-ttu-id="32f6c-116">Importare il certificato per l'interfaccia interna nel primo server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="32f6c-116">Import the certificate for the internal interface on the first Edge Server.</span></span>

5.  <span data-ttu-id="32f6c-117">Importare il certificato sugli altri server perimetrali di questo sito (o distribuiti dietro questo bilanciamento del carico).</span><span class="sxs-lookup"><span data-stu-id="32f6c-117">Import the certificate on the other Edge Servers at this site (or deployed behind this load balancer).</span></span>

6.  <span data-ttu-id="32f6c-118">Assegnare il certificato per l'interfaccia interna di ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="32f6c-118">Assign the certificate for the internal interface of every Edge Server.</span></span>

<span data-ttu-id="32f6c-119">Se si hanno più siti con Edge Server, ossia una topologia a più siti, o Set distinti di server perimetrali distribuiti con diversi tipi di bilanciamento del carico, è necessario seguire questi passaggi per ogni sito con Edge Server e per ogni set di Edge Server distribuiti dietro un diverso bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="32f6c-119">If you have more than one site with Edge Servers (that is, a multiple-site edge topology), or separate sets of Edge Servers deployed behind different load balancers, you need to follow these steps for each site that has Edge Servers, and for each set of Edge Servers deployed behind a different load balancer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="32f6c-120">La procedura per le procedure in questa sezione si basa sull'uso di una&nbsp;CA di windows Server 2008&nbsp;,&nbsp;di una CA, di Windows Server 2008 R2, di Windows Server 2012 CA o di Windows Server 2012 R2 per creare un certificato per ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="32f6c-120">The steps for procedures in this section are based on using a Windows Server&nbsp;2008 CA, Windows Server&nbsp;2008&nbsp;R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA to create a certificate for each Edge Server.</span></span> <span data-ttu-id="32f6c-121">Per istruzioni dettagliate per qualsiasi altra autorità di certificazione, consultare la documentazione relativa a tale CA.</span><span class="sxs-lookup"><span data-stu-id="32f6c-121">For step-by-step guidance for any other CA, consult the documentation for that CA.</span></span> <span data-ttu-id="32f6c-122">Per impostazione predefinita, tutti gli utenti autenticati dispongono dei diritti utente appropriati per richiedere certificati.</span><span class="sxs-lookup"><span data-stu-id="32f6c-122">By default, all authenticated users have the appropriate user rights to request certificates.</span></span><BR><span data-ttu-id="32f6c-123">Le procedure descritte in questa sezione si basano sulla creazione di richieste di certificato nell'Edge Server come parte del processo di distribuzione di Edge Server.</span><span class="sxs-lookup"><span data-stu-id="32f6c-123">The procedures in this section are based on creating certificate requests on the Edge Server as part of the Edge Server deployment process.</span></span> <span data-ttu-id="32f6c-124">È possibile creare richieste di certificato con il server front-end.</span><span class="sxs-lookup"><span data-stu-id="32f6c-124">It is possible to create certificate requests using the Front End Server.</span></span> <span data-ttu-id="32f6c-125">Puoi eseguire questa operazione per completare la richiesta di certificato all'inizio del processo di pianificazione e distribuzione, prima di iniziare la distribuzione degli Edge Server.</span><span class="sxs-lookup"><span data-stu-id="32f6c-125">You can do this to complete the certificate request early in the planning and deployment process, before you start deployment of the Edge Servers.</span></span> <span data-ttu-id="32f6c-126">A questo scopo, devi assicurarti che il certificato richiesto sia definito con una chiave privata esportabile.</span><span class="sxs-lookup"><span data-stu-id="32f6c-126">To do this, you must ensure that the certificate you request is defined with an exportable private key.</span></span><BR><span data-ttu-id="32f6c-127">Le procedure descritte in questa sezione descrivono l'uso di un file con estensione CER e p7b per il certificato.</span><span class="sxs-lookup"><span data-stu-id="32f6c-127">The procedures in this section describe using a .cer and a .p7b file for the certificate.</span></span> <span data-ttu-id="32f6c-128">Se si usa un tipo di file diverso, modificare le procedure in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="32f6c-128">If you use a different type of file, modify these procedures as appropriate.</span></span>



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a><span data-ttu-id="32f6c-129">Per scaricare la catena di certificazione CA per l'interfaccia interna tramite il sito Web di certsrv</span><span class="sxs-lookup"><span data-stu-id="32f6c-129">To download the CA certification chain for the internal interface using certsrv Web site</span></span>

1.  <span data-ttu-id="32f6c-130">Accedere a un server Lync Server 2013 nella rete interna, ovvero non nel server perimetrale, come membro del gruppo **Administrators** .</span><span class="sxs-lookup"><span data-stu-id="32f6c-130">Log on to an Lync Server 2013 server in the internal network (that is, not the Edge Server) as a member of the **Administrators** group.</span></span>

2.  <span data-ttu-id="32f6c-131">Eseguire il comando seguente al prompt dei comandi facendo clic sul pulsante **Start**, scegliendo **Esegui**e digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="32f6c-131">Run the following command at a command prompt by clicking **Start**, clicking **Run**, and then typing the following:</span></span>
    
        https://<name of your Issuing CA Server>/certsrv
    
    <span data-ttu-id="32f6c-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="32f6c-132">For example:</span></span>
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32f6c-133">Se si usa una CA di Windows Server 2008 o Windows Server 2008 R2 Enterprise, è necessario usare HTTPS e non http.</span><span class="sxs-lookup"><span data-stu-id="32f6c-133">If you are using a Windows Server 2008 or Windows Server 2008 R2 enterprise CA, you must use https, not http.</span></span>

    
    </div>

3.  <span data-ttu-id="32f6c-134">Nella pagina Web certsrv della CA emittente, in **selezionare un'attività**, fare clic su **Scarica un certificato CA, una catena di certificati o un CRL**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-134">On the issuing CA’s certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

4.  <span data-ttu-id="32f6c-135">In **scaricare un certificato CA, una catena di certificati o un CRL**fare clic su **Scarica catena di certificati CA**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-135">Under **Download a CA Certificate, Certificate Chain, or CRL**, click **Download CA certificate chain**.</span></span>

5.  <span data-ttu-id="32f6c-136">Nella finestra di dialogo **Download file** fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-136">In the **File Download** dialog box, click **Save**.</span></span>

6.  <span data-ttu-id="32f6c-137">Salvare il file con estensione p7b nell'unità disco rigido del server e quindi copiarlo in una cartella in ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="32f6c-137">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32f6c-138">Il file con estensione p7b contiene tutti i certificati presenti nel percorso di certificazione.</span><span class="sxs-lookup"><span data-stu-id="32f6c-138">The .p7b file contains all of the certificates that are in the certification path.</span></span> <span data-ttu-id="32f6c-139">Per visualizzare il percorso di certificazione, aprire il certificato del server e fare clic sul percorso di certificazione.</span><span class="sxs-lookup"><span data-stu-id="32f6c-139">To view the certification path, open the server certificate and click the certification path.</span></span>

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a><span data-ttu-id="32f6c-140">Per esportare la catena di certificazione CA per l'interfaccia interna tramite MMC</span><span class="sxs-lookup"><span data-stu-id="32f6c-140">To export the CA certification chain for the internal interface using MMC</span></span>

1.  <span data-ttu-id="32f6c-141">È possibile esportare il certificato radice della CA da qualsiasi computer unito a un dominio usando Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="32f6c-141">You can export the CA root certificate from any domain joined machine using the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="32f6c-142">Fare clic sul pulsante **Start**, scegliere **Esegui**e quindi digitare **MMC**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-142">Click **Start**, click **Run**, and then type **MMC**.</span></span>

2.  <span data-ttu-id="32f6c-143">Nella console MMC fare clic su **file**, quindi su **Aggiungi/Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-143">In the MMC console, click **File**, click **Add/Remove**.</span></span>

3.  <span data-ttu-id="32f6c-144">Nell'elenco **Aggiungi o Rimuovi snap-** in selezionare **certificati**, quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-144">From the **Add or Remove Snap-ins** dialog list, select **Certificates**, then click **Add**.</span></span> <span data-ttu-id="32f6c-145">Quando richiesto, selezionare **account computer**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-145">When prompted, select **Computer Account**.</span></span> <span data-ttu-id="32f6c-146">Nella finestra di dialogo **Seleziona computer** selezionare **computer locale**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-146">On the **Select Computer** dialog, select **Local Computer**.</span></span> <span data-ttu-id="32f6c-147">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-147">Click **Finish**.</span></span> <span data-ttu-id="32f6c-148">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-148">Click **OK**.</span></span>

4.  <span data-ttu-id="32f6c-149">Espandere **certificati (computer locale)**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-149">Expand **Certificates (Local Computer)**.</span></span> <span data-ttu-id="32f6c-150">Espandere **autorità di certificazione radice attendibili**, selezionare **certificati**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-150">Expand **Trusted Root Certification Authorities**, select **Certificates**.</span></span>

5.  <span data-ttu-id="32f6c-151">Fare clic sul certificato radice emesso dalla CA.</span><span class="sxs-lookup"><span data-stu-id="32f6c-151">Click the root certificate issued by your CA.</span></span> <span data-ttu-id="32f6c-152">Fare clic con il pulsante destro del mouse sul certificato, selezionare **tutte le attività**, quindi **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-152">Right click the certificate, select **All Tasks**, select **Export**.</span></span> <span data-ttu-id="32f6c-153">Verrà aperta l' **esportazione guidata certificati** .</span><span class="sxs-lookup"><span data-stu-id="32f6c-153">The **Certificate Export Wizard** will open.</span></span>

6.  <span data-ttu-id="32f6c-154">Nell' **esportazione guidata certificati**fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-154">In the **Certificate Export Wizard**, click **Next**.</span></span>

7.  <span data-ttu-id="32f6c-155">Nella finestra di dialogo **Esporta formato file** selezionare un formato da esportare.</span><span class="sxs-lookup"><span data-stu-id="32f6c-155">On the **Export File Format** dialog, select a format to export to.</span></span> <span data-ttu-id="32f6c-156">È consigliabile la **sintassi del messaggio crittografico standard: \#i certificati PKCS 7 (. P7B)**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-156">We recommend the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**.</span></span> <span data-ttu-id="32f6c-157">Se si seleziona la **sintassi del messaggio crittografico standard, \#ovvero i certificati PKCS 7 (. P7B)** selezionare la casella di controllo **Includi tutti i certificati nel percorso di certificazione, se possibile** , per esportare la catena di certificati, incluso il certificato della CA radice e gli eventuali certificati intermedi della CA.</span><span class="sxs-lookup"><span data-stu-id="32f6c-157">If you select the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**, select the **Include all certificates in the certification path if possible** checkbox to export the certificate chain, including the root CA certificate and any Intermediate CA certificates.</span></span> <span data-ttu-id="32f6c-158">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-158">Click **Next**.</span></span>

8.  <span data-ttu-id="32f6c-159">Nella finestra **di dialogo file da esportare** nella voce nome file digitare un percorso e un nome file (l'estensione predefinita è p7b) per il certificato esportato.</span><span class="sxs-lookup"><span data-stu-id="32f6c-159">On the **File to Export** dialog in the file name entry, type a path and file name (default extension is .p7b) for the exported certificate.</span></span> <span data-ttu-id="32f6c-160">Facoltativamente, fare clic su **Sfoglia**, individuare una directory in cui inserire il certificato esportato e specificare un nome per il certificato esportato.</span><span class="sxs-lookup"><span data-stu-id="32f6c-160">Optionally, click **Browse**, locate a directory to place the exported certificate in and provide a name for the exported certificate.</span></span> <span data-ttu-id="32f6c-161">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-161">Click **Save**.</span></span> <span data-ttu-id="32f6c-162">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-162">Click **Next**.</span></span>

9.  <span data-ttu-id="32f6c-163">Esaminare il riepilogo delle azioni e fare clic su **fine** per completare l'esportazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="32f6c-163">Review the summary of actions, and click **Finish** to complete the export of the certificate.</span></span> <span data-ttu-id="32f6c-164">Fare clic su **OK** per confermare l'esportazione riuscita.</span><span class="sxs-lookup"><span data-stu-id="32f6c-164">Click **OK** to confirm the successful export.</span></span>

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a><span data-ttu-id="32f6c-165">Per importare la catena di certificazione CA per l'interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="32f6c-165">To import the CA certification chain for the internal interface</span></span>

1.  <span data-ttu-id="32f6c-166">In ogni server perimetrale aprire Microsoft Management Console (MMC) facendo clic sul pulsante **Start**, scegliendo **Esegui**, digitando **MMC** nella casella **Apri** e quindi facendo clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-166">On each Edge Server, open the Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="32f6c-167">Nel menu **file** fare clic su **Aggiungi/Rimuovi snap-in**e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-167">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="32f6c-168">Nella casella **Add standalone snap-** in fare clic su **certificati**e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-168">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="32f6c-169">Nella finestra di dialogo di **snap-in certificato** fare clic su **account computer**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-169">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="32f6c-170">Nella finestra di dialogo **Seleziona computer** verificare che la casella di controllo computer **locale: (il computer in cui è in uso questa console)** sia selezionata e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-170">In the **Select Computer** dialog box, ensure that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="32f6c-171">Fare clic su **Chiudi**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-171">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="32f6c-172">Nell'albero della console espandere **certificati (computer locale)**, fare clic con il pulsante destro del mouse su **autorità di certificazione radice attendibili**, scegliere **tutte le attività**e quindi fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-172">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, point to **All Tasks**, and then click **Import**.</span></span>

8.  <span data-ttu-id="32f6c-173">Nella procedura guidata, in **file da importare**, specificare il nome del file del certificato, ovvero il nome specificato quando è stata scaricata la catena di certificazione CA per l'interfaccia interna nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="32f6c-173">In the wizard, in **File to Import**, specify the file name of the certificate (that is, the name of that you specified when you downloaded the CA certification chain for the internal interface in the previous procedure).</span></span>

9.  <span data-ttu-id="32f6c-174">Ripetere questa procedura in ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="32f6c-174">Repeat this procedure on each Edge Server.</span></span>

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a><span data-ttu-id="32f6c-175">Per creare la richiesta di certificato per l'interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="32f6c-175">To create the certificate request for the internal interface</span></span>

1.  <span data-ttu-id="32f6c-176">In uno dei server perimetrali avviare la distribuzione guidata e, accanto al **passaggio 3: richiedere, installare o assegnare certificati**, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-176">On one of the Edge Servers, start the Deployment Wizard, and next to **Step 3: Request, Install, or Assign Certificates**, click **Run**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32f6c-177">Se si hanno più Edge Server in una posizione in un pool, è possibile eseguire la procedura guidata certificato in uno dei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="32f6c-177">If you have multiple Edge Servers in one location in a pool, you can run the Certificate Wizard on any one of the Edge Servers.</span></span><BR><span data-ttu-id="32f6c-178">Dopo aver eseguito il passaggio 3 la prima volta, il pulsante viene modificato di <STRONG>nuovo in esecuzione</STRONG>e un segno di spunta verde che indica che il completamento dell'attività non viene visualizzato finché tutti i certificati di richiesta non sono stati richiesti, installati e assegnati.</span><span class="sxs-lookup"><span data-stu-id="32f6c-178">After you run Step 3 the first time, the button changes to <STRONG>Run again</STRONG>, and a green check mark that indicates successful completion of the task is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

    
    </div>

2.  <span data-ttu-id="32f6c-179">Nella pagina **attività certificato disponibili** fare clic su **Crea una nuova richiesta di certificato**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-179">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="32f6c-180">Nella pagina **richiesta certificato** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-180">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="32f6c-181">Nella pagina **richieste immediate o posticipate** fare clic su **prepara la richiesta ora, ma inviarla**in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="32f6c-181">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>

5.  <span data-ttu-id="32f6c-182">Nella pagina **file di richiesta certificato** Digitare il percorso completo e il nome del file a cui deve essere salvata la richiesta, ad esempio **c:\\CERT\_Internal\_Edge. cer**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-182">On the **Certificate Request File** page, type the full path and file name to which the request is to be saved (for example, **c:\\cert\_internal\_edge.cer**).</span></span>

6.  <span data-ttu-id="32f6c-183">Nella pagina **Specifica modello di certificato alternativo** , per usare un modello diverso da quello predefinito del modello webserver, selezionare la casella di controllo **Usa il modello di certificato alternativo per l'autorità di certificazione selezionata** .</span><span class="sxs-lookup"><span data-stu-id="32f6c-183">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>

7.  <span data-ttu-id="32f6c-184">Nella pagina **impostazioni di sicurezza e nome** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="32f6c-184">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="32f6c-185">In **nome descrittivo**Digitare un nome visualizzato per il certificato, ad esempio bordo interno.</span><span class="sxs-lookup"><span data-stu-id="32f6c-185">In **Friendly name**, type a display name for the certificate (for example, Internal Edge).</span></span>
    
      - <span data-ttu-id="32f6c-186">In **bit length**specificare la lunghezza in bit (in genere, il valore predefinito è **2048**).</span><span class="sxs-lookup"><span data-stu-id="32f6c-186">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="32f6c-187">Le lunghezze di bit più alte offrono maggiore sicurezza, ma hanno un impatto negativo sulla velocità.</span><span class="sxs-lookup"><span data-stu-id="32f6c-187">Higher bit lengths offer more security, but they have a negative impact on speed.</span></span>

        
        </div>
    
      - <span data-ttu-id="32f6c-188">Se il certificato deve essere esportabile, selezionare la casella di controllo **contrassegna la chiave privata del certificato come esportabile** .</span><span class="sxs-lookup"><span data-stu-id="32f6c-188">If the certificate needs to be exportable, select the **Mark certificate private key as exportable** check box.</span></span>

8.  <span data-ttu-id="32f6c-189">Nella pagina **informazioni organizzazione** Digitare il nome dell'organizzazione e dell'unità organizzativa (ad esempio, divisione o reparto).</span><span class="sxs-lookup"><span data-stu-id="32f6c-189">On the **Organization Information** page, type the name for the organization and the organizational unit (OU) (for example, a division or department).</span></span>

9.  <span data-ttu-id="32f6c-190">Nella pagina **informazioni geografiche** specificare le informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="32f6c-190">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="32f6c-191">Nella pagina **nome oggetto/nomi oggetto alternativo** vengono visualizzate le informazioni che verranno inserite automaticamente dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="32f6c-191">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span>

11. <span data-ttu-id="32f6c-192">Nella pagina **Configura altri nomi alternativi oggetto** specificare eventuali altri nomi alternativi per gli argomenti necessari.</span><span class="sxs-lookup"><span data-stu-id="32f6c-192">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

12. <span data-ttu-id="32f6c-193">Nella pagina **Riepilogo richieste** verificare le informazioni sul certificato che verranno usate per generare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="32f6c-193">On the **Request Summary** page, review the certificate information that is going to be used to generate the request.</span></span>

13. <span data-ttu-id="32f6c-194">Dopo aver completato i comandi, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="32f6c-194">After the commands complete, do the following:</span></span>
    
      - <span data-ttu-id="32f6c-195">Per visualizzare il log per la richiesta di certificato, fare clic su **Visualizza log**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-195">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="32f6c-196">Per completare la richiesta di certificato, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-196">To complete the certificate request, click **Next**.</span></span>

14. <span data-ttu-id="32f6c-197">Nella pagina **file di richiesta certificato** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="32f6c-197">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="32f6c-198">Per visualizzare il file della richiesta di firma del certificato (CSR) generato, fare clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-198">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="32f6c-199">Per chiudere la procedura guidata, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-199">To close the wizard, click **Finish**.</span></span>

15. <span data-ttu-id="32f6c-200">Inviare il file alla CA (tramite posta elettronica o altro metodo supportato dall'organizzazione per la CA aziendale) e, quando si riceve il file di risposta, copiare il nuovo certificato nel computer in modo che sia disponibile per l'importazione.</span><span class="sxs-lookup"><span data-stu-id="32f6c-200">Submit this file to your CA (by email or other method supported by your organization for your enterprise CA) and, when you receive the response file, copy the new certificate to this computer so that it is available for import.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a><span data-ttu-id="32f6c-201">Per importare il certificato per l'interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="32f6c-201">To import the certificate for the internal interface</span></span>

1.  <span data-ttu-id="32f6c-202">Accedere all'Edge Server in cui è stata creata la richiesta di certificato come membro del gruppo Administrators locale.</span><span class="sxs-lookup"><span data-stu-id="32f6c-202">Log on to the Edge Server on which you created the certificate request as a member of the local Administrators group.</span></span>

2.  <span data-ttu-id="32f6c-203">Nella distribuzione guidata, accanto a **passaggio 3: richiedere, installare o assegnare certificati**, fare di nuovo clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-203">In the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <span data-ttu-id="32f6c-204">Dopo aver eseguito il passaggio 3 la prima volta, il pulsante viene modificato di **nuovo in esecuzione**, ma un segno di spunta verde (che indica il completamento dell'attività) non viene visualizzato finché non sono stati richiesti, installati e assegnati tutti i certificati.</span><span class="sxs-lookup"><span data-stu-id="32f6c-204">After you run Step 3 the first time, the button changes to **Run again**, but a green check mark (indicating successful completion of the task) is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

3.  <span data-ttu-id="32f6c-205">Nella pagina **attività certificato disponibili** fare clic su **Importa un certificato da a. File di P7b, pfx o CER**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-205">On the **Available Certificate Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>

4.  <span data-ttu-id="32f6c-206">Nella pagina **Importa certificato** Digitare il percorso completo e il nome file del certificato richiesto e ricevuto per l'interfaccia interna di questo Edge Server (oppure fare clic su **Sfoglia** per individuare e selezionare il file).</span><span class="sxs-lookup"><span data-stu-id="32f6c-206">On the **Import Certificate** page, type the full path and file name of the certificate that you requested and received for the internal interface of this Edge Server (or, click **Browse** to locate and select the file).</span></span>

5.  <span data-ttu-id="32f6c-207">Se si importano certificati per altri membri del pool un certificato contenente una chiave privata, selezionare il **file di certificato contiene la casella di controllo chiave privata di certificato** e specificare la password.</span><span class="sxs-lookup"><span data-stu-id="32f6c-207">If you are importing certificates for other members of the pool a certificate containing a private key, select the **Certificate file contains certifcate’s private key** check box and specify the password.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="32f6c-208">Per esportare il certificato con la chiave privata per Edge Server in un pool</span><span class="sxs-lookup"><span data-stu-id="32f6c-208">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="32f6c-209">Accedere come membro del gruppo Administrators allo stesso Edge Server in cui è stato importato il certificato.</span><span class="sxs-lookup"><span data-stu-id="32f6c-209">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="32f6c-210">Fare clic sul pulsante **Start**, scegliere **Esegui**e digitare **MMC**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-210">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="32f6c-211">Nella console MMC fare clic su **file**, fare clic su **Aggiungi/Rimuovi snap-in**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-211">From the MMC console, click **File**, click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="32f6c-212">Nella pagina Aggiungi o Rimuovi snap-in fare clic su **certificati**, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-212">From Add or Remove Snap-ins page, click **Certificates**, click **Add**.</span></span>

5.  <span data-ttu-id="32f6c-213">Nella finestra di dialogo snap-in certificati selezionare **account computer**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-213">In the Certificates snap-in dialog, select **Computer account**.</span></span> <span data-ttu-id="32f6c-214">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-214">Click **Next**.</span></span> <span data-ttu-id="32f6c-215">In Seleziona computer selezionare **computer locale: (il computer in cui è in uso la console)**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-215">In Select Computer, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="32f6c-216">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-216">Click **Finish**.</span></span> <span data-ttu-id="32f6c-217">Fare clic su **OK** per completare la configurazione della console MMC.</span><span class="sxs-lookup"><span data-stu-id="32f6c-217">Click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="32f6c-218">Fare doppio clic su **certificati (computer locale)** per espandere gli archivi di certificati.</span><span class="sxs-lookup"><span data-stu-id="32f6c-218">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="32f6c-219">Fare doppio clic su **personale**, quindi fare doppio clic su **certificati**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-219">Double-click **Personal**, then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="32f6c-220">Se non ci sono certificati nell'archivio personale certificati per il computer locale, non esiste alcuna chiave privata associata al certificato importato.</span><span class="sxs-lookup"><span data-stu-id="32f6c-220">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported.</span></span> <span data-ttu-id="32f6c-221">Esaminare la procedura di richiesta e importazione.</span><span class="sxs-lookup"><span data-stu-id="32f6c-221">Review the request and import steps.</span></span> <span data-ttu-id="32f6c-222">Se il problema persiste, contattare l'amministratore o il provider dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="32f6c-222">If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="32f6c-223">Nell'archivio personale certificati per il computer locale fare clic con il pulsante destro del mouse sul certificato che si sta esportando.</span><span class="sxs-lookup"><span data-stu-id="32f6c-223">In the Certificates Personal store for the local computer, right-click the certificate that you are exporting.</span></span> <span data-ttu-id="32f6c-224">Fare clic su **tutte le attività**, fare clic su **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-224">Click **All Tasks**, click **Export**.</span></span>

8.  <span data-ttu-id="32f6c-225">Nell'esportazione guidata certificati fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-225">In the Certificate Export Wizard, click **Next**.</span></span> <span data-ttu-id="32f6c-226">Selezionare **Sì, esportare la chiave privata**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-226">Select **Yes, export the private key**.</span></span> <span data-ttu-id="32f6c-227">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-227">Click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32f6c-228">Se la selezione <STRONG>Sì, Esporta la chiave privata</STRONG> non è disponibile, la chiave privata associata al certificato non è stata contrassegnata per l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="32f6c-228">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export.</span></span> <span data-ttu-id="32f6c-229">Sarà necessario richiedere di nuovo il certificato, assicurandosi che il certificato sia contrassegnato per consentire l'esportazione della chiave privata prima di poter continuare con l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="32f6c-229">You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export.</span></span> <span data-ttu-id="32f6c-230">Contattare l'amministratore o il provider dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="32f6c-230">Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="32f6c-231">Nella finestra di dialogo Esporta formati di file selezionare **Personal Information Exchange-\#PKCS 12 (. PFX)** e quindi selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="32f6c-231">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="32f6c-232">Includere tutti i certificati nel percorso di certificazione, se possibile</span><span class="sxs-lookup"><span data-stu-id="32f6c-232">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="32f6c-233">Esportare tutte le proprietà estese</span><span class="sxs-lookup"><span data-stu-id="32f6c-233">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="32f6c-234">Quando si esporta il certificato da un server perimetrale, non selezionare <STRONG>Elimina la chiave privata se l'esportazione ha esito positivo</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="32f6c-234">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>.</span></span> <span data-ttu-id="32f6c-235">Se si seleziona questa opzione, è necessario importare il certificato e la chiave privata in questo server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="32f6c-235">Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>
    
    <span data-ttu-id="32f6c-236">Fare clic su **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="32f6c-236">Click **Next** to continue.</span></span>

10. <span data-ttu-id="32f6c-237">Se si vuole assegnare una password per proteggere la chiave privata, digitare una password per la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="32f6c-237">If you want to assign password to protect the private key, type a password for the private key.</span></span> <span data-ttu-id="32f6c-238">Immettere di nuovo la password per confermare.</span><span class="sxs-lookup"><span data-stu-id="32f6c-238">Re-enter the password to confirm.</span></span> <span data-ttu-id="32f6c-239">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-239">Click **Next**.</span></span>

11. <span data-ttu-id="32f6c-240">Digitare un percorso e un nome di file per il certificato esportato, usando un'estensione di file PFX.</span><span class="sxs-lookup"><span data-stu-id="32f6c-240">Type a path and file name for the exported certificate, using a file extension of .pfx.</span></span> <span data-ttu-id="32f6c-241">Il percorso deve essere accessibile a tutti gli altri Edge Server nel pool o disponibile per il trasporto tramite supporti rimovibili, ad esempio un'unità flash USB.</span><span class="sxs-lookup"><span data-stu-id="32f6c-241">The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive.</span></span> <span data-ttu-id="32f6c-242">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-242">Click **Next**.</span></span>

12. <span data-ttu-id="32f6c-243">Esaminare il riepilogo nella finestra di dialogo completamento dell'esportazione guidata certificati.</span><span class="sxs-lookup"><span data-stu-id="32f6c-243">Review the summary on the Completing the Certificate Export Wizard dialog.</span></span> <span data-ttu-id="32f6c-244">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-244">Click **Finish**.</span></span>

13. <span data-ttu-id="32f6c-245">Fare clic su **OK** nella finestra di dialogo Esporta riuscita.</span><span class="sxs-lookup"><span data-stu-id="32f6c-245">Click **OK** in the successful export dialog.</span></span>

14. <span data-ttu-id="32f6c-246">Importare il file di certificato esportato negli altri Edge Server seguendo la procedura descritta in [configurare i certificati per l'interfaccia esterna di Edge per le procedure di Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="32f6c-246">Import the exported certificate file to the other Edge servers following the steps outlined in the [Set up certificates for the external edge interface for Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) procedures.</span></span>

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a><span data-ttu-id="32f6c-247">Per assegnare il certificato interno agli Edge Server</span><span class="sxs-lookup"><span data-stu-id="32f6c-247">To assign the internal certificate on the Edge Servers</span></span>

1.  <span data-ttu-id="32f6c-248">In ogni server perimetrale, nella distribuzione guidata, accanto a **passaggio 3: richiedere, installare o assegnare certificati**, fare di **nuovo**clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="32f6c-248">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="32f6c-249">Nella pagina **attività certificato disponibili** fare clic su **assegna un certificato esistente**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-249">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="32f6c-250">Nella pagina **assegnazione certificato** selezionare **bordo interno** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="32f6c-250">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>

4.  <span data-ttu-id="32f6c-251">Nella pagina **archivio certificati** selezionare il certificato importato per il bordo interno (nella procedura precedente).</span><span class="sxs-lookup"><span data-stu-id="32f6c-251">On the **Certificate Store** page, select the certificate that you imported for the internal edge (from the previous procedure).</span></span>

5.  <span data-ttu-id="32f6c-252">Nella pagina **Riepilogo assegnazione certificati** verificare le impostazioni e quindi fare clic su **Avanti** per assegnare i certificati.</span><span class="sxs-lookup"><span data-stu-id="32f6c-252">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

6.  <span data-ttu-id="32f6c-253">Nella pagina Completamento procedura guidata fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="32f6c-253">On the wizard completion page, click **Finish**.</span></span>

7.  <span data-ttu-id="32f6c-254">Dopo aver usato questa procedura per assegnare il certificato del bordo interno, aprire lo snap-in certificato in ogni server, espandere **certificati (computer locale)**, espandere **personale**, fare clic su **certificati**e quindi verificare nel riquadro dei dettagli l'elenco del certificato perimetrale interno.</span><span class="sxs-lookup"><span data-stu-id="32f6c-254">After using this procedure to assign the internal edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the internal edge certificate is listed.</span></span>

8.  <span data-ttu-id="32f6c-255">Se la distribuzione include più Edge Server, ripetere questa procedura per ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="32f6c-255">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

