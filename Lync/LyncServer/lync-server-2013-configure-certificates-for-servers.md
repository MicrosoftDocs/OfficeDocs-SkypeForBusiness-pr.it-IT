---
title: 'Lync Server 2013: configurare i certificati per i server'
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
ms.openlocfilehash: 3556c9147ddf2769e6a403de9e31edf31129d796
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a><span data-ttu-id="6afee-102">Configurare i certificati per i server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6afee-102">Configure certificates for servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6afee-103">_**Ultimo argomento modificato:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="6afee-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="6afee-104">Per eseguire questa procedura, è necessario accedere come utente membro del gruppo RTCUniversalServerAdmins o disporre della delega delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="6afee-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="6afee-105">Per informazioni dettagliate su come delegare le autorizzazioni, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6afee-105">For details about delegating permissions, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="6afee-106">A seconda dell'organizzazione e dei requisiti per la richiesta dei certificati, potrebbe essere necessario appartenere ad altri gruppi.</span><span class="sxs-lookup"><span data-stu-id="6afee-106">Depending on your organization and requirements for requesting certificates, you may require other group memberships.</span></span> <span data-ttu-id="6afee-107">Rivolgersi al gruppo che gestisce l'Autorità di certificazione (CA) dell'infrastruttura a chiave pubblica (PKI).</span><span class="sxs-lookup"><span data-stu-id="6afee-107">Consult with the group that manages your public key infrastructure (PKI) certification authority (CA).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6afee-108">Lync Server 2013 include il supporto per la famiglia SHA-2 (SHA-2 utilizza la lunghezza del digest di 224, 256, 384 o 512 bit) dell'hash digest e gli algoritmi di firma per le connessioni dai client che eseguono Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista o Sistemi operativi Windows XP, oltre a Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="6afee-108">Lync Server 2013 includes support for the SHA-2 suite (SHA-2 uses digest lengths of 224, 256, 384 or 512 bits) of digest hash and signing algorithms for connections from clients running the Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista, or Windows XP operating systems, in addition to Lync Phone Edition.</span></span> <span data-ttu-id="6afee-109">Per supportare l'accesso esterno tramite la famiglia SHA-2, il certificato esterno viene emesso da un'autorità di certificazione pubblica che può anche emettere un certificato con lo stesso bit di lunghezza del digest.</span><span class="sxs-lookup"><span data-stu-id="6afee-109">To support external access using the SHA-2 suite, the external certificate is issued by a public CA that also can issue a certificate with the same bit length digest.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="6afee-110">La selezione dell'algoritmo di firma e del digest hash dipende dai client e dai server che utilizzeranno il certificato e da altri computer e dispositivi che i client e i server comunicheranno con gli utenti che devono anche sapere come utilizzare gli algoritmi utilizzati nell' certificato.</span><span class="sxs-lookup"><span data-stu-id="6afee-110">The selection of which hash digest and signing algorithm is dependent on the clients and the servers that will use the certificate, and other computers and devices that clients and servers will communicate with who must also know how to use the algorithms used in the certificate.</span></span> <span data-ttu-id="6afee-111">Per informazioni su quali lunghezze del digest sono supportate nel sistema operativo e in alcune applicazioni client<A href="https://go.microsoft.com/fwlink/?linkid=287002">https://go.microsoft.com/fwlink/?LinkId=287002</A>, vedere.</span><span class="sxs-lookup"><span data-stu-id="6afee-111">For information on which digest lengths are supported in the operating system and some client applications, see<A href="https://go.microsoft.com/fwlink/?linkid=287002">https://go.microsoft.com/fwlink/?LinkId=287002</A>.</span></span>



</div>

