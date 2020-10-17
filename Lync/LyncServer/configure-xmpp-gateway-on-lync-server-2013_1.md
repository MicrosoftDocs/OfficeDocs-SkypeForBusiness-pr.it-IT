---
title: Configurare il gateway XMPP in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49733538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a2893d05230edbd261f7115a9be92bcd3275723
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503173"
---
# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="5a7c0-102">Configurare il gateway XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a7c0-102">Configure XMPP gateway on Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a7c0-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="5a7c0-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="5a7c0-104">Quando si configurano i criteri per il supporto di partner federati XMPP, tali criteri si applicano agli utenti di domini federati XMPP, ma non agli utenti di provider di servizi di messaggistica istantanea SIP (Session Initiation Protocol), ad esempio Windows Live, o di domini federati SIP.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-104">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="5a7c0-105">Configurare un partner federato XMPP per ogni dominio federato XMPP di cui si desidera consentire agli utenti di aggiungere contatti e con cui possono comunicare.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-105">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="5a7c0-106">Una volta che i criteri sono sul posto, attività aggiuntive includono la configurazione dei certificati del gateway XMPP, la distribuzione del gateway XMPP Lync Server 2013 e infine l'aggiornamento dei record DNS per il gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-106">Once the policies are in place, additional tasks include configuring the XMPP Gateway certificates, deploying the Lync Server 2013 XMPP Gateway, and finally updating the DNS records for the XMPP Gateway.</span></span>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="5a7c0-107">Configurare i certificati del gateway XMPP nel server perimetrale Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a7c0-107">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="5a7c0-108">Nel server perimetrale fare clic su **Riesegui** nella Distribuzione guidata accanto a **Passaggio 3: Richiesta, installazione o assegnazione dei certificati**.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-108">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="5a7c0-109">Se si distribuisce il server perimetrale per la prima volta, sarà disponibile il pulsante Esegui anziché Riesegui.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-109">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="5a7c0-110">Nella pagina **Attività certificato disponibili** fare clic su **Crea una nuova richiesta di certificato**.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-110">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="5a7c0-111">Nella pagina **Richiesta di certificato** fare clic su **Certificato perimetro esterno**.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-111">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="5a7c0-112">Nella pagina **Richieste immediate o ritardate** selezionare la casella di controllo **Prepara la richiesta per l'invio posticipato**.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-112">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="5a7c0-113">Nella pagina **file richiesta di certificato** Digitare il percorso completo e il nome del file in cui deve essere salvata la richiesta (ad esempio, c: \\ CERT \_ esterni \_ Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="5a7c0-113">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="5a7c0-114">Nella pagina **Specifica modello di certificato alternativo**, per utilizzare un modello diverso dal modello Web Server predefinito selezionare la casella di controllo **Utilizza modello di certificato alternativo per l'autorità di certificazione selezionata**.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-114">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="5a7c0-115">Nella pagina **Impostazioni nome e sicurezza** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a7c0-115">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="5a7c0-116">In **Nome descrittivo** digitare un nome visualizzato per il certificato.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-116">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="5a7c0-117">In **Lunghezza bit** specificare la lunghezza in bit (in genere il valore predefinito 2048).</span><span class="sxs-lookup"><span data-stu-id="5a7c0-117">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="5a7c0-118">Verificare che la casella di controllo **Contrassegna come esportabile la chiave di certificato privata** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-118">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="5a7c0-119">Nella pagina **Informazioni sull'organizzazione** digitare il nome dell'organizzazione e dell'unità organizzativa, ad esempio una divisione o un reparto.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-119">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="5a7c0-120">Nella pagina **Dati geografici** specificare le informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-120">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="5a7c0-p102">Nella pagina **Nome soggetto / Nomi soggetto alternativi** verranno visualizzate le informazioni compilate automaticamente dalla procedura guidata. Se sono necessari ulteriori nomi alternativi soggetto, specificarli nei prossimi due passaggi.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-p102">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="5a7c0-123">Nella pagina **impostazione dominio SIP su nomi soggetto alternativi (San)** selezionare la casella di controllo Domain per aggiungere un SIP.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="5a7c0-123">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\></span></span> <span data-ttu-id="5a7c0-124">voce all'elenco dei nomi alternativi del soggetto.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-124">entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="5a7c0-125">Nella pagina **Configura nomi alternativi soggetto aggiuntivi** specificare eventuali nomi alternativi del soggetto aggiuntivi necessari.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-125">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="5a7c0-p104">Se è installato il proxy XMPP, per impostazione predefinita le voci SAN vengono popolate con il nome di dominio, ad esempio contoso.com. Se sono necessarie ulteriori voci, aggiungerle in questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-p104">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="5a7c0-128">Nella pagina **Riepilogo richiesta** esaminare le informazioni sul certificato da utilizzare per generare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-128">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="5a7c0-129">Al termine dell'esecuzione dei comandi, è possibile scegliere **Visualizza log** oppure fare clic su **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-129">After the commands finish running, you can **View Log**, or click **Next** to continue.</span></span>

