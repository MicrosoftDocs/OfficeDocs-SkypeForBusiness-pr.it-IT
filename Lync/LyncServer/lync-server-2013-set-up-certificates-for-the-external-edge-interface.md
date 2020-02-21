---
title: "Lync Server 2013: configurare i certificati per l'interfaccia perimetrale esterna"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec2bad8f01e773d50f8d722ddbbf4be0757cb31d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a><span data-ttu-id="cbcfe-102">Configurare i certificati per l'interfaccia perimetrale esterna per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbcfe-102">Set up certificates for the external edge interface for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbcfe-103">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="cbcfe-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cbcfe-104">Quando si esegue la Configurazione guidata certificati, verificare di aver eseguito l'accesso con un account membro di un gruppo a cui sono state assegnate le autorizzazioni appropriate per il tipo di modello di certificato che verrà utilizzato.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="cbcfe-105">Per impostazione predefinita, una richiesta di certificato di Lync Server utilizzerà il modello di certificato del server Web.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-105">By default, a Lync Server certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="cbcfe-106">Se per la richiesta di certificato con questo modello si utilizza un account membro del gruppo RTCUniversalServerAdmins, verificare che al gruppo siano assegnate le autorizzazioni di registrazione necessarie per l'utilizzo del modello.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="cbcfe-107">Per ogni server perimetrale è necessario un certificato pubblico nell'interfaccia tra la rete perimetrale e Internet e il nome alternativo soggetto del certificato deve contenere i nomi esterni dei nomi di dominio completi (FQDN) del servizio Access Edge e del servizio Web Conferencing Edge.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-107">Each Edge Server requires a public certificate on the interface between the perimeter network and the Internet, and the certificate’s subject alternative name must contain the external names of the Access Edge service and Web Conferencing Edge service fully qualified domain names (FQDNs).</span></span>

