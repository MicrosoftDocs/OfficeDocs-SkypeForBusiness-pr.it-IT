---
title: "Lync Server 2013: Impostare i certificati per l'interfaccia perimetrale esterna"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2cb33a91d6609f9109e6416f5688d1b2ddfb9ed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a><span data-ttu-id="d2c87-102">Impostare i certificati per l'interfaccia perimetrale esterna per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2c87-102">Set up certificates for the external edge interface for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2c87-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="d2c87-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d2c87-104">Quando si esegue la creazione guidata certificato, verificare di avere effettuato l'accesso con un account membro di un gruppo a cui sono state assegnate le autorizzazioni appropriate per il tipo di modello di certificato che verrà usato.</span><span class="sxs-lookup"><span data-stu-id="d2c87-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="d2c87-105">Per impostazione predefinita, una richiesta di certificato di Lync Server utilizzerà il modello di certificato server Web.</span><span class="sxs-lookup"><span data-stu-id="d2c87-105">By default, a Lync Server certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="d2c87-106">Se si usa un account che è un membro del gruppo RTCUniversalServerAdmins per richiedere un certificato con questo modello, verificare che al gruppo siano state assegnate le autorizzazioni di registrazione necessarie per l'uso di tale modello.</span><span class="sxs-lookup"><span data-stu-id="d2c87-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="d2c87-107">Ogni Edge Server richiede un certificato pubblico nell'interfaccia tra la rete perimetrale e Internet e il nome dell'oggetto alternativo del certificato deve contenere i nomi esterni del servizio Access Edge e del servizio Web Conferencing Edge completamente nomi di dominio completi (FQDN).</span><span class="sxs-lookup"><span data-stu-id="d2c87-107">Each Edge Server requires a public certificate on the interface between the perimeter network and the Internet, and the certificate’s subject alternative name must contain the external names of the Access Edge service and Web Conferencing Edge service fully qualified domain names (FQDNs).</span></span>

