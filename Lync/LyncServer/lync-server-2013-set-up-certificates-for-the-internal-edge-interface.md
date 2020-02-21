---
title: "Lync Server 2013: impostare i certificati per l'interfaccia perimetrale interna"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c34e1d0d4e87bffbf28ba600ab23d849fd664423
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a><span data-ttu-id="f4e4a-102">Configurare i certificati per l'interfaccia perimetrale interna in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4e4a-102">Set up certificates for the internal edge interface in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4e4a-103">_**Ultimo argomento modificato:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="f4e4a-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f4e4a-104">Quando si esegue la Configurazione guidata certificati, verificare di aver eseguito l'accesso con un account membro di un gruppo a cui sono state assegnate le autorizzazioni appropriate per il tipo di modello di certificato che verrà utilizzato.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="f4e4a-105">Per impostazione predefinita, una richiesta di certificato di Lync Server 2013 utilizzerà il modello di certificato del server Web.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="f4e4a-106">Se per la richiesta di un certificato con questo modello si utilizza un account membro del gruppo RTCUniversalServerAdmins, verificare che al gruppo siano state assegnate le autorizzazioni di registrazione necessarie per l'utilizzo del modello.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="f4e4a-p102">Per l'interfaccia interna di ogni server perimetrale è necessario un unico certificato. I certificati per l'interfaccia interna possono essere emessi da un'Autorità di certificazione (CA) globale (enterprise) interna o da una CA pubblica. Se nell'organizzazione è distribuita una CA interna, è possibile emettere il certificato per l'interfaccia interna utilizzando la CA interna, evitando la spesa legata all'utilizzo di certificati pubblici. Per la creazione dei certificati è possibile utilizzare una CA interna Windows Server 2008 o Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-p102">A single certificate is required on the internal interface of each Edge Server. Certificates for the internal interface can be issued by an internal enterprise certification authority (CA) or a public CA. If your organization has an internal CA deployed you can save on the expense of using public certificates by using the internal CA to issue the certificate for the internal interface. You can use an internal Windows Server 2008 CA or Windows Server 2008 R2 CA to create these certificates.</span></span>