<span data-ttu-id="cbcfe-108">Per informazioni dettagliate su questo e altri requisiti per i certificati, vedere [requisiti dei certificati per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="cbcfe-108">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="cbcfe-109">Per un elenco delle autorità di certificazione pubbliche che forniscono certificati conformi ai requisiti specifici per i certificati di comunicazione unificata e che hanno collaborato con Microsoft per verificare che funzionino con la configurazione guidata certificati di Lync Server 2013, vedere l'articolo 929395 della Microsoft Knowledge Base "partner di certificati per comunicazioni unificate per Exchange Server [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)e per Communications Server" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-109">For a list of public certification authorities (CAs) that provide certificates that comply with specific requirements for unified communications certificates and have partnered with Microsoft to ensure they work with the Lync Server 2013 Certificate Wizard, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a><span data-ttu-id="cbcfe-110">Configurazione dei certificati nelle interfacce esterne</span><span class="sxs-lookup"><span data-stu-id="cbcfe-110">Configuring Certificates on the External Interfaces</span></span>

<span data-ttu-id="cbcfe-111">Per configurare un certificato sull'interfaccia perimetrale esterna di un sito, utilizzare le procedure in questa sezione per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cbcfe-111">To set up a certificate on the external edge interface at a site, use the procedures in this section to do the following:</span></span>

  - <span data-ttu-id="cbcfe-112">Creare la richiesta di certificato per l'interfaccia esterna del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-112">Create the certificate request for the external interface of the Edge Server.</span></span>

  - <span data-ttu-id="cbcfe-113">Inviare la richiesta alla CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-113">Submit the request to your public CA.</span></span>

  - <span data-ttu-id="cbcfe-114">Importare il certificato per l'interfaccia esterna di ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-114">Import the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="cbcfe-115">Assegnare il certificato per l'interfaccia esterna di ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-115">Assign the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="cbcfe-p102">Se la distribuzione include più server perimetrali, esportare il certificato insieme alla relativa chiave privata, quindi copiarlo negli altri server perimetrali. Per ogni server perimetrale, quindi, importarlo e assegnarlo come descritto in precedenza. Ripetere questa procedura per ogni Edge Server.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-p102">If your deployment includes multiple Edge Servers, export the certificate along with its private key, and then copy it to the other Edge Servers. Then, for each Edge Server, import it and assign it as previously described. Repeat this procedure for each Edge Server.</span></span>

<span data-ttu-id="cbcfe-p103">È possibile richiedere certificati pubblici direttamente a un'autorità di certificazione (CA) pubblica, ad esempio dal sito Web di una CA pubblica. Le procedure in questa sezione utilizzano la Configurazione guidata certificati per la maggior parte delle attività correlate ai certificati. Se si sceglie di richiedere un certificato direttamente a una CA pubblica, sarà necessario modificare ogni procedura nel modo appropriato per richiedere, trasferire e importare il certificato, nonché importare la catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-p103">You can request public certificates directly from a public certification authority (CA) (such as from the website of a public CA). The procedures in this section use the Certificate Wizard for most certificate tasks. If you chose to request a certificate directly from a public CA, then you will need to modify each procedure as appropriate to request, transport, and import the certificate and also to import the certificate chain.</span></span>

<span data-ttu-id="cbcfe-p104">Quando si richiede un certificato a una CA esterna, le credenziali fornite devono disporre dei diritti necessari per richiedere un certificato a tale CA. Per ogni CA esistono criteri di sicurezza che definiscono le credenziali, ovvero i nomi di utenti e gruppi specifici, cui è consentito richiedere, emettere, gestire o leggere certificati.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-p104">When you request a certificate from an External CA, the credentials provided must have rights to request a certificate from that CA. Each CA has a security policy that defines which credentials (that is, specific user and group names) are allowed to request, issue, manage, or read certificates.</span></span>

<span data-ttu-id="cbcfe-124">Se si decide di utilizzare la console MMC (Microsoft Management Console) Certificati per importare la catena di certificati e il certificato, è necessario importarli nell'archivio certificarti per il computer.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-124">If you decide to use the Certificates Microsoft Management Console (MMC) to import the certificate chain and certificate, you must import them to the certificate store for the computer.</span></span> <span data-ttu-id="cbcfe-125">Se vengono importati nell'archivio certificati utente o del servizio, il certificato non sarà disponibile per l'assegnazione nella procedura guidata per il certificato di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-125">If you import them to the user or service certificate store, the certificate will not be available for assignment in the Lync Server 2013 Certificate Wizard.</span></span>

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="cbcfe-126">Per creare la richiesta di certificato per l'interfaccia esterna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="cbcfe-126">To create the certificate request for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="cbcfe-127">Nel server perimetrale, nella Distribuzione guidata fare clic su **Riesegui** accanto a **Passaggio 3: Richiesta, installazione o assegnazione dei certificati**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-127">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cbcfe-128">Se l'organizzazione desidera supportare la connettività di messaggistica istantanea pubblica con AOL, non è possibile utilizzare la Distribuzione guidata di Lync Server per richiedere il certificato.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-128">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="cbcfe-129">Eseguire invece i passaggi della procedura "Per creare una richiesta di certificato per l'interfaccia esterna del server perimetrale per il supporto della connettività di messaggistica istantanea pubblica con AOL" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-129">Instead, perform the steps in the “To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL” procedure later in this topic.</span></span><BR><span data-ttu-id="cbcfe-130">Se si dispone di più server perimetrali in un'unica posizione in un pool, è possibile eseguire la configurazione guidata certificati di Lync Server 2013 su uno dei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-130">If you have multiple Edge Servers in one location in a pool, you can run the Lync Server 2013 Certificate Wizard on any one of the Edge Servers.</span></span>

    
    </div>

2.  <span data-ttu-id="cbcfe-131">Nella pagina **Attività certificato disponibili** fare clic su **Crea una nuova richiesta di certificato**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-131">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="cbcfe-132">Nella pagina **Richiesta di certificato** fare clic su **Certificato perimetro esterno**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-132">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="cbcfe-133">Nella pagina **Richieste immediate o ritardate** selezionare la casella di controllo **Prepara la richiesta per l'invio posticipato**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-133">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="cbcfe-134">Nella pagina **file richiesta di certificato** Digitare il percorso completo e il nome del file in cui deve essere salvata la richiesta (ad esempio, c:\\CERT\_esterni\_Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="cbcfe-134">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="cbcfe-135">Nella pagina **Specifica modello di certificato alternativo**, per utilizzare un modello diverso dal modello Web Server predefinito selezionare la casella di controllo **Utilizza modello di certificato alternativo per l'autorità di certificazione selezionata**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-135">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="cbcfe-136">Nella pagina **Impostazioni nome e sicurezza** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cbcfe-136">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="cbcfe-137">In **Nome descrittivo** digitare un nome visualizzato per il certificato.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-137">In **Friendly name**, type a display name for the certificate.</span></span>
    
      - <span data-ttu-id="cbcfe-138">In **Lunghezza bit** specificare la lunghezza in bit (di solito, l'impostazione predefinita **2048**).</span><span class="sxs-lookup"><span data-stu-id="cbcfe-138">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
    
      - <span data-ttu-id="cbcfe-139">Verificare che la casella di controllo **Contrassegna come esportabile la chiave di certificato privata** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-139">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="cbcfe-140">Nella pagina **Informazioni sull'organizzazione** digitare il nome dell'organizzazione e dell'unità organizzativa, ad esempio una divisione o un reparto.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-140">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="cbcfe-141">Nella pagina **Dati geografici** specificare le informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-141">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="cbcfe-p107">Nella pagina **Nome soggetto / Nomi soggetto alternativi** verranno visualizzate le informazioni compilate automaticamente dalla procedura guidata. Se sono necessari ulteriori nomi alternativi soggetto, specificarli nei prossimi due passaggi.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-p107">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="cbcfe-144">Nella pagina **impostazione dominio SIP su nomi soggetto alternativi (San)** selezionare la casella di controllo Domain per aggiungere un SIP. \<voce\> SipDomain all'elenco dei nomi alternativi del soggetto.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-144">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="cbcfe-145">Nella pagina **Configura nomi soggetto alternativi aggiuntivi** specificare eventuali ulteriori nomi alternativi soggetto necessari.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-145">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

13. <span data-ttu-id="cbcfe-146">Nella pagina **Riepilogo richiesta** esaminare le informazioni sul certificato da utilizzare per generare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-146">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="cbcfe-147">Al termine dell'esecuzione dei comandi, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cbcfe-147">After the commands finish running, do the following:</span></span>
    
      - <span data-ttu-id="cbcfe-148">Per visualizzare il registro per la richiesta del certificato, fare clic su **Visualizza registro**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-148">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="cbcfe-149">Per completare la richiesta del certificato, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-149">To complete the certificate request, click **Next**.</span></span>

15. <span data-ttu-id="cbcfe-150">Nella pagina **File richiesta di certificato** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cbcfe-150">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="cbcfe-151">Per visualizzare il file di richiesta di firma del certificato (CSR) generato, fare clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-151">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="cbcfe-152">Per chiudere la procedura guidata, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-152">To close the wizard, click **Finish**.</span></span>

16. <span data-ttu-id="cbcfe-153">Copiare il file di output in un percorso da cui possa essere inoltrato alla CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-153">Copy the output file to a location where you can submit it to the public CA.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="cbcfe-154">Per creare una richiesta di certificato per l'interfaccia esterna del server perimetrale per il supporto della connettività di messaggistica istantanea pubblica con AOL</span><span class="sxs-lookup"><span data-stu-id="cbcfe-154">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="cbcfe-155">Quando il modello richiesto è disponibile per la CA, utilizzare il cmdlet di Windows PowerShell seguente dal server perimetrale per richiedere il certificato:</span><span class="sxs-lookup"><span data-stu-id="cbcfe-155">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate:</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="cbcfe-156">Il nome del certificato predefinito del modello fornito in Lync Server 2013 è il server Web.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-156">The default certificate name of the template provided in Lync Server 2013 is Web Server.</span></span> <span data-ttu-id="cbcfe-157">Specificare il nome \<\> del modello solo se è necessario utilizzare un modello diverso dal modello predefinito.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-157">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cbcfe-158">Se l'organizzazione desidera supportare la connettività di messaggistica istantanea pubblica con AOL, è necessario utilizzare Windows PowerShell anziché la procedura guidata per richiedere il certificato da assegnare al server perimetrale esterno per il servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-158">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="cbcfe-159">Ciò è dovuto al fatto che il modello del server Web Lync Server 2013 utilizzato dalla procedura guidata certificate per richiedere un certificato non supporta la configurazione EKU client.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-159">This is because the Lync Server 2013 Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="cbcfe-160">Prima di utilizzare Windows PowerShell per creare il certificato, l'amministratore della CA deve creare e distribuire un nuovo modello che supporti l'EKU client.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-160">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a><span data-ttu-id="cbcfe-161">Per inviare una richiesta a un'autorità di certificazione pubblica</span><span class="sxs-lookup"><span data-stu-id="cbcfe-161">To submit a request to a public certification authority</span></span>

1.  <span data-ttu-id="cbcfe-162">Aprire il file di output.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-162">Open the output file.</span></span>

2.  <span data-ttu-id="cbcfe-163">Copiare e incollare il contenuto della richiesta di firma del certificato (CSR).</span><span class="sxs-lookup"><span data-stu-id="cbcfe-163">Copy and paste the contents of the Certificate Signing Request (CSR).</span></span>

3.  <span data-ttu-id="cbcfe-164">Se richiesto, specificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cbcfe-164">If prompted, specify the following:</span></span>
    
      - <span data-ttu-id="cbcfe-165">**Microsoft** come piattaforma server.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-165">**Microsoft** as the server platform.</span></span>
    
      - <span data-ttu-id="cbcfe-166">**IIS** come versione.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-166">**IIS** as the version.</span></span>
    
      - <span data-ttu-id="cbcfe-167">**Server Web** come tipo di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-167">**Web Server** as the usage type.</span></span>
    
      - <span data-ttu-id="cbcfe-168">**PKCS7** come formato della risposta.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-168">**PKCS7** as the response format.</span></span>

4.  <span data-ttu-id="cbcfe-169">Dopo la verifica delle informazioni da parte della CA pubblica, si riceverà un messaggio di posta elettronica contenente il testo richiesto per il certificato.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-169">When the public CA has verified your information, you will receive an email message containing text required for your certificate.</span></span>

5.  <span data-ttu-id="cbcfe-170">Copiare il testo dal messaggio di posta elettronica e salvarne il contenuto in un file di testo (con estensione txt) nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-170">Copy the text from the email message and save the contents in a text file (.txt) on your local computer.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="cbcfe-171">Per importare il certificato per l'interfaccia esterna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="cbcfe-171">To import the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="cbcfe-172">Accedere come membro del gruppo Administrators al server perimetrale in cui è stata creata la richiesta di certificato.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-172">Log on as a member of the Administrators group to the same Edge Server on which you created the certificate request.</span></span>

2.  <span data-ttu-id="cbcfe-173">Nella pagina **Distribuisci Edge Server** della Distribuzione guidata fare clic su **Riesegui** accanto a **Passaggio 3: Richiesta, installazione o assegnazione dei certificati**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-173">In the Deployment Wizard, on the **Deploy Edge Server** page, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

3.  <span data-ttu-id="cbcfe-174">Nella pagina **Attività certificato disponibili** fare clic su **Importa un certificato da un file con estensione p7b, pfx o cer**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-174">On the **Available Certificate Tasks** page, click **Import a certificate from a .p7b, pfx or .cer file**.</span></span>

4.  <span data-ttu-id="cbcfe-p110">Nella pagina **Importa certificato** fare clic su **Sfoglia** per individuare e selezionare il certificato richiesto per l'interfaccia esterna del server perimetrale, In alternativa, è possibile digitare il percorso completo e il nome di file. Se il certificato contiene una chiave privata, selezionare **Il file di certificato contiene una chiave di certificato privata** e digitare la password per la chiave privata. Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-p110">On the **Import Certificate** page, click **Browse** to locate and select the certificate that you requested for the external interface of the Edge Server (or, you can type the full path and file name). If the certificate contains a private key, select **Certificate file contains certificate’s private key** and type the password for the private key. Click **Next**.</span></span>

5.  <span data-ttu-id="cbcfe-178">Nella pagina **Riepilogo importazione certificato** verificare le informazioni di riepilogo e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-178">On **Import Certificate Summary** page, review the summary and then click **Next**.</span></span>

6.  <span data-ttu-id="cbcfe-179">In **Esecuzione comandi in corso** controllare i risultati dell'impostazione, fare clic su **Visualizza registro** per ulteriori informazioni eventualmente necessarie e quindi fare clic su **Fine** per completare l'importazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-179">On **Executing Commands**, review the results of the import, click **View Log** for more information as needed, and then click **Finish** to complete the certificate import.</span></span>

7.  <span data-ttu-id="cbcfe-p111">Se si sta configurando un pool di server perimetrali, esportare il certificato con la relativa chiave privata come descritto nella procedura "Per esportare il certificato con la chiave privata per i server perimetrali in un pool" di seguito in questo argomento. Copiare il file del certificato esportato negli altri server perimetrali e importarlo nell'archivio del computer in ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-p111">If you are configuring an Edge Server pool, export the certificate with its private key as outlined in the “To export the certificate with the private key for Edge Servers in a pool” procedure later in this topic. Copy the exported certificate file to the other Edge Servers, and import it into the computer store on each Edge Server.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="cbcfe-182">Per esportare il certificato con la chiave privata per i server perimetrali in un pool</span><span class="sxs-lookup"><span data-stu-id="cbcfe-182">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="cbcfe-183">Accedere come membro del gruppo Administrators allo stesso server perimetrale in cui è stato importato il certificato.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-183">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="cbcfe-184">Fare clic sul pulsante **Start**, scegliere **Esegui** e quindi digitare **MMC**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-184">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="cbcfe-185">Nella console MMC scegliere **Aggiungi/Rimuovi snap-in** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-185">In the Microsoft Management Console (MMC) console, click **File**, and then click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="cbcfe-186">In **Aggiungi o rimuovi snap-in** fare clic su **Certificati** e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-186">In **Add or Remove Snap-ins**, click **Certificates**, and then click **Add**.</span></span>

5.  <span data-ttu-id="cbcfe-187">Nella finestra di dialogo **Certificati** selezionare **Account computer**, fare clic su **Avanti**, selezionare **Computer locale (il computer su cui è in esecuzione questa console)** in **Selezione computer**, fare clic su **Fine** e quindi fare clic su **OK** per completare la configurazione della console MMC.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-187">In the **Certificates** dialog box, select **Computer account**, click **Next**, select **Local computer: (the computer this console is running on)** in **Select Computer**, click **Finish** and then click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="cbcfe-188">Fare doppio clic su **Certificati (computer locale)** per espandere gli archivi di certificati, fare doppio clic su **Personale** e quindi doppio clic su **Certificati**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-188">Double-click **Certificates (Local Computer)** to expand the certificate stores, double-click **Personal**, and then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cbcfe-p112">Se l'archivio dei certificati personali per il computer locale non contiene alcun certificato, non esiste una chiave privata associata al certificato importato. Controllare la richiesta e i passaggi di importazione. Se il problema persiste, contattare l'amministratore o il provider dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-p112">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported. Review the request and import steps. If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="cbcfe-192">Nell'archivio dei certificati personali per il computer locale\*\*\*\* fare clic con il pulsante destro del mouse sul certificato da esportare, scegliere **Tutte le attività** e quindi fare clic su **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-192">In the **Certificates Personal store for the local computer**, right-click the certificate that you are exporting, click **All Tasks**, and then click **Export**.</span></span>

8.  <span data-ttu-id="cbcfe-193">Nell'Esportazione guidata certificati fare clic su **Avanti**, selezionare **Sì, esporta la chiave privata** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-193">In the Certificate Export Wizard, click **Next**, select **Yes, export the private key**, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cbcfe-p113">Se l'opzione <STRONG>Sì, esporta la chiave privata</STRONG> non è disponibile, la chiave privata associata al certificato non è stata contrassegnata per l'esportazione. Sarà necessario richiedere di nuovo il certificato, assicurandosi che il certificato sia contrassegnato per consentire l'esportazione della chiave privata prima di poter continuare con l'esportazione. Contattare l'amministratore o il provider dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-p113">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export. You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export. Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="cbcfe-197">Nella finestra di dialogo formati file di esportazione selezionare **scambio di informazioni personali\#-PKCS 12 (. PFX)** e quindi selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cbcfe-197">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="cbcfe-198">Se possibile, includi tutti i certificati nel percorso certificazione</span><span class="sxs-lookup"><span data-stu-id="cbcfe-198">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="cbcfe-199">Esporta tutte le proprietà estese</span><span class="sxs-lookup"><span data-stu-id="cbcfe-199">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="cbcfe-p114">Quando si esporta il certificato da un server perimetrale, non selezionare <STRONG>Elimina la chiave privata se l'esportazione ha esito positivo</STRONG>. Se si seleziona questa opzione sarà necessario importare il certificato e la chiave privata in questo server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-p114">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>. Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>

10. <span data-ttu-id="cbcfe-202">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-202">Click **Next**.</span></span>

11. <span data-ttu-id="cbcfe-203">Digitare una password per la chiave privata, digitarla di nuovo per confermare e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-203">Type a password for the private key, type the password again to confirm, and then click **Next**.</span></span>

12. <span data-ttu-id="cbcfe-p115">Digitare un percorso e il nome di file per il certificato esportato, utilizzando l'estensione di file pfx. Il percorso deve essere accessibile per tutti i server perimetrali nel pool o essere disponibile per il trasferimento con un supporto rimovibile, come un'unità flash USB. Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-p115">Type a path and file name for the exported certificate, using a file extension of .pfx. The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive. Click **Next**.</span></span>

13. <span data-ttu-id="cbcfe-207">Controllare le informazioni di riepilogo in **Completamento dell'Esportazione guidata certificati** e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-207">Review the summary in **Completing the Certificate Export Wizard**, and then click **Finish**.</span></span>

14. <span data-ttu-id="cbcfe-208">Nella finestra di dialogo di completamento dell'esportazione fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-208">In the successful export dialog box, click **OK**.</span></span>

15. <span data-ttu-id="cbcfe-209">Importare il file del certificato esportato negli altri server perimetrali seguendo i passaggi descritti nella procedura “Per importare il certificato per l'interfaccia esterna del server perimetrale” più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-209">Import the exported certificate file to the other Edge servers following the steps outlined in the “To import the certificate for the external interface of the Edge Server” procedure earlier in this topic.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="cbcfe-210">Per assegnare il certificato per l'interfaccia esterna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="cbcfe-210">To assign the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="cbcfe-211">In ogni server perimetrale, nella Distribuzione guidata fare clic su **Esegui** accanto a **Passaggio 3: Richiesta, installazione o assegnazione dei certificati**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-211">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="cbcfe-212">Nella pagina **Attività certificato disponibili** fare clic su **Assegna un certificato esistente**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-212">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="cbcfe-213">Nella pagina **Assegnazione certificato** fare clic su **Certificato perimetro esterno** e selezionare la casella di controllo **Utilizzi avanzati certificato**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-213">On the **Certificate Assignment** page, click **External Edge Certificate** and select the **Advanced Certificate Usages** check box.</span></span>

4.  <span data-ttu-id="cbcfe-214">Nella pagina **Utilizzi avanzati certificato** selezionare tutte le caselle di controllo per assegnare il certificato a tutti i tipi di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-214">On the **Advanced Certificate Usages** page, select all check boxes to assign the certificate for all usages.</span></span>

5.  <span data-ttu-id="cbcfe-215">Nella pagina **Archivio certificati** selezionare il certificato pubblico richiesto e importato per l'interfaccia esterna del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-215">On the **Certificate Store** page, select the public certificate that you requested and imported for the external interface of the Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cbcfe-216">Se il certificato richiesto e importato non è incluso nell'elenco, uno dei metodi per risolvere il problema consiste nel verificare che il nome soggetto e i nomi alternativi soggetto del certificato soddisfino tutti i requisiti per il certificato. Se il certificato e la catena di certificati sono stati importanti manualmente anziché tramite le procedure precedenti, è necessario verificare che il certificato si trovi nell'archivio corretto, ovvero l'archivio del computer e non quello dell'utente o del servizio.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-216">If the certificate you requested and imported is not in the list, one of the trouble shooting methods is to verify that subject name and subject alternative names of the certificate meet all requirements for the certificate and, if you manually imported the certificate and certificate chain instead of using the preceding procedures, that the certificate is in the correct certificate store (the computer certificate store, not the user or service certificate store).</span></span>

    
    </div>

6.  <span data-ttu-id="cbcfe-217">Nella pagina **Riepilogo assegnazione certificato** controllare le impostazioni e quindi fare clic su **Avanti** per assegnare i certificati.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-217">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

7.  <span data-ttu-id="cbcfe-218">Nella pagina finale della procedura guidata fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-218">On the wizard completion page, click **Finish**.</span></span>

8.  <span data-ttu-id="cbcfe-219">Dopo aver assegnato il certificato del server perimetrale interno mediante questa procedura, aprire lo snap-in Certificati in ogni server, espandere **Certificati (computer locale)**, espandere **Personale**, fare clic su **Certificati** e quindi verificare che il certificato sia presente nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-219">After using this procedure to assign the edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the certificate is listed.</span></span>

9.  <span data-ttu-id="cbcfe-220">Se la distribuzione include più server perimetrali, ripetere la procedura per ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="cbcfe-220">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