<span data-ttu-id="d2c87-108">Per informazioni dettagliate su questo e altri requisiti per i certificati, vedere [requisiti di certificato per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="d2c87-108">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="d2c87-109">Per un elenco delle autorità di certificazione pubbliche che includono certificati che soddisfano i requisiti specifici per i certificati di comunicazioni unificate e che hanno collaborato con Microsoft per verificare che funzionino con la procedura guidata certificati di Lync Server 2013, vedere l'articolo 929395 della Microsoft Knowledge Base "partner certificati per le comunicazioni unificate per Exchange Server [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)e per Communications Server".</span><span class="sxs-lookup"><span data-stu-id="d2c87-109">For a list of public certification authorities (CAs) that provide certificates that comply with specific requirements for unified communications certificates and have partnered with Microsoft to ensure they work with the Lync Server 2013 Certificate Wizard, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a><span data-ttu-id="d2c87-110">Configurazione dei certificati sulle interfacce esterne</span><span class="sxs-lookup"><span data-stu-id="d2c87-110">Configuring Certificates on the External Interfaces</span></span>

<span data-ttu-id="d2c87-111">Per configurare un certificato nell'interfaccia esterna di Edge in un sito, usare le procedure descritte in questa sezione per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2c87-111">To set up a certificate on the external edge interface at a site, use the procedures in this section to do the following:</span></span>

  - <span data-ttu-id="d2c87-112">Creare la richiesta di certificato per l'interfaccia esterna del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d2c87-112">Create the certificate request for the external interface of the Edge Server.</span></span>

  - <span data-ttu-id="d2c87-113">Inviare la richiesta alla CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="d2c87-113">Submit the request to your public CA.</span></span>

  - <span data-ttu-id="d2c87-114">Importare il certificato per l'interfaccia esterna di ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d2c87-114">Import the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="d2c87-115">Assegnare il certificato per l'interfaccia esterna di ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d2c87-115">Assign the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="d2c87-116">Se la distribuzione include più Edge Server, esportare il certificato insieme alla relativa chiave privata e quindi copiarlo negli altri Edge Server.</span><span class="sxs-lookup"><span data-stu-id="d2c87-116">If your deployment includes multiple Edge Servers, export the certificate along with its private key, and then copy it to the other Edge Servers.</span></span> <span data-ttu-id="d2c87-117">Quindi, per ogni Edge Server, importalo e assegnalo come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d2c87-117">Then, for each Edge Server, import it and assign it as previously described.</span></span> <span data-ttu-id="d2c87-118">Ripetere questa procedura per ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d2c87-118">Repeat this procedure for each Edge Server.</span></span>

<span data-ttu-id="d2c87-119">È possibile richiedere certificati pubblici direttamente da un'autorità di certificazione (CA) pubblica, ad esempio dal sito Web di una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="d2c87-119">You can request public certificates directly from a public certification authority (CA) (such as from the website of a public CA).</span></span> <span data-ttu-id="d2c87-120">Le procedure descritte in questa sezione usano la creazione guidata certificato per la maggior parte delle attività di certificato.</span><span class="sxs-lookup"><span data-stu-id="d2c87-120">The procedures in this section use the Certificate Wizard for most certificate tasks.</span></span> <span data-ttu-id="d2c87-121">Se si è scelto di richiedere un certificato direttamente da una CA pubblica, sarà necessario modificare ogni procedura in modo appropriato per richiedere, trasportare e importare il certificato e anche per importare la catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="d2c87-121">If you chose to request a certificate directly from a public CA, then you will need to modify each procedure as appropriate to request, transport, and import the certificate and also to import the certificate chain.</span></span>

<span data-ttu-id="d2c87-122">Quando si richiede un certificato da una CA esterna, le credenziali fornite devono avere diritti per richiedere un certificato da tale autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="d2c87-122">When you request a certificate from an External CA, the credentials provided must have rights to request a certificate from that CA.</span></span> <span data-ttu-id="d2c87-123">Ogni autorità di certificazione ha un criterio di sicurezza che definisce le credenziali, ovvero i nomi di utenti e gruppi specifici, che possono richiedere, emettere, gestire o leggere i certificati.</span><span class="sxs-lookup"><span data-stu-id="d2c87-123">Each CA has a security policy that defines which credentials (that is, specific user and group names) are allowed to request, issue, manage, or read certificates.</span></span>

<span data-ttu-id="d2c87-124">Se si decide di usare i certificati Microsoft Management Console (MMC) per importare la catena di certificati e il certificato, è necessario importarli nell'archivio certificati per il computer.</span><span class="sxs-lookup"><span data-stu-id="d2c87-124">If you decide to use the Certificates Microsoft Management Console (MMC) to import the certificate chain and certificate, you must import them to the certificate store for the computer.</span></span> <span data-ttu-id="d2c87-125">Se vengono importati nell'archivio certificati dell'utente o del servizio, il certificato non sarà disponibile per l'assegnazione nella procedura guidata certificato di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d2c87-125">If you import them to the user or service certificate store, the certificate will not be available for assignment in the Lync Server 2013 Certificate Wizard.</span></span>

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="d2c87-126">Per creare la richiesta di certificato per l'interfaccia esterna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="d2c87-126">To create the certificate request for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="d2c87-127">Nel server perimetro, nella distribuzione guidata, accanto a **passaggio 3: richiedere, installare o assegnare certificati**, fare di nuovo clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-127">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d2c87-128">Se l'organizzazione vuole supportare la connettività di messaggistica istantanea pubblica con AOL, non è possibile usare la distribuzione guidata di Lync Server per richiedere il certificato.</span><span class="sxs-lookup"><span data-stu-id="d2c87-128">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="d2c87-129">Eseguire invece la procedura descritta nella sezione "per creare una richiesta di certificato per l'interfaccia esterna dell'Edge Server per supportare la connettività di messaggistica istantanea pubblica con AOL" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d2c87-129">Instead, perform the steps in the “To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL” procedure later in this topic.</span></span><BR><span data-ttu-id="d2c87-130">Se si hanno più Edge Server in una posizione in un pool, è possibile eseguire la configurazione guidata certificati di Lync Server 2013 in uno dei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="d2c87-130">If you have multiple Edge Servers in one location in a pool, you can run the Lync Server 2013 Certificate Wizard on any one of the Edge Servers.</span></span>

    
    </div>

2.  <span data-ttu-id="d2c87-131">Nella pagina **attività certificato disponibili** fare clic su **Crea una nuova richiesta di certificato**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-131">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="d2c87-132">Nella pagina **richiesta certificato** fare clic su **certificato bordo esterno**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-132">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="d2c87-133">Nella pagina **richiesta posticipata o immediata** selezionare la casella di controllo **prepara la richiesta ora, ma inviarla in seguito** .</span><span class="sxs-lookup"><span data-stu-id="d2c87-133">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="d2c87-134">Nella pagina **file di richiesta certificato** Digitare il percorso completo e il nome file del file in cui deve essere salvata la richiesta, ad esempio c:\\CERT\_exernal\_Edge. cer.</span><span class="sxs-lookup"><span data-stu-id="d2c87-134">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="d2c87-135">Nella pagina **Specifica modello di certificato alternativo** , per usare un modello diverso da quello predefinito del modello webserver, selezionare la casella di controllo **Usa il modello di certificato alternativo per l'autorità di certificazione selezionata** .</span><span class="sxs-lookup"><span data-stu-id="d2c87-135">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="d2c87-136">Nella pagina **impostazioni di sicurezza e nome** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2c87-136">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="d2c87-137">In **nome descrittivo**Digitare un nome visualizzato per il certificato.</span><span class="sxs-lookup"><span data-stu-id="d2c87-137">In **Friendly name**, type a display name for the certificate.</span></span>
    
      - <span data-ttu-id="d2c87-138">In **bit length**specificare la lunghezza in bit (in genere, il valore predefinito è **2048**).</span><span class="sxs-lookup"><span data-stu-id="d2c87-138">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
    
      - <span data-ttu-id="d2c87-139">Verificare che la casella **di controllo contrassegna la chiave privata del certificato come esportabile** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="d2c87-139">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="d2c87-140">Nella pagina **informazioni organizzazione** Digitare il nome dell'organizzazione e dell'unità organizzativa, ad esempio divisione o reparto.</span><span class="sxs-lookup"><span data-stu-id="d2c87-140">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="d2c87-141">Nella pagina **informazioni geografiche** specificare le informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="d2c87-141">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="d2c87-142">Nella pagina **nome oggetto/nomi oggetto alternativo** vengono visualizzate le informazioni che verranno inserite automaticamente dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="d2c87-142">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="d2c87-143">Se sono necessari altri nomi alternativi per l'oggetto, è necessario specificarli nei due passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="d2c87-143">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="d2c87-144">Nell' **impostazione del dominio SIP nella pagina nome alternativo oggetto (sans)** selezionare la casella di controllo Domain per aggiungere un SIP. \<SipDomain\> voce nell'elenco nomi alternativi oggetto.</span><span class="sxs-lookup"><span data-stu-id="d2c87-144">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="d2c87-145">Nella pagina **Configura altri nomi alternativi oggetto** specificare eventuali altri nomi alternativi per gli argomenti necessari.</span><span class="sxs-lookup"><span data-stu-id="d2c87-145">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

13. <span data-ttu-id="d2c87-146">Nella pagina **Riepilogo richieste** verificare le informazioni sul certificato da usare per generare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="d2c87-146">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="d2c87-147">Dopo aver completato i comandi, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2c87-147">After the commands finish running, do the following:</span></span>
    
      - <span data-ttu-id="d2c87-148">Per visualizzare il log per la richiesta di certificato, fare clic su **Visualizza log**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-148">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="d2c87-149">Per completare la richiesta di certificato, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-149">To complete the certificate request, click **Next**.</span></span>

15. <span data-ttu-id="d2c87-150">Nella pagina **file di richiesta certificato** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2c87-150">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="d2c87-151">Per visualizzare il file della richiesta di firma del certificato (CSR) generato, fare clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-151">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="d2c87-152">Per chiudere la procedura guidata, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-152">To close the wizard, click **Finish**.</span></span>

16. <span data-ttu-id="d2c87-153">Copiare il file di output in un percorso in cui è possibile inviarlo alla CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="d2c87-153">Copy the output file to a location where you can submit it to the public CA.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="d2c87-154">Per creare una richiesta di certificato per l'interfaccia esterna di Edge Server per supportare la connettività di messaggistica istantanea pubblica con AOL</span><span class="sxs-lookup"><span data-stu-id="d2c87-154">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="d2c87-155">Quando il modello richiesto è disponibile per la CA, usare il cmdlet di Windows PowerShell seguente da su Edge Server per richiedere il certificato:</span><span class="sxs-lookup"><span data-stu-id="d2c87-155">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate:</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="d2c87-156">Il nome del certificato predefinito del modello fornito in Lync Server 2013 è Web Server.</span><span class="sxs-lookup"><span data-stu-id="d2c87-156">The default certificate name of the template provided in Lync Server 2013 is Web Server.</span></span> <span data-ttu-id="d2c87-157">Specifica il nome \<\> del modello solo se devi usare un modello diverso dal modello predefinito.</span><span class="sxs-lookup"><span data-stu-id="d2c87-157">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d2c87-158">Se l'organizzazione vuole supportare la connettività di messaggistica istantanea pubblica con AOL, è necessario usare Windows PowerShell invece della procedura guidata certificato per richiedere che il certificato venga assegnato al bordo esterno per il servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="d2c87-158">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="d2c87-159">Questo perché il modello di server Web Lync Server 2013 usato dalla creazione guidata certificato per richiedere un certificato non supporta la configurazione EKU client.</span><span class="sxs-lookup"><span data-stu-id="d2c87-159">This is because the Lync Server 2013 Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="d2c87-160">Prima di usare Windows PowerShell per creare il certificato, l'amministratore della CA deve creare e distribuire un nuovo modello che supporti EKU client.</span><span class="sxs-lookup"><span data-stu-id="d2c87-160">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a><span data-ttu-id="d2c87-161">Per inviare una richiesta a un'autorità di certificazione pubblica</span><span class="sxs-lookup"><span data-stu-id="d2c87-161">To submit a request to a public certification authority</span></span>

1.  <span data-ttu-id="d2c87-162">Aprire il file di output.</span><span class="sxs-lookup"><span data-stu-id="d2c87-162">Open the output file.</span></span>

2.  <span data-ttu-id="d2c87-163">Copiare e incollare il contenuto della richiesta di firma del certificato (CSR).</span><span class="sxs-lookup"><span data-stu-id="d2c87-163">Copy and paste the contents of the Certificate Signing Request (CSR).</span></span>

3.  <span data-ttu-id="d2c87-164">Se richiesto, specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d2c87-164">If prompted, specify the following:</span></span>
    
      - <span data-ttu-id="d2c87-165">**Microsoft** come piattaforma server.</span><span class="sxs-lookup"><span data-stu-id="d2c87-165">**Microsoft** as the server platform.</span></span>
    
      - <span data-ttu-id="d2c87-166">**IIS** come versione.</span><span class="sxs-lookup"><span data-stu-id="d2c87-166">**IIS** as the version.</span></span>
    
      - <span data-ttu-id="d2c87-167">**Server Web** come tipo di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="d2c87-167">**Web Server** as the usage type.</span></span>
    
      - <span data-ttu-id="d2c87-168">**PKCS7** come formato di risposta.</span><span class="sxs-lookup"><span data-stu-id="d2c87-168">**PKCS7** as the response format.</span></span>

4.  <span data-ttu-id="d2c87-169">Quando la CA pubblica ha verificato le proprie informazioni, viene visualizzato un messaggio di posta elettronica contenente il testo necessario per il certificato.</span><span class="sxs-lookup"><span data-stu-id="d2c87-169">When the public CA has verified your information, you will receive an email message containing text required for your certificate.</span></span>

5.  <span data-ttu-id="d2c87-170">Copiare il testo dal messaggio di posta elettronica e salvare il contenuto in un file di testo (txt) nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="d2c87-170">Copy the text from the email message and save the contents in a text file (.txt) on your local computer.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="d2c87-171">Per importare il certificato per l'interfaccia esterna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="d2c87-171">To import the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="d2c87-172">Accedere come membro del gruppo Administrators allo stesso Edge Server in cui è stata creata la richiesta di certificato.</span><span class="sxs-lookup"><span data-stu-id="d2c87-172">Log on as a member of the Administrators group to the same Edge Server on which you created the certificate request.</span></span>

2.  <span data-ttu-id="d2c87-173">Nella distribuzione guidata, nella pagina **Deploy Edge Server** , accanto a **passaggio 3: richiedere, installare o assegnare certificati**, fare di nuovo clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-173">In the Deployment Wizard, on the **Deploy Edge Server** page, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

3.  <span data-ttu-id="d2c87-174">Nella pagina **attività certificato disponibili** fare clic su **Importa un certificato da un file con estensione p7b, pfx o CER**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-174">On the **Available Certificate Tasks** page, click **Import a certificate from a .p7b, pfx or .cer file**.</span></span>

4.  <span data-ttu-id="d2c87-175">Nella pagina **Importa certificato** fare clic su **Sfoglia** per individuare e selezionare il certificato richiesto per l'interfaccia esterna del server perimetrale oppure digitare il percorso completo e il nome del file.</span><span class="sxs-lookup"><span data-stu-id="d2c87-175">On the **Import Certificate** page, click **Browse** to locate and select the certificate that you requested for the external interface of the Edge Server (or, you can type the full path and file name).</span></span> <span data-ttu-id="d2c87-176">Se il certificato contiene una chiave privata, selezionare il **file di certificato contiene la chiave privata del certificato** e digitare la password per la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="d2c87-176">If the certificate contains a private key, select **Certificate file contains certificate’s private key** and type the password for the private key.</span></span> <span data-ttu-id="d2c87-177">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-177">Click **Next**.</span></span>

5.  <span data-ttu-id="d2c87-178">Nella pagina di **Riepilogo importa certificato** esaminare il riepilogo e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-178">On **Import Certificate Summary** page, review the summary and then click **Next**.</span></span>

6.  <span data-ttu-id="d2c87-179">Per **eseguire i comandi**, esaminare i risultati dell'importazione, fare clic su **Visualizza log** per altre informazioni in base alle esigenze e quindi fare clic su **fine** per completare l'importazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="d2c87-179">On **Executing Commands**, review the results of the import, click **View Log** for more information as needed, and then click **Finish** to complete the certificate import.</span></span>

7.  <span data-ttu-id="d2c87-180">Se si sta configurando un pool di Edge Server, esportare il certificato con la relativa chiave privata come indicato nella procedura "per esportare il certificato con la chiave privata per i server perimetrali in un pool" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d2c87-180">If you are configuring an Edge Server pool, export the certificate with its private key as outlined in the “To export the certificate with the private key for Edge Servers in a pool” procedure later in this topic.</span></span> <span data-ttu-id="d2c87-181">Copiare il file di certificato esportato negli altri Edge Server e importarlo nell'archivio del computer in ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d2c87-181">Copy the exported certificate file to the other Edge Servers, and import it into the computer store on each Edge Server.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="d2c87-182">Per esportare il certificato con la chiave privata per Edge Server in un pool</span><span class="sxs-lookup"><span data-stu-id="d2c87-182">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="d2c87-183">Accedere come membro del gruppo Administrators allo stesso Edge Server in cui è stato importato il certificato.</span><span class="sxs-lookup"><span data-stu-id="d2c87-183">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="d2c87-184">Fare clic sul pulsante **Start**, scegliere **Esegui**e digitare **MMC**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-184">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="d2c87-185">Nella console Microsoft Management Console (MMC) fare clic su **file**e quindi su **Aggiungi/Rimuovi snap-in**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-185">In the Microsoft Management Console (MMC) console, click **File**, and then click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="d2c87-186">In **Aggiungi o Rimuovi snap-** in fare clic su **certificati**e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-186">In **Add or Remove Snap-ins**, click **Certificates**, and then click **Add**.</span></span>

5.  <span data-ttu-id="d2c87-187">Nella finestra di dialogo **certificati** selezionare **account computer**, fare clic **su Avanti**, selezionare **computer locale: (il computer in cui è in esecuzione la console)** in **selezionare il computer**, fare clic su **fine** e quindi su **OK** per completare la configurazione della console MMC.</span><span class="sxs-lookup"><span data-stu-id="d2c87-187">In the **Certificates** dialog box, select **Computer account**, click **Next**, select **Local computer: (the computer this console is running on)** in **Select Computer**, click **Finish** and then click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="d2c87-188">Fare doppio clic su **certificati (computer locale)** per espandere gli archivi di certificati, fare doppio clic su **personale**e quindi fare doppio clic su **certificati**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-188">Double-click **Certificates (Local Computer)** to expand the certificate stores, double-click **Personal**, and then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d2c87-189">Se non ci sono certificati nell'archivio personale certificati per il computer locale, non esiste alcuna chiave privata associata al certificato importato.</span><span class="sxs-lookup"><span data-stu-id="d2c87-189">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported.</span></span> <span data-ttu-id="d2c87-190">Esaminare la procedura di richiesta e importazione.</span><span class="sxs-lookup"><span data-stu-id="d2c87-190">Review the request and import steps.</span></span> <span data-ttu-id="d2c87-191">Se il problema persiste, contattare l'amministratore o il provider dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="d2c87-191">If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="d2c87-192">Nell' **archivio personale certificati per il computer locale**fare clic con il pulsante destro del mouse sul certificato che si sta esportando, scegliere **tutte le attività**e quindi fare clic su **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-192">In the **Certificates Personal store for the local computer**, right-click the certificate that you are exporting, click **All Tasks**, and then click **Export**.</span></span>

8.  <span data-ttu-id="d2c87-193">Nell'esportazione guidata certificati fare clic su **Avanti**, selezionare **Sì, esportare la chiave privata**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-193">In the Certificate Export Wizard, click **Next**, select **Yes, export the private key**, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d2c87-194">Se la selezione <STRONG>Sì, Esporta la chiave privata</STRONG> non è disponibile, la chiave privata associata al certificato non è stata contrassegnata per l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="d2c87-194">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export.</span></span> <span data-ttu-id="d2c87-195">Sarà necessario richiedere di nuovo il certificato, assicurandosi che il certificato sia contrassegnato per consentire l'esportazione della chiave privata prima di poter continuare con l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="d2c87-195">You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export.</span></span> <span data-ttu-id="d2c87-196">Contattare l'amministratore o il provider dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="d2c87-196">Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="d2c87-197">Nella finestra di dialogo Esporta formati di file selezionare **Personal Information Exchange-\#PKCS 12 (. PFX)** e quindi selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2c87-197">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="d2c87-198">Includere tutti i certificati nel percorso di certificazione, se possibile</span><span class="sxs-lookup"><span data-stu-id="d2c87-198">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="d2c87-199">Esportare tutte le proprietà estese</span><span class="sxs-lookup"><span data-stu-id="d2c87-199">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="d2c87-200">Quando si esporta il certificato da un server perimetrale, non selezionare <STRONG>Elimina la chiave privata se l'esportazione ha esito positivo</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d2c87-200">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>.</span></span> <span data-ttu-id="d2c87-201">Se si seleziona questa opzione, è necessario importare il certificato e la chiave privata in questo server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d2c87-201">Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>

10. <span data-ttu-id="d2c87-202">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-202">Click **Next**.</span></span>

11. <span data-ttu-id="d2c87-203">Digitare una password per la chiave privata, digitare di nuovo la password per confermare e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-203">Type a password for the private key, type the password again to confirm, and then click **Next**.</span></span>

12. <span data-ttu-id="d2c87-204">Digitare un percorso e un nome di file per il certificato esportato, usando un'estensione di file PFX.</span><span class="sxs-lookup"><span data-stu-id="d2c87-204">Type a path and file name for the exported certificate, using a file extension of .pfx.</span></span> <span data-ttu-id="d2c87-205">Il percorso deve essere accessibile a tutti gli altri Edge Server nel pool o disponibile per il trasporto tramite supporti rimovibili, ad esempio un'unità flash USB.</span><span class="sxs-lookup"><span data-stu-id="d2c87-205">The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive.</span></span> <span data-ttu-id="d2c87-206">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-206">Click **Next**.</span></span>

13. <span data-ttu-id="d2c87-207">Esaminare il riepilogo in **completamento dell'esportazione guidata certificati**e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-207">Review the summary in **Completing the Certificate Export Wizard**, and then click **Finish**.</span></span>

14. <span data-ttu-id="d2c87-208">Nella finestra di dialogo Esporta completata fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-208">In the successful export dialog box, click **OK**.</span></span>

15. <span data-ttu-id="d2c87-209">Importare il file di certificato esportato negli altri Edge Server seguendo i passaggi descritti nella procedura "per importare il certificato per l'interfaccia esterna del server perimetrale" più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d2c87-209">Import the exported certificate file to the other Edge servers following the steps outlined in the “To import the certificate for the external interface of the Edge Server” procedure earlier in this topic.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="d2c87-210">Per assegnare il certificato per l'interfaccia esterna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="d2c87-210">To assign the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="d2c87-211">In ogni server perimetrale, nella distribuzione guidata, accanto a **passaggio 3: richiedere, installare o assegnare certificati**, fare di **nuovo**clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="d2c87-211">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="d2c87-212">Nella pagina **attività certificato disponibili** fare clic su **assegna un certificato esistente**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-212">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="d2c87-213">Nella pagina **assegnazione certificato** fare clic su **Certificato perimetro esterno** e selezionare la casella di controllo **usi avanzati dei certificati** .</span><span class="sxs-lookup"><span data-stu-id="d2c87-213">On the **Certificate Assignment** page, click **External Edge Certificate** and select the **Advanced Certificate Usages** check box.</span></span>

4.  <span data-ttu-id="d2c87-214">Nella pagina **usi avanzati certificati** selezionare tutte le caselle di controllo per assegnare il certificato per tutti gli usi.</span><span class="sxs-lookup"><span data-stu-id="d2c87-214">On the **Advanced Certificate Usages** page, select all check boxes to assign the certificate for all usages.</span></span>

5.  <span data-ttu-id="d2c87-215">Nella pagina **archivio certificati** selezionare il certificato pubblico richiesto e importato per l'interfaccia esterna del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d2c87-215">On the **Certificate Store** page, select the public certificate that you requested and imported for the external interface of the Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d2c87-216">Se il certificato richiesto e importato non è presente nell'elenco, uno dei metodi per la ripresa dei problemi consiste nel verificare che il nome dell'oggetto e i nomi alternativi oggetto del certificato soddisfino tutti i requisiti per il certificato e, se è stato importato manualmente il certificato e catena di certificati invece di usare le procedure descritte in precedenza, il certificato si trova nell'archivio certificati corretto, ovvero nell'archivio certificati del computer, non nell'archivio certificati dell'utente o del servizio.</span><span class="sxs-lookup"><span data-stu-id="d2c87-216">If the certificate you requested and imported is not in the list, one of the trouble shooting methods is to verify that subject name and subject alternative names of the certificate meet all requirements for the certificate and, if you manually imported the certificate and certificate chain instead of using the preceding procedures, that the certificate is in the correct certificate store (the computer certificate store, not the user or service certificate store).</span></span>

    
    </div>

6.  <span data-ttu-id="d2c87-217">Nella pagina **Riepilogo assegnazione certificati** verificare le impostazioni e quindi fare clic su **Avanti** per assegnare i certificati.</span><span class="sxs-lookup"><span data-stu-id="d2c87-217">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

7.  <span data-ttu-id="d2c87-218">Nella pagina Completamento procedura guidata fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="d2c87-218">On the wizard completion page, click **Finish**.</span></span>

8.  <span data-ttu-id="d2c87-219">Dopo aver usato questa procedura per assegnare il certificato Edge, aprire lo snap-in certificato in ogni server, espandere **certificati (computer locale)**, espandere **personale**, fare clic su **certificati**e quindi verificare nel riquadro dei dettagli che il certificato è elencato.</span><span class="sxs-lookup"><span data-stu-id="d2c87-219">After using this procedure to assign the edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the certificate is listed.</span></span>

9.  <span data-ttu-id="d2c87-220">Se la distribuzione include più Edge Server, ripetere questa procedura per ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d2c87-220">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