<span data-ttu-id="f4e4a-111">Per informazioni dettagliate su questo e altri requisiti per i certificati, vedere [requisiti dei certificati per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f4e4a-111">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="f4e4a-112">Per impostare i certificati per l'interfaccia perimetrale interna presso un sito, le procedure descritte in questa sezione consentono di eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4e4a-112">To set up certificates on the internal edge interface at a site, use the procedures in this section to do the following:</span></span>

1.  <span data-ttu-id="f4e4a-113">Scaricare la catena di certificazione CA per l'interfaccia interna in ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-113">Download the CA certification chain for the internal interface to each Edge Server.</span></span>

2.  <span data-ttu-id="f4e4a-114">Importare la catena di certificazione CA per l'interfaccia interna in ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-114">Import the CA certification chain for the internal interface, on each Edge Server.</span></span>

3.  <span data-ttu-id="f4e4a-115">Creare la richiesta di certificato per l'interfaccia interna in un unico server perimetrale, denominato primo server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-115">Create the certificate request for the internal interface, on one Edge Server, called the first Edge Server.</span></span>

4.  <span data-ttu-id="f4e4a-116">Importare il certificato per l'interfaccia interna nel primo server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-116">Import the certificate for the internal interface on the first Edge Server.</span></span>

5.  <span data-ttu-id="f4e4a-117">Importare il certificato negli altri server perimetrali presenti nel sito o distribuiti e controllati dal servizio di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-117">Import the certificate on the other Edge Servers at this site (or deployed behind this load balancer).</span></span>

6.  <span data-ttu-id="f4e4a-118">Assegnare il certificato per l'interfaccia interna di ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-118">Assign the certificate for the internal interface of every Edge Server.</span></span>

<span data-ttu-id="f4e4a-119">Se sono presenti più siti con server perimetrali, ovvero se è disponibile una topologia perimetrale con più siti, oppure insiemi distinti di server perimetrali distribuiti e controllati da servizi di bilanciamento del carico diversi, è necessario completare questi passaggi separatamente per ogni sito in cui sono presenti server perimetrali e per ogni insieme di server perimetrali distribuito e controllato da un servizio di bilanciamento del carico diverso.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-119">If you have more than one site with Edge Servers (that is, a multiple-site edge topology), or separate sets of Edge Servers deployed behind different load balancers, you need to follow these steps for each site that has Edge Servers, and for each set of Edge Servers deployed behind a different load balancer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f4e4a-120">I passaggi per le procedure descritte in questa sezione si basano sull'utilizzo&nbsp;di un certificato di windows&nbsp;server&nbsp;2008 CA, di Windows Server 2008 r2 CA, di Windows Server 2012 CA o di Windows Server 2012 R2 per la creazione di certificati per ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-120">The steps for procedures in this section are based on using a Windows Server&nbsp;2008 CA, Windows Server&nbsp;2008&nbsp;R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA to create a certificate for each Edge Server.</span></span> <span data-ttu-id="f4e4a-121">Per istruzioni dettagliate per altre CA, consultare la documentazione della CA specifica.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-121">For step-by-step guidance for any other CA, consult the documentation for that CA.</span></span> <span data-ttu-id="f4e4a-122">Per impostazione predefinita, tutti gli utenti autenticati dispongono dei diritti appropriati per richiedere certificati.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-122">By default, all authenticated users have the appropriate user rights to request certificates.</span></span><BR><span data-ttu-id="f4e4a-p104">Per le procedure descritte in questa sezione, si presuppone che la creazione delle richieste di certificati nel server perimetrale avvenga nel corso del processo di distribuzione del server perimetrale stesso. È possibile creare richieste di certificati utilizzando il Front End Server per completare la richiesta del certificato in una fase iniziale del processo di pianificazione e distribuzione, prima di cominciare la distribuzione dei server perimetrali. A tale scopo, è necessario che il certificato richiesto sia definito con una chiave privata esportabile.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-p104">The procedures in this section are based on creating certificate requests on the Edge Server as part of the Edge Server deployment process. It is possible to create certificate requests using the Front End Server. You can do this to complete the certificate request early in the planning and deployment process, before you start deployment of the Edge Servers. To do this, you must ensure that the certificate you request is defined with an exportable private key.</span></span><BR><span data-ttu-id="f4e4a-p105">Nelle procedure di questa sezione è descritto l'utilizzo di un file con estensione cer e con estensione p7b come certificato. Se si utilizza un tipo di file diverso, modificare le procedure di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-p105">The procedures in this section describe using a .cer and a .p7b file for the certificate. If you use a different type of file, modify these procedures as appropriate.</span></span>



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a><span data-ttu-id="f4e4a-129">Per scaricare la catena di certificazione CA per l'interfaccia interna tramite il sito Web certsrv</span><span class="sxs-lookup"><span data-stu-id="f4e4a-129">To download the CA certification chain for the internal interface using certsrv Web site</span></span>

1.  <span data-ttu-id="f4e4a-130">Accedere a un server Lync Server 2013 nella rete interna, ovvero non nel server perimetrale, come membro del gruppo **Administrators** .</span><span class="sxs-lookup"><span data-stu-id="f4e4a-130">Log on to an Lync Server 2013 server in the internal network (that is, not the Edge Server) as a member of the **Administrators** group.</span></span>

2.  <span data-ttu-id="f4e4a-131">Eseguire il comando che segue. A tale scopo, fare clic sul pulsante **Start**, scegliere **Esegui** e quindi al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f4e4a-131">Run the following command at a command prompt by clicking **Start**, clicking **Run**, and then typing the following:</span></span>
    
        https://<name of your Issuing CA Server>/certsrv
    
    <span data-ttu-id="f4e4a-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f4e4a-132">For example:</span></span>
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f4e4a-133">Se si utilizza una CA globale (enterprise) Windows Server 2008 o Windows Server 2008 R2, è necessario digitare https anziché http.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-133">If you are using a Windows Server 2008 or Windows Server 2008 R2 enterprise CA, you must use https, not http.</span></span>

    
    </div>

3.  <span data-ttu-id="f4e4a-134">Nella pagina Web certsrv della CA emittente, in **Selezionare un'attività**, fare clic su **Scarica un certificato CA, la catena di certificati o un CRL**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-134">On the issuing CA’s certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

4.  <span data-ttu-id="f4e4a-135">In **Scarica un certificato CA, la catena di certificati o un CRL** fare clic su **Esegui download catena di certificati CA**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-135">Under **Download a CA Certificate, Certificate Chain, or CRL**, click **Download CA certificate chain**.</span></span>

5.  <span data-ttu-id="f4e4a-136">Nella finestra di dialogo **Download del file** fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-136">In the **File Download** dialog box, click **Save**.</span></span>

6.  <span data-ttu-id="f4e4a-137">Salvare il file con estensione p7b nell'unità disco rigido del server e quindi copiarlo in una cartella di ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-137">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f4e4a-p106">Il file con estensione p7b contiene tutti i certificati inclusi nel percorso di certificazione. Per visualizzare il percorso di certificazione, aprire il certificato server e fare clic sul percorso di certificazione.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-p106">The .p7b file contains all of the certificates that are in the certification path. To view the certification path, open the server certificate and click the certification path.</span></span>

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a><span data-ttu-id="f4e4a-140">Per esportare la catena di certificazione CA per l'interfaccia interna tramite MMC</span><span class="sxs-lookup"><span data-stu-id="f4e4a-140">To export the CA certification chain for the internal interface using MMC</span></span>

1.  <span data-ttu-id="f4e4a-141">È possibile esportare il certificato radice della CA da qualsiasi computer aggiunto a un dominio utilizzando Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="f4e4a-141">You can export the CA root certificate from any domain joined machine using the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="f4e4a-142">A tale scopo, fare clic sul pulsante **Start**, scegliere **Esegui** e quindi digitare **MMC**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-142">Click **Start**, click **Run**, and then type **MMC**.</span></span>

2.  <span data-ttu-id="f4e4a-143">Nella console MMC fare clic su **File** e quindi su **Aggiungi/Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-143">In the MMC console, click **File**, click **Add/Remove**.</span></span>

3.  <span data-ttu-id="f4e4a-p108">Nell'elenco della finestra di dialogo **Aggiungi o rimuovi snap-in** selezionare **Certificati** e quindi fare clic su **Aggiungi**. Quando richiesto, selezionare **Account del computer**. Nella finestra di dialogo **Selezione computer** selezionare **Computer locale**. Fare clic su **Fine**. Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-p108">From the **Add or Remove Snap-ins** dialog list, select **Certificates**, then click **Add**. When prompted, select **Computer Account**. On the **Select Computer** dialog, select **Local Computer**. Click **Finish**. Click **OK**.</span></span>

4.  <span data-ttu-id="f4e4a-p109">Espandere **Certificati (computer locale)**. Espandere **Autorità di certificazione radice attendibili** e selezionare **Certificati**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-p109">Expand **Certificates (Local Computer)**. Expand **Trusted Root Certification Authorities**, select **Certificates**.</span></span>

5.  <span data-ttu-id="f4e4a-p110">Fare clic sul certificato radice emesso dalla CA. Fare clic con il pulsante destro del mouse sul certificato, scegliere **Tutte le attività** e quindi **Esporta**. Verrà aperta l'**Esportazione guidata certificati**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-p110">Click the root certificate issued by your CA. Right click the certificate, select **All Tasks**, select **Export**. The **Certificate Export Wizard** will open.</span></span>

6.  <span data-ttu-id="f4e4a-154">Nell'**Esportazione guidata certificati** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-154">In the **Certificate Export Wizard**, click **Next**.</span></span>

7.  <span data-ttu-id="f4e4a-155">Nella finestra di dialogo **Formato file di esportazione** selezionare un formato per l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-155">On the **Export File Format** dialog, select a format to export to.</span></span> <span data-ttu-id="f4e4a-156">È consigliabile utilizzare la **sintassi del messaggio crittografico standard \#– i certificati PKCS 7 (. P7B)**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-156">We recommend the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**.</span></span> <span data-ttu-id="f4e4a-157">Se si seleziona la **sintassi del messaggio crittografico standard – \#PKCS 7 Certificates (. P7B)**, selezionare la casella di controllo **Includi tutti i certificati nel percorso di certificazione, se possibile** , per esportare la catena di certificati, incluso il certificato della CA radice e tutti i certificati di CA intermedi.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-157">If you select the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**, select the **Include all certificates in the certification path if possible** checkbox to export the certificate chain, including the root CA certificate and any Intermediate CA certificates.</span></span> <span data-ttu-id="f4e4a-158">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-158">Click **Next**.</span></span>

8.  <span data-ttu-id="f4e4a-p112">Nella finestra di dialogo **File da esportare** digitare nell'apposito campo un percorso e un nome file (l'estensione predefinita è p7b) per il certificato esportato. Facoltativamente fare clic su **Sfoglia**, individuare una directory in cui inserire il certificato esportato e specificare un nome per tale certificato. Fare clic su **Salva**. Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-p112">On the **File to Export** dialog in the file name entry, type a path and file name (default extension is .p7b) for the exported certificate. Optionally, click **Browse**, locate a directory to place the exported certificate in and provide a name for the exported certificate. Click **Save**. Click **Next**.</span></span>