<span data-ttu-id="6afee-112">Ogni server Standard Edition o front end server richiede fino a quattro certificati: il certificato oAuthTokenIssuer, un certificato predefinito, un certificato interno Web e un certificato esterno Web.</span><span class="sxs-lookup"><span data-stu-id="6afee-112">Each Standard Edition server or Front End Server requires up to four certificates: the oAuthTokenIssuer certificate, a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="6afee-113">È tuttavia possibile richiedere e assegnare un singolo certificato predefinito con voci appropriate del nome alternativo del soggetto, nonché il certificato oAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="6afee-113">However, it is possible to request and assign a single default certificate with appropriate subject alternative name entries as well as the oAuthTokenIssuer certificate.</span></span> <span data-ttu-id="6afee-114">Per informazioni dettagliate sui requisiti dei certificati, vedere [requisiti dei certificati per i server interni in Lync server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span><span class="sxs-lookup"><span data-stu-id="6afee-114">For details about the certificate requirements, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span></span> <span data-ttu-id="6afee-115">Per informazioni dettagliate sulla richiesta, l'assegnazione e l'installazione del certificato oAuthTokenIssuer, vedere [Managing server-to-Server Authentication (OAuth) and partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="6afee-115">For details about requesting, assigning and installing the oAuthTokenIssuer certificate, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

<span data-ttu-id="6afee-116">Utilizzare la procedura seguente per richiedere, assegnare e installare il server Standard Edition o i certificati del server front end.</span><span class="sxs-lookup"><span data-stu-id="6afee-116">Use the following procedure to request, assign, and install the Standard Edition server or Front End Server certificates.</span></span> <span data-ttu-id="6afee-117">Ripetere la procedura per ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="6afee-117">Repeat the procedure for each Front End Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6afee-118">Nella procedura seguente viene illustrato come configurare i certificati di un'infrastruttura a chiave pubblica interna distribuita dall'organizzazione e con l'elaborazione delle richieste offline.</span><span class="sxs-lookup"><span data-stu-id="6afee-118">The following procedure describes how to configure certificates from an internal enterprise PKI deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="6afee-119">Per informazioni su come ottenere certificati da un'autorità di certificazione pubblica, vedere <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate Requirements for Internal Servers in Lync server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="6afee-119">For information about obtaining certificates from a public CA, see <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate requirements for internal servers in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="6afee-120">Inoltre, in questa procedura viene descritto come richiedere, assegnare e installare i certificati durante la configurazione del front end server.</span><span class="sxs-lookup"><span data-stu-id="6afee-120">Also, this procedure describes how to request, assign, and install certificates during set up of the Front End Server.</span></span> <span data-ttu-id="6afee-121">Se sono stati richiesti in anticipo i certificati, come descritto nella sezione <A href="lync-server-2013-request-certificates-in-advance-optional.md">richiesta certificati in anticipo (facoltativo) per Lync Server 2013</A> della documentazione relativa alla distribuzione o non si utilizza un'infrastruttura PKI aziendale interna distribuita nell'organizzazione per ottenere i certificati, è necessario modificare questa procedura in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="6afee-121">If you requested certificates in advance, as described in the <A href="lync-server-2013-request-certificates-in-advance-optional.md">Request certificates in advance (optional) for Lync Server 2013</A> section of this Deployment documentation, or you do not use an internal enterprise PKI deployed in your organization to obtain certificates, you must modify this procedure as appropriate.</span></span>



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a><span data-ttu-id="6afee-122">Per configurare i certificati per un Front End Server</span><span class="sxs-lookup"><span data-stu-id="6afee-122">To configure certificates for a Front End Server</span></span>

1.  <span data-ttu-id="6afee-123">Nella distribuzione guidata di Lync Server, fare clic su **Esegui** accanto a **passaggio 3: richiesta, installazione o assegnazione dei certificati**.</span><span class="sxs-lookup"><span data-stu-id="6afee-123">In the Lync Server Deployment Wizard, click **Run** next to **Step 3: Request, Install or Assign Certificates**.</span></span>

2.  <span data-ttu-id="6afee-124">Nella pagina **Configurazione guidata certificati** fare clic su **Richiesta**.</span><span class="sxs-lookup"><span data-stu-id="6afee-124">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="6afee-125">Nella pagina **Richiesta di certificato** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6afee-125">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="6afee-p107">Nella pagina **Richieste immediate o ritardate** è possibile accettare l'opzione predefinita **Invia immediatamente la richiesta a un'autorità di certificazione online** facendo clic su **Avanti**. Se si seleziona questa opzione, deve essere disponibile la CA interna con registrazione automatica online. Se si sceglie l'opzione di ritardare la richiesta, sarà necessario specificare un nome e un percorso in cui salvare il file di richiesta di certificato. La richiesta di certificato deve essere presentata ed elaborata da una CA all'interno dell'organizzazione o da una CA pubblica. Sarà quindi necessario importare il certificato di risposta e assegnarlo al ruolo appropriato.</span><span class="sxs-lookup"><span data-stu-id="6afee-p107">On the **Delayed or Immediate Requests** page, you can accept the default **Send the request immediately to an online certification authority** option by clicking **Next**. The internal CA with automatic online enrollment must be available if you select this option. If you choose the option to delay the request, you will be prompted for a name and location to save the certificate request file. The certificate request must be presented and processed by a CA either inside your organization, or by a public CA. You will then need to import the certificate response and assign it to the proper certificate role.</span></span>

5.  <span data-ttu-id="6afee-131">Nella pagina **scegliere un'autorità di certificazione (CA)** selezionare l'opzione **Seleziona una CA dall'elenco rilevato nell'ambiente in uso** e quindi selezionare una CA nota (tramite registrazione in servizi di dominio Active Directory) dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="6afee-131">On the **Choose a Certificate Authority (CA)** page, select the **Select a CA from the list detected in your environment** option, and then select a known (through registration in Active Directory Domain Services) CA from the list.</span></span> <span data-ttu-id="6afee-132">In alternativa, selezionare l'opzione **Specifica un'altra autorità di certificazione**, immettere il nome di un'altra CA e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6afee-132">Or, select the **Specify another certification authority** option, enter the name of another CA in the box, and then click **Next**.</span></span>

6.  <span data-ttu-id="6afee-p109">Nella pagina **Account autorità di certificazione** viene richiesto di immettere le credenziali per richiedere ed elaborare la richiesta di certificato per la CA. Stabilire se è necessario specificare un nome utente e una password per richiedere un certificato in anticipo. L'amministratore della CA dispone delle informazioni necessarie per poter assistere l'utente in questo passaggio. Se è necessario fornire credenziali alternative, selezionare la casella di controllo, specificare il nome utente e la password nelle caselle di testo, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6afee-p109">On the **Certificate Authority Account** page, you are prompted for credentials to request and process the certificate request at the CA. You should have determined if a user name and password is necessary to request a certificate in advance. Your CA administrator will have the required information and may have to assist you in this step. If you need to supply alternate credentials, select the check box, provide a user name and password in the text boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="6afee-137">Nella pagina **Specifica modello di certificato alternativo** fare clic su **Avanti** per utilizzare il modello Server Web predefinito.</span><span class="sxs-lookup"><span data-stu-id="6afee-137">On the **Specify Alternate Certificate Template** page, to use the default Web Server template, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6afee-p110">Se l'organizzazione ha creato un modello da utilizzare come alternativa al modello Server Web predefinito della CA, selezionare la casella di controllo, quindi immettere il nome del modello alternativo. È necessario specificare il nome del modello come definito dall'amministratore della CA.</span><span class="sxs-lookup"><span data-stu-id="6afee-p110">If your organization has created a template for use as an alternative for the default Web server CA template, select the check box, and then enter the name of the alternate template. You will need the template name as defined by the CA administrator.</span></span>

    
    </div>

8.  <span data-ttu-id="6afee-p111">Nella pagina **Impostazioni nome e sicurezza** specificare un valore in **Nome descrittivo** per consentire di identificare il certificato e lo scopo. Se questo campo viene lasciato vuoto, verrà generato automaticamente un nome. Impostare il valore **Lunghezza in bit** della chiave o accettare il valore predefinito di 2048 bit. Selezionare l'opzione **Contrassegna come esportabile la chiave di certificato privata** se è necessario spostare o copiare la chiave privata in altri sistemi, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6afee-p111">On the **Name and Security Settings** page, specify a **Friendly Name** that should allow you to identify the certificate and purpose. If you leave it blank, a name will be generated automatically. Set the **Bit length** of the key, or accept the default of 2048 bits. Select the **Mark the certificate’s private key as exportable** if you determine that the certificate and private key needs to be moved or copied to other systems, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6afee-144">Lync Server 2013 ha requisiti minimi per una chiave privata esportabile.</span><span class="sxs-lookup"><span data-stu-id="6afee-144">Lync Server 2013 has minimal requirements for an exportable private key.</span></span> <span data-ttu-id="6afee-145">La chiave viene esportata nei server perimetrali di un pool, dove il servizio di autenticazione del Media Relay utilizza copie del certificato anziché i singoli certificati per ogni istanza nel pool.</span><span class="sxs-lookup"><span data-stu-id="6afee-145">One such place is on the Edge Servers in a pool, where the Media Relay Authentication Service uses copies of the certificate, rather than individual certificates for each instance in the pool.</span></span>

    
    </div>

9.  <span data-ttu-id="6afee-146">Nella pagina **Informazioni sull'organizzazione** immettere facoltativamente le informazioni sull'organizzazione e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6afee-146">On the **Organization Information** page, optionally provide organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="6afee-147">Nella pagina **Dati geografici** specificare facoltativamente i dati geografici e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6afee-147">On the **Geographical Information** page, optionally provide geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="6afee-148">Nella pagina **Nome soggetto / Nomi soggetto alternativi** verificare i nomi soggetto alternativi che verranno aggiunti e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6afee-148">On the **Subject Name / Subject Alternate Names** page, review the subject alternative names that will be added, and then click **Next**.</span></span>

12. <span data-ttu-id="6afee-149">Nella pagina **Impostazione del dominio SIP** selezionare la casella di controllo **Dominio SIP** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6afee-149">On the **SIP Domain setting** page, select the **SIP Domain**, and then click **Next**.</span></span>

13. <span data-ttu-id="6afee-150">Nella pagina **Configura nomi soggetto alternativi aggiuntivi** aggiungere eventuali nomi soggetto alternativi aggiuntivi necessari, inclusi quelli potranno essere richiesti in futuro per i domini SIP aggiuntivi, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6afee-150">On the **Configure Additional Subject Alternate Names** page, add any additional required subject alternative names, including any that might be required for additional SIP domains in the future, and then click **Next**.</span></span>

14. <span data-ttu-id="6afee-p113">Nella pagina **Riepilogo richiesta certificato** esaminare le informazioni. Se sono corrette, fare clic su **Avanti**. Se è necessario correggere o modificare un'impostazione, fare clic su **Indietro** fino alla pagina appropriata.</span><span class="sxs-lookup"><span data-stu-id="6afee-p113">On the **Certificate Request Summary** page, review the information in the summary. If the information is correct, click **Next**. If you need to correct or modify a setting, click **Back** to the proper page to make the correction or modification.</span></span>

15. <span data-ttu-id="6afee-154">Nella pagina **Esecuzione comandi in corso** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6afee-154">On the **Executing Commands** page, click **Next**.</span></span>

16. <span data-ttu-id="6afee-155">Nella pagina On the **Stato richiesta di certificato online** esaminare le informazioni restituite.</span><span class="sxs-lookup"><span data-stu-id="6afee-155">On the **Online Certificate Request Status** page, review the information returned.</span></span> <span data-ttu-id="6afee-156">Verificare che il certificato sia stato emesso e installato nell'archivio certificati locale.</span><span class="sxs-lookup"><span data-stu-id="6afee-156">You should note that the certificate was issued and installed into the local certificate store.</span></span> <span data-ttu-id="6afee-157">Se viene segnalato come emesso e installato, ma non è valido, verificare che il certificato radice della CA sia stato installato nell'archivio CA radice attendibile del server.</span><span class="sxs-lookup"><span data-stu-id="6afee-157">If it is reported as having been issued and installed, but is not valid, make sure that the CA root certificate has been installed in the server’s Trusted Root CA store.</span></span> <span data-ttu-id="6afee-158">Per informazioni su come recuperare un certificato di CA radice attendibile, consultare la documentazione sulla CA.</span><span class="sxs-lookup"><span data-stu-id="6afee-158">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span></span> <span data-ttu-id="6afee-159">Se è necessario visualizzare il certificato recuperato, fare clic su **Visualizza dettagli certificato**.</span><span class="sxs-lookup"><span data-stu-id="6afee-159">If you need to view the retrieved certificate, click **View Certificate Details**.</span></span> <span data-ttu-id="6afee-160">Per impostazione predefinita, la casella di controllo **Assegnare il certificato restituito agli utilizzi di Lync Server sul server**.</span><span class="sxs-lookup"><span data-stu-id="6afee-160">By default, the check box for **Assign the certificate to Lync Server certificate usages** is checked.</span></span> <span data-ttu-id="6afee-161">Se si desidera assegnare manualmente il certificato, deselezionare la casella di controllo e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="6afee-161">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span></span>

17. <span data-ttu-id="6afee-p115">Se nella pagina precedente è stata deselezionata la casella di controllo **Assegnare il certificato restituito agli utilizzi di Lync Server sul server**, verrà visualizzata la pagina **Assegnazione certificato**. Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6afee-p115">If you cleared the check box for **Assign the certificate to Lync Server certificate usages** on the previous page, you will be presented with the **Certificate Assignment** page. Click **Next**.</span></span>

18. <span data-ttu-id="6afee-p116">Nella pagina **Archivio certificati** selezionare il certificato richiesto. Se si desidera visualizzarlo, fare clic su **Visualizza dettagli certificato** e quindi su **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="6afee-p116">On the **Certificate Store** page, select the certificate that you requested. If you want to view the certificate, click **View Certificate Details**, and then click **Next** to continue.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6afee-p117">Se nella pagina <STRONG>Stato richiesta di certificato online</STRONG> viene segnalato un problema con il certificato, ad esempio che non è valido, la visualizzazione del certificato effettivo può consentire di risolverlo. In particolare, il certificato può non essere valido perché non è stato emesso da una CA radice attendibile, come accennato in precedenza, oppure perché non è associato a una chiave privata. Per risolvere questi due problemi, consultare la documentazione della CA.</span><span class="sxs-lookup"><span data-stu-id="6afee-p117">If the <STRONG>Online Certificate Request Status</STRONG> page reported an issue with the certificate, such as the certificate not being valid, viewing the actual certificate can assist in resolving the issue. Two specific issues that can cause a certificate to not be valid is the previously mentioned missing Trusted Root CA certificate, and a missing private key that is associated with the certificate. Refer to your CA documentation to resolve these two issues.</span></span>

    
    </div>

19. <span data-ttu-id="6afee-169">Nella pagina **Riepilogo assegnazione certificato** esaminare le informazioni presentate per assicurarsi che si tratta del certificato da assegnare e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6afee-169">On the **Certificate Assignment Summary** page, review the information presented to make sure that this is the certificate that should be assigned, and then click **Next**.</span></span>

20. <span data-ttu-id="6afee-p118">Nella pagina **Esecuzione comandi in corso** esaminare l'output del comando. Fare clic su **Visualizza registro** se si desidera rivedere il processo di assegnazione oppure se è stato generato un messaggio di errore o di avviso. Al termine, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="6afee-p118">On the **Executing Commands** page, review the output of the command. Click **View Log** if you want to review the assignment process or if there was an error or warning issued. When you are finished with your review, click **Finish**.</span></span>

21. <span data-ttu-id="6afee-173">Nella pagina **Configurazione guidata certificati** verificare che lo **Stato** dei certificato sia "Assegnato" e quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="6afee-173">On the **Certificate Wizard** page, verify that the **Status** of the certificate is “Assigned,” and then click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6afee-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6afee-174">See Also</span></span>


[<span data-ttu-id="6afee-175">Requisiti dell'infrastruttura dei certificati per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6afee-175">Certificate infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