15. <span data-ttu-id="5a7c0-130">Nella pagina **File richiesta di certificato** è possibile visualizzare il file richiesta di firma del certificato (CSR) generato facendo clic su Visualizza oppure uscire dalla Configurazione guidata certificati facendo clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-130">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="5a7c0-131">Copiare il file richiesta e inoltrarlo all'autorità di certificazione pubblica.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-131">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="5a7c0-p105">Dopo aver ricevuto, importato e assegnato il certificato pubblico, è necessario arrestare e riavviare i servizi del server perimetrale. A tale scopo, digitare quanto segue nella console di gestione di Lync Server:</span><span class="sxs-lookup"><span data-stu-id="5a7c0-p105">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
       ```console
        Stop-CsWindowsService
       ```
    
       ```console
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="5a7c0-134">Configurare un nuovo gateway XMPP di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a7c0-134">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="5a7c0-135">Aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-135">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="5a7c0-136">Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Partner federati XMPP**.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-136">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="5a7c0-137">Per creare una nuova configurazione, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-137">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="5a7c0-138">Definire le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a7c0-138">Define the following settings:</span></span>

5.  <span data-ttu-id="5a7c0-139">**Dominio principale**     (Obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="5a7c0-139">**Primary domain**    (Required).</span></span> <span data-ttu-id="5a7c0-140">Il dominio primario è il dominio di base del partner XMPP.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-140">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="5a7c0-141">Ad esempio, è necessario immettere **fabrikam.com** per il nome di dominio del partner XMPP.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-141">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="5a7c0-142">Questa voce è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-142">This is a required entry.</span></span>

6.  <span data-ttu-id="5a7c0-143">**Descrizione/Controlli**     La descrizione è relativa alle note o ad altre informazioni di identificazione per la configurazione specifica.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-143">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="5a7c0-144">Questa voce è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-144">This entry is optional.</span></span>

7.  <span data-ttu-id="5a7c0-145">**Domini aggiuntivi**     I domini aggiuntivi sono domini che fanno parte del dominio del partner XMPP che deve essere incluso come parte della comunicazione XMPP consentita.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-145">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="5a7c0-146">Se ad esempio il dominio primario è **fabrikam.com**, sarà necessario elencare tutti gli altri domini inclusi in fabrikam.com con cui si comunicherà mediante XMPP.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-146">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="5a7c0-147">**Tipo**     di partner Il **tipo di partner** è un'impostazione obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-147">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="5a7c0-148">È necessario selezionare una delle opzioni seguenti per descrivere e applicare i contatti che possono essere aggiunti.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-148">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="5a7c0-149">È possibile selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a7c0-149">You can select from:</span></span>
    
      - <span data-ttu-id="5a7c0-150">**Federata** Un tipo di partner **federato** rappresenta un livello elevato di attendibilità tra la distribuzione di Lync Server e il partner XMPP.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-150">**Federated** A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="5a7c0-151">Questo tipo di partner è consigliato per la federazione con i server XMPP della stessa azienda o in scenari di rapporti professionali consolidati.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-151">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="5a7c0-152">I contatti XMPP nei partner federati possono eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a7c0-152">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="5a7c0-153">Aggiungere contatti Lync e visualizzare le relative informazioni sulla presenza senza autorizzazione esplicita da parte dell'utente Lync.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-153">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="5a7c0-154">Inviare messaggi istantanei a contatti Lync indipendentemente dal fatto che siano stati aggiunti nell'elenco contatti dell'utente Lync.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-154">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="5a7c0-155">Visualizzare le note sullo stato di un utente Lync.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-155">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="5a7c0-156">**Pubblico verificato**   Un partner **verificato pubblico** è un provider XMPP pubblico che è attendibile per verificare l'identità dei propri utenti.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-156">**Public verified** A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="5a7c0-157">I contatti XMPP nelle reti di tipo Verificato pubblico possono aggiungere contatti Lync, visualizzare le relative informazioni sulla presenza e inviare loro messaggi istantanei senza autorizzazione esplicita degli utenti Lync.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-157">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="5a7c0-158">I contatti XMPP nelle reti di tipo Verificato pubblico non visualizzano mai le note sullo stato di un utente Lync.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-158">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="5a7c0-159">Questa impostazione non è consigliata.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-159">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="5a7c0-p112">**Non verificato pubblico**: un partner di tipo **Non verificato pubblico** è un fornitore XMPP pubblico provider, non ritenuto attendibile per la verifica dell'identità dei propri utenti. Gli utenti XMPP nelle reti di tipo Non verificato pubblico possono comunicare con utenti Lync solo se l'utente Lync li ha autorizzati esplicitamente, aggiungendoli all'elenco contatti. Gli utenti XMPP in reti di tipo Non verificato pubblico non possono mai vedere le note di stato degli utenti Lync. Questa impostazione è consigliata per qualsiasi federazione con provider XMPP pubblici, ad esempio Google Talk.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-p112">**Public unverified** A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.  XMPP users on public unverified networks never see Lync users’ status notes.  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="5a7c0-164">**Tipo di connessione**: consente di definire le diverse regole e impostazioni di Dialback.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-164">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="5a7c0-165">**Negoziazione TLS**     Definisce le regole di negoziazione TLS.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-165">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="5a7c0-166">Un servizio XMPP può richiedere la negoziazione TLS, può definirla come facoltativa oppure l'utente può specificare che la negoziazione TLS non è supportata.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-166">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="5a7c0-167">Se si seleziona Facoltativa, l'eventuale obbligatorietà della negoziazione viene decisa dal servizio XMPP.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-167">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="5a7c0-168">Per visualizzare tutte le impostazioni e i dettagli possibili per la negoziazione SASL, TLS e richiamata, incluse le configurazioni degli errori non valide e note, vedere [impostazioni di negoziazione per i partner federati XMPP in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span><span class="sxs-lookup"><span data-stu-id="5a7c0-168">To view all possible settings and details for SASL, TLS and Dialback negotiation – including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span></span>
        
           - <span data-ttu-id="5a7c0-169">**Necessario**     Il servizio XMPP richiede la negoziazione TLS.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-169">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
           - <span data-ttu-id="5a7c0-170">**Facoltativo**     Il servizio XMPP indica che TLS è obbligatorio per la negoziazione.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-170">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="5a7c0-171">**Non supportato**     Il servizio XMPP non supporta TLS.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-171">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="5a7c0-172">**Negoziazione SASL**     Definisce le regole di negoziazione SASL.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-172">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="5a7c0-173">Un servizio XMPP può richiedere la negoziazione SASL, può definirla come facoltativa oppure l'utente può specificare che la negoziazione SASL non è supportata.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-173">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="5a7c0-174">Se si seleziona Facoltativa, l'eventuale obbligatorietà della negoziazione viene decisa dal servizio XMPP del partner.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-174">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
           - <span data-ttu-id="5a7c0-175">**Necessario**     Il servizio XMPP richiede la negoziazione SASL.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-175">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
           - <span data-ttu-id="5a7c0-176">**Facoltativo**     Il servizio XMPP indica che SASL è obbligatorio per la negoziazione.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-176">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="5a7c0-177">**Non supportato**     Il servizio XMPP non supporta SASL.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-177">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="5a7c0-178">**Negoziazione richiamata del server di supporto** Il processo di negoziazione del server di supporto richiamata utilizza il DNS (Domain Name System) e un server autorevole per verificare che la richiesta provenisse da un partner XMPP valido.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-178">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="5a7c0-179">A tale scopo, il server di origine crea un messaggio di un tipo specifico con una chiave richiamata generata e cerca il server di ricezione in DNS.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-179">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="5a7c0-180">Il server di origine invia la chiave in un flusso XML alla ricerca DNS risultante, presumibilmente il server di ricezione.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-180">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="5a7c0-181">Al ricevimento della chiave tramite il flusso XML, il server di ricezione non risponde al server di origine, ma invia la chiave a un server autorevole noto.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-181">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="5a7c0-182">Il server autorevole verifica che la chiave sia valida o non valida.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-182">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="5a7c0-183">Se non è valido, il server di ricezione non risponde al server di origine.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-183">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="5a7c0-184">Se la chiave è valida, il server di ricezione informa il server di origine che l'identità e la chiave sono valide e che la conversazione può iniziare.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-184">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="5a7c0-185">Sono disponibili due stati validi per la negoziazione di tipo **Dialback**:</span><span class="sxs-lookup"><span data-stu-id="5a7c0-185">There are two valid states for **Dialback negotiation**:</span></span>
        
           - <span data-ttu-id="5a7c0-186">**Vero**     Il server XMPP è configurato per l'utilizzo della negoziazione richiamata se una richiesta deve essere ricevuta da un server di origine.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-186">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
           - <span data-ttu-id="5a7c0-187">Valore **false**     Il server XMPP non è configurato per l'utilizzo della negoziazione richiamata e se una richiesta deve essere ricevuta da un server di origine, verrà ignorata.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-187">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="5a7c0-188">Fare clic su **Commit** per salvare le modifiche apportate ai criteri utente o sito.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-188">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="5a7c0-189">Aggiornare i record DNS per il gateway XMPP di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a7c0-189">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="5a7c0-190">Per configurare DNS per la Federazione XMPP, è necessario aggiungere il record SRV seguente al DNS esterno: \_ XMPP-server. \_ TCP.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="5a7c0-190">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\></span></span> <span data-ttu-id="5a7c0-191">Il record SRV si risolverà nell'FQDN del server perimetrale di Access Edge, con un valore di porta pari a 5269.</span><span class="sxs-lookup"><span data-stu-id="5a7c0-191">The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