9.  <span data-ttu-id="f4e4a-p113">Esaminare il riepilogo delle azioni e fare clic su **Fine** per completare l'esportazione del certificato. Fare clic su **OK** per confermare l'avvenuta esecuzione dell'esportazione.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-p113">Review the summary of actions, and click **Finish** to complete the export of the certificate. Click **OK** to confirm the successful export.</span></span>

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a><span data-ttu-id="f4e4a-165">Per importare la catena di certificazione della CA per l'interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="f4e4a-165">To import the CA certification chain for the internal interface</span></span>

1.  <span data-ttu-id="f4e4a-166">In ogni server perimetrale fare clic sul pulsante **Start**, scegliere **Esegui**, digitare **mmc** nella casella **Apri** e quindi fare clic su **OK** per aprire Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="f4e4a-166">On each Edge Server, open the Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="f4e4a-167">Scegliere **Aggiungi/Rimuovi snap-in** dal menu **File** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-167">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="f4e4a-168">Nella casella **Aggiungi snap-in autonomo** fare clic su **Certificati** e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-168">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="f4e4a-169">Nella finestra di dialogo **Snap-in certificati** fare clic su **Account del computer** e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-169">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="f4e4a-170">Nella finestra di dialogo **Seleziona computer** assicurarsi che la casella di controllo **Computer locale (il computer su cui è in esecuzione questa console)** sia selezionata e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-170">In the **Select Computer** dialog box, ensure that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="f4e4a-171">Fare clic su **Chiudi** e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-171">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="f4e4a-172">Nell'albero della console espandere **Certificati (computer locale)**, fare clic con il pulsante destro del mouse su **Autorità di certificazione radice disponibile nell'elenco locale**, scegliere **Tutte le attività** e quindi **Importa**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-172">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, point to **All Tasks**, and then click **Import**.</span></span>

8.  <span data-ttu-id="f4e4a-173">In **File da importare** all'interno della procedura guidata specificare il nome del file del certificato, ovvero il nome specificato al momento del download della catena di certificazione CA per l'interfaccia interna nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-173">In the wizard, in **File to Import**, specify the file name of the certificate (that is, the name of that you specified when you downloaded the CA certification chain for the internal interface in the previous procedure).</span></span>

9.  <span data-ttu-id="f4e4a-174">Ripetere questa procedura in ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-174">Repeat this procedure on each Edge Server.</span></span>

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a><span data-ttu-id="f4e4a-175">Per creare la richiesta di certificato per l'interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="f4e4a-175">To create the certificate request for the internal interface</span></span>

1.  <span data-ttu-id="f4e4a-176">In uno dei server perimetrali avviare la Distribuzione guidata e accanto a **Passaggio 3: Richiesta, installazione o assegnazione dei certificati** fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-176">On one of the Edge Servers, start the Deployment Wizard, and next to **Step 3: Request, Install, or Assign Certificates**, click **Run**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f4e4a-177">Se in una stessa posizione sono presenti più server perimetrali in pool, è possibile eseguire la Configurazione guidata certificati in uno qualsiasi del server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-177">If you have multiple Edge Servers in one location in a pool, you can run the Certificate Wizard on any one of the Edge Servers.</span></span><BR><span data-ttu-id="f4e4a-178">Dopo la prima esecuzione del passaggio 3, il pulsante viene modificato in <STRONG>Riesegui</STRONG>. Il segno di spunta di colore verde che indica il completamento dell'attività viene visualizzato solo dopo la richiesta, l'installazione e l'assegnazione di tutti i certificati.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-178">After you run Step 3 the first time, the button changes to <STRONG>Run again</STRONG>, and a green check mark that indicates successful completion of the task is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

    
    </div>

2.  <span data-ttu-id="f4e4a-179">Nella pagina **Attività certificato disponibili** fare clic su **Crea una nuova richiesta di certificato**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-179">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="f4e4a-180">Nella pagina **Richiesta di certificato** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-180">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="f4e4a-181">Nella pagina **Richieste immediate o ritardate** fare clic su **Prepara la richiesta per l'invio posticipato**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-181">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>

5.  <span data-ttu-id="f4e4a-182">Nella pagina **file richiesta di certificato** Digitare il percorso completo e il nome del file in cui si desidera salvare la richiesta, ad esempio **c\\: CERT\_Internal\_Edge. cer**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-182">On the **Certificate Request File** page, type the full path and file name to which the request is to be saved (for example, **c:\\cert\_internal\_edge.cer**).</span></span>

6.  <span data-ttu-id="f4e4a-183">Nella pagina **Specifica modello di certificato alternativo** per utilizzare un modello diverso dal modello WebServer predefinito selezionare la casella di controllo **Utilizza modello di certificato alternativo per l'autorità di certificazione selezionata**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-183">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>

7.  <span data-ttu-id="f4e4a-184">Nella pagina **Impostazioni nome e sicurezza** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4e4a-184">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="f4e4a-185">In **Nome descrittivo** digitare il nome da visualizzare per il certificato, ad esempio Server perimetrale interno.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-185">In **Friendly name**, type a display name for the certificate (for example, Internal Edge).</span></span>
    
      - <span data-ttu-id="f4e4a-186">In **Lunghezza bit** specificare la lunghezza in bit (di solito, l'impostazione predefinita **2048**).</span><span class="sxs-lookup"><span data-stu-id="f4e4a-186">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f4e4a-187">Una lunghezza in bit più alta offre maggiore sicurezza, ma influisce negativamente sulla velocità.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-187">Higher bit lengths offer more security, but they have a negative impact on speed.</span></span>

        
        </div>
    
      - <span data-ttu-id="f4e4a-188">Se è necessario che il certificato sia esportabile, selezionare la casella di controllo **Contrassegna come esportabile la chiave di certificato privata**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-188">If the certificate needs to be exportable, select the **Mark certificate private key as exportable** check box.</span></span>

8.  <span data-ttu-id="f4e4a-189">Nella pagina **Informazioni sull'organizzazione** digitare il nome per l'organizzazione e l'unità organizzativa, ad esempio una divisione o un reparto.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-189">On the **Organization Information** page, type the name for the organization and the organizational unit (OU) (for example, a division or department).</span></span>

9.  <span data-ttu-id="f4e4a-190">Nella pagina **Dati geografici** specificare le informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-190">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="f4e4a-191">Nella pagina **Nome soggetto / Nomi soggetto alternativi** sono visualizzate le informazioni che verranno inserite automaticamente mediante la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-191">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span>

11. <span data-ttu-id="f4e4a-192">Nella pagina **Configura nomi soggetto alternativi aggiuntivi** specificare eventuali nomi soggetto alternativi aggiuntivi richiesti.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-192">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

12. <span data-ttu-id="f4e4a-193">Nella pagina **Riepilogo richiesta** rivedere le informazioni relative al certificato che verranno utilizzate per la generazione della richiesta.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-193">On the **Request Summary** page, review the certificate information that is going to be used to generate the request.</span></span>

13. <span data-ttu-id="f4e4a-194">Dopo il completamento dell'esecuzione dei comandi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4e4a-194">After the commands complete, do the following:</span></span>
    
      - <span data-ttu-id="f4e4a-195">Per visualizzare il registro della richiesta di certificato, fare clic su **Visualizza registro**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-195">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="f4e4a-196">Per completare la richiesta del certificato, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-196">To complete the certificate request, click **Next**.</span></span>

14. <span data-ttu-id="f4e4a-197">Nella pagina **File richiesta di certificato** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4e4a-197">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="f4e4a-198">Per visualizzare il file di richiesta di firma del certificato (CSR) generato, fare clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-198">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="f4e4a-199">Per chiudere la procedura guidata, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-199">To close the wizard, click **Finish**.</span></span>

15. <span data-ttu-id="f4e4a-200">Inviare il file alla CA, tramite posta elettronica o un altro metodo supportato dall'organizzazione per la CA globale (enterprise). Alla ricezione del file di risposta copiare il nuovo certificato nel computer in modo che sia disponibile per l'importazione.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-200">Submit this file to your CA (by email or other method supported by your organization for your enterprise CA) and, when you receive the response file, copy the new certificate to this computer so that it is available for import.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a><span data-ttu-id="f4e4a-201">Per importare il certificato per l'interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="f4e4a-201">To import the certificate for the internal interface</span></span>

1.  <span data-ttu-id="f4e4a-202">Accedere al server perimetrale in cui è stata creata la richiesta di certificato con un account membro del gruppo Administrators locale.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-202">Log on to the Edge Server on which you created the certificate request as a member of the local Administrators group.</span></span>

2.  <span data-ttu-id="f4e4a-203">Nella Distribuzione guidata, accanto a **Passaggio 3: Richiesta, installazione o assegnazione dei certificati**, fare clic su **Riesegui**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-203">In the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <span data-ttu-id="f4e4a-204">Dopo la prima esecuzione del passaggio 3, il pulsante viene modificato in **Riesegui**. Il segno di spunta di colore verde che indica il completamento dell'attività viene visualizzato solo dopo la richiesta l'installazione e l'assegnazione di tutti i certificati.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-204">After you run Step 3 the first time, the button changes to **Run again**, but a green check mark (indicating successful completion of the task) is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

3.  <span data-ttu-id="f4e4a-205">Nella pagina **Attività certificato disponibili** fare clic su **Importa un certificato da un file con estensione P7b, pfx o cer**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-205">On the **Available Certificate Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>

4.  <span data-ttu-id="f4e4a-206">Nella pagina **Importa certificato** digitare il percorso completo e il nome del file del certificato richiesto e ricevuto per il server perimetrale. In alternativa, fare clic su **Sfoglia** per individuare e selezionare il file.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-206">On the **Import Certificate** page, type the full path and file name of the certificate that you requested and received for the internal interface of this Edge Server (or, click **Browse** to locate and select the file).</span></span>

5.  <span data-ttu-id="f4e4a-207">Se si desidera importare certificati per altri membri del pool e un certificato contiene una chiave privata, selezionare la casella di controllo **Il file di certificato contiene una chiave di certificato privata** e specificare la password.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-207">If you are importing certificates for other members of the pool a certificate containing a private key, select the **Certificate file contains certifcate’s private key** check box and specify the password.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="f4e4a-208">Per esportare il certificato con la chiave privata per i server perimetrali in un pool</span><span class="sxs-lookup"><span data-stu-id="f4e4a-208">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="f4e4a-209">Accedere come membro del gruppo Administrators allo stesso server perimetrale in cui è stato importato il certificato.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-209">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="f4e4a-210">Fare clic sul pulsante **Start**, scegliere **Esegui** e digitare **MMC**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-210">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="f4e4a-211">Nella console MMC scegliere **Aggiungi/Rimuovi snap-in** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-211">From the MMC console, click **File**, click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="f4e4a-212">Nella pagina Aggiungi/Rimuovi snap-in fare clic su **Certificati** e su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-212">From Add or Remove Snap-ins page, click **Certificates**, click **Add**.</span></span>

5.  <span data-ttu-id="f4e4a-p114">Nella finestra di dialogo dello snap-in Certificati selezionare **Account del computer**. Fare clic su **Avanti**. In Seleziona computer selezionare **Computer locale (il computer in cui viene eseguita questa console)**. Fare clic su **Fine**. Fare clic su **OK** per completare la configurazione della console MMC console.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-p114">In the Certificates snap-in dialog, select **Computer account**. Click **Next**. In Select Computer, select **Local computer: (the computer this console is running on)**. Click **Finish**. Click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="f4e4a-p115">Fare doppio clic su **Certificati (computer locale)** per espandere gli archivi certificati. Fare doppio clic su **Personale** e quindi su **Certificati**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-p115">Double-click **Certificates (Local Computer)** to expand the certificate stores. Double-click **Personal**, then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f4e4a-p116">Se nell'archivio personale dei certificati non sono presenti certificati per il computer locale, al certificato importato non è associata alcuna chiave privata. Rivedere i passaggi della richiesta e dell'impostazione. Se il problema persiste, rivolgersi all'amministratore o al provider dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-p116">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported. Review the request and import steps. If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="f4e4a-p117">Nell'archivio personale dei certificati per il computer locale fare clic con il pulsante destro del mouse sul certificato che si desidera esportare. Scegliere **Tutte le attività** e quindi fare clic su **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-p117">In the Certificates Personal store for the local computer, right-click the certificate that you are exporting. Click **All Tasks**, click **Export**.</span></span>

8.  <span data-ttu-id="f4e4a-p118">Nell'Esportazione guidata certificati fare clic su **Avanti**. Selezionare **Sì, esporta la chiave privata**. Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-p118">In the Certificate Export Wizard, click **Next**. Select **Yes, export the private key**. Click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f4e4a-p119">Se l'opzione <STRONG>Sì, esporta la chiave privata</STRONG> non è disponibile, la chiave privata associata al certificato non è stata contrassegnata per l'esportazione. Per continuare l'esportazione, è necessario ripetere la richiesta di certificato, verificando che il certificato stesso sia contrassegnato per l'esportazione della chiave privata. Rivolgersi all'amministratore o al provider dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-p119">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export. You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export. Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="f4e4a-231">Nella finestra di dialogo formati file di esportazione selezionare **scambio di informazioni personali\#-PKCS 12 (. PFX)** e quindi selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4e4a-231">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="f4e4a-232">Se possibile, includi tutti i certificati nel percorso certificazione</span><span class="sxs-lookup"><span data-stu-id="f4e4a-232">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="f4e4a-233">Esporta tutte le proprietà estese</span><span class="sxs-lookup"><span data-stu-id="f4e4a-233">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="f4e4a-p120">Quando si esporta un certificato da un server perimetrale, non selezionare <STRONG>Elimina la chiave privata se l'esportazione ha esito positivo</STRONG>. In caso contrario, è necessario importare nel server perimetrale il certificato e la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-p120">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>. Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>
    
    <span data-ttu-id="f4e4a-236">Fare clic su **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-236">Click **Next** to continue.</span></span>

10. <span data-ttu-id="f4e4a-p121">Se si desidera assegnare una password per proteggere la chiave privata, digitare una password per la chiave privata. Reimmettere la password per conferma. Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-p121">If you want to assign password to protect the private key, type a password for the private key. Re-enter the password to confirm. Click **Next**.</span></span>

11. <span data-ttu-id="f4e4a-p122">Digitare un percorso e un nome di file per il certificato esportato Assegnare al file l'estensione pfx. Il percorso deve essere accessibile per tutti gli altri server perimetrali del pool o disponibile per il trasporto mediante supporto rimovibile, ad esempio un'unità flash USB. Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-p122">Type a path and file name for the exported certificate, using a file extension of .pfx. The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive. Click **Next**.</span></span>

12. <span data-ttu-id="f4e4a-p123">Esaminare il riepilogo nella finestra di dialogo Completamento dell'Esportazione guidata certificati. Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-p123">Review the summary on the Completing the Certificate Export Wizard dialog. Click **Finish**.</span></span>

13. <span data-ttu-id="f4e4a-245">Fare clic su **OK** nella finestra di dialogo di conclusione dell'esportazione.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-245">Click **OK** in the successful export dialog.</span></span>

14. <span data-ttu-id="f4e4a-246">Importare il file del certificato esportato negli altri server perimetrali seguendo i passaggi descritti nella procedura di [configurazione dei certificati per l'interfaccia perimetrale esterna per le procedure di Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f4e4a-246">Import the exported certificate file to the other Edge servers following the steps outlined in the [Set up certificates for the external edge interface for Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) procedures.</span></span>

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a><span data-ttu-id="f4e4a-247">Per assegnare il certificato interno nei server perimetrali</span><span class="sxs-lookup"><span data-stu-id="f4e4a-247">To assign the internal certificate on the Edge Servers</span></span>

1.  <span data-ttu-id="f4e4a-248">In ogni server perimetrale, nella Distribuzione guidata, accanto a **Passaggio 3: Richiesta, installazione o assegnazione dei certificati**, fare clic su **Riesegui**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-248">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="f4e4a-249">Nella pagina **Attività certificato disponibili** fare clic su **Assegna un certificato esistente**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-249">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="f4e4a-250">Nella pagina **Assegnazione certificato** selezionare **Edge Server interno** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-250">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>

4.  <span data-ttu-id="f4e4a-251">Nella pagina **Archivio certificati** selezionare il certificato importato con la procedura precedente per il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-251">On the **Certificate Store** page, select the certificate that you imported for the internal edge (from the previous procedure).</span></span>

5.  <span data-ttu-id="f4e4a-252">Nella pagina **Riepilogo assegnazione certificato** rivedere le impostazioni e quindi fare clic su **Avanti** per assegnare i certificati.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-252">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

6.  <span data-ttu-id="f4e4a-253">Nella pagina finale della procedura guidata fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-253">On the wizard completion page, click **Finish**.</span></span>

7.  <span data-ttu-id="f4e4a-254">Dopo aver assegnato il certificato del server perimetrale interno mediante questa procedura, aprire lo snap-in Certificati in ogni server, espandere **Certificati (computer locale)**, espandere **Personale**, fare clic su **Certificati** e quindi verificare che il certificato del server perimetrale interno sia presente nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-254">After using this procedure to assign the internal edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the internal edge certificate is listed.</span></span>

8.  <span data-ttu-id="f4e4a-255">Se la distribuzione include più server perimetrali, ripetere la procedura per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="f4e4a-255">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

