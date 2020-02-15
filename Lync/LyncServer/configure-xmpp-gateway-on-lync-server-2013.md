---
title: Configurare il gateway XMPP in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49733816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5d75f2e52daed2968d264a2a3eef1bf16bc35b1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="b9792-102">Configurare il gateway XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9792-102">Configure XMPP gateway on Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9792-103">_**Ultimo argomento modificato:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="b9792-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="b9792-104">I passaggi finali per la migrazione del gateway XMPP sono la configurazione dei certificati per il server perimetrale di Lync Server 2013, la distribuzione del gateway XMPP di Lync Server 2013 e l'aggiornamento dei record DNS per il gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="b9792-104">The final steps for migrating your XMPP Gateway are to configure certificates for the Lync Server 2013 Edge Server, deploy the Lync Server 2013 XMPP Gateway, and update the DNS records for the XMPP Gateway.</span></span> <span data-ttu-id="b9792-105">Queste operazioni devono essere eseguite in parallelo per ridurre al minimo il tempo di inattività del gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="b9792-105">These steps should be performed in parallel to minimize the down time of your XMPP Gateway.</span></span> <span data-ttu-id="b9792-106">Prima di eseguire questa procedura, è necessario spostare tutti gli utenti nella distribuzione di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9792-106">All users must be moved to your Microsoft Lync Server 2013 deployment before performing these steps.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="b9792-107">La Federazione XMPP non è supportata per gli utenti ospitati in Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="b9792-107">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="b9792-108">Ciò vale sia per la visualizzazione delle informazioni sulla presenza che per lo scambio di messaggi di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="b9792-108">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="b9792-109">Configurare i certificati del gateway XMPP nel server perimetrale Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9792-109">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="b9792-110">Nel server perimetrale fare clic su **Riesegui** nella Distribuzione guidata accanto a **Passaggio 3: Richiesta, installazione o assegnazione dei certificati**.</span><span class="sxs-lookup"><span data-stu-id="b9792-110">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="b9792-111">Se si distribuisce il server perimetrale per la prima volta, sarà disponibile il pulsante Esegui anziché Riesegui.</span><span class="sxs-lookup"><span data-stu-id="b9792-111">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="b9792-112">Nella pagina **Attività certificato disponibili** fare clic su **Crea una nuova richiesta di certificato**.</span><span class="sxs-lookup"><span data-stu-id="b9792-112">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="b9792-113">Nella pagina **Richiesta di certificato** fare clic su **Certificato perimetro esterno**.</span><span class="sxs-lookup"><span data-stu-id="b9792-113">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="b9792-114">Nella pagina **Richieste immediate o ritardate** selezionare la casella di controllo **Prepara la richiesta per l'invio posticipato**.</span><span class="sxs-lookup"><span data-stu-id="b9792-114">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="b9792-115">Nella pagina **file richiesta di certificato** Digitare il percorso completo e il nome del file in cui deve essere salvata la richiesta (ad esempio, c:\\CERT\_esterni\_Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="b9792-115">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="b9792-116">Nella pagina **Specifica modello di certificato alternativo**, per utilizzare un modello diverso dal modello Web Server predefinito selezionare la casella di controllo **Utilizza modello di certificato alternativo per l'autorità di certificazione selezionata**.</span><span class="sxs-lookup"><span data-stu-id="b9792-116">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="b9792-117">Nella pagina **Impostazioni nome e sicurezza** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9792-117">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="b9792-118">In **Nome descrittivo** digitare un nome visualizzato per il certificato.</span><span class="sxs-lookup"><span data-stu-id="b9792-118">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="b9792-119">In **Lunghezza bit** specificare la lunghezza in bit (in genere il valore predefinito 2048).</span><span class="sxs-lookup"><span data-stu-id="b9792-119">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="b9792-120">Verificare che la casella di controllo **Contrassegna come esportabile la chiave di certificato privata** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="b9792-120">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="b9792-121">Nella pagina **Informazioni sull'organizzazione** digitare il nome dell'organizzazione e dell'unità organizzativa, ad esempio una divisione o un reparto.</span><span class="sxs-lookup"><span data-stu-id="b9792-121">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="b9792-122">Nella pagina **Dati geografici** specificare le informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="b9792-122">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="b9792-p103">Nella pagina **Nome soggetto / Nomi soggetto alternativi** verranno visualizzate le informazioni compilate automaticamente dalla procedura guidata. Se sono necessari ulteriori nomi alternativi soggetto, specificarli nei prossimi due passaggi.</span><span class="sxs-lookup"><span data-stu-id="b9792-p103">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="b9792-125">Nella pagina **impostazione dominio SIP su nomi soggetto alternativi (San)** selezionare la casella di controllo Domain per aggiungere un SIP. \<voce\> SipDomain all'elenco dei nomi alternativi del soggetto.</span><span class="sxs-lookup"><span data-stu-id="b9792-125">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="b9792-126">Nella pagina **Configura nomi alternativi soggetto aggiuntivi** specificare eventuali nomi alternativi del soggetto aggiuntivi necessari.</span><span class="sxs-lookup"><span data-stu-id="b9792-126">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="b9792-p104">Se è installato il proxy XMPP, per impostazione predefinita le voci SAN vengono popolate con il nome di dominio, ad esempio contoso.com. Se sono necessarie ulteriori voci, aggiungerle in questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="b9792-p104">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="b9792-129">Nella pagina **Riepilogo richiesta** esaminare le informazioni sul certificato da utilizzare per generare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="b9792-129">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="b9792-130">Dopo l'esecuzione del comando, è possibile scegliere **Visualizza Log** oppure fare clic su Avanti per continuare.</span><span class="sxs-lookup"><span data-stu-id="b9792-130">After the commands finish running, you can **View Log**, or click Next to continue.</span></span>

15. <span data-ttu-id="b9792-131">Nella pagina **File richiesta di certificato** è possibile visualizzare il file di richiesta di firma del certificato (CSR) generato facendo clic su **Visualizza** oppure uscire dalla Configurazione guidata certificati facendo clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="b9792-131">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking **View** or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="b9792-132">Copiare il file di richiesta e inviarlo all'autorità di certificazione pubblica.</span><span class="sxs-lookup"><span data-stu-id="b9792-132">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="b9792-p105">Dopo aver ricevuto, importato e assegnato il certificato pubblico, è necessario arrestare e riavviare i servizi del server perimetrale. A tale scopo, digitare quanto segue nella console di gestione di Lync Server:</span><span class="sxs-lookup"><span data-stu-id="b9792-p105">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="b9792-135">Configurare un nuovo gateway XMPP di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9792-135">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="b9792-136">Aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b9792-136">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="b9792-137">Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Partner federati XMPP**.</span><span class="sxs-lookup"><span data-stu-id="b9792-137">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="b9792-138">Per creare una nuova configurazione, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b9792-138">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="b9792-139">Definire le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9792-139">Define the following settings:</span></span>

5.  <span data-ttu-id="b9792-140">**Dominio primario (**     obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="b9792-140">**Primary domain**    (Required).</span></span> <span data-ttu-id="b9792-141">Il dominio primario è il dominio di base del partner XMPP.</span><span class="sxs-lookup"><span data-stu-id="b9792-141">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="b9792-142">Ad esempio, è necessario immettere **fabrikam.com** per il nome di dominio del partner XMPP.</span><span class="sxs-lookup"><span data-stu-id="b9792-142">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="b9792-143">Questa voce è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="b9792-143">This is a required entry.</span></span>

6.  <span data-ttu-id="b9792-144">**Descrizione**   la descrizione è relativa alle note o ad altre informazioni di identificazione per la configurazione specifica.</span><span class="sxs-lookup"><span data-stu-id="b9792-144">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="b9792-145">Questa voce è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="b9792-145">This entry is optional.</span></span>

7.  <span data-ttu-id="b9792-146">**Domini aggiuntivi**   ulteriori domini sono domini che fanno parte del dominio del partner XMPP che deve essere incluso come parte della comunicazione XMPP consentita.</span><span class="sxs-lookup"><span data-stu-id="b9792-146">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="b9792-147">Se ad esempio il dominio primario è **fabrikam.com**, sarà necessario elencare tutti gli altri domini inclusi in fabrikam.com con cui si comunicherà mediante XMPP.</span><span class="sxs-lookup"><span data-stu-id="b9792-147">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="b9792-148">**Tipo di partner**   il **tipo di partner** è un'impostazione obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="b9792-148">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="b9792-149">È necessario selezionare una delle opzioni seguenti per descrivere e applicare i contatti che possono essere aggiunti.</span><span class="sxs-lookup"><span data-stu-id="b9792-149">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="b9792-150">È possibile selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9792-150">You can select from:</span></span>
    
      - <span data-ttu-id="b9792-151">**Federata**   un tipo di partner **federato** rappresenta un livello elevato di attendibilità tra la distribuzione di Lync Server e il partner XMPP.</span><span class="sxs-lookup"><span data-stu-id="b9792-151">**Federated**   A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="b9792-152">Questo tipo di partner è consigliato per la federazione con i server XMPP della stessa azienda o in scenari di rapporti professionali consolidati.</span><span class="sxs-lookup"><span data-stu-id="b9792-152">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="b9792-153">I contatti XMPP nei partner federati possono eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9792-153">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="b9792-154">Aggiungere contatti Lync e visualizzare le relative informazioni sulla presenza senza autorizzazione esplicita da parte dell'utente Lync.</span><span class="sxs-lookup"><span data-stu-id="b9792-154">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="b9792-155">Inviare messaggi istantanei a contatti Lync indipendentemente dal fatto che siano stati aggiunti nell'elenco contatti dell'utente Lync.</span><span class="sxs-lookup"><span data-stu-id="b9792-155">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="b9792-156">Visualizzare le note sullo stato di un utente Lync.</span><span class="sxs-lookup"><span data-stu-id="b9792-156">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="b9792-157">**Public Verified**   un partner **verificato** pubblico è un provider XMPP pubblico che è attendibile per verificare l'identità dei propri utenti.</span><span class="sxs-lookup"><span data-stu-id="b9792-157">**Public verified**   A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="b9792-158">I contatti XMPP nelle reti di tipo Verificato pubblico possono aggiungere contatti Lync, visualizzare le relative informazioni sulla presenza e inviare loro messaggi istantanei senza autorizzazione esplicita degli utenti Lync.</span><span class="sxs-lookup"><span data-stu-id="b9792-158">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="b9792-159">I contatti XMPP nelle reti di tipo Verificato pubblico non visualizzano mai le note sullo stato di un utente Lync.</span><span class="sxs-lookup"><span data-stu-id="b9792-159">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="b9792-160">Questa impostazione non è consigliata.</span><span class="sxs-lookup"><span data-stu-id="b9792-160">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="b9792-161">**Pubblico non verificato**   un partner **pubblico non verificato** è un provider XMPP pubblico che non è attendibile per verificare l'identità dei propri utenti.</span><span class="sxs-lookup"><span data-stu-id="b9792-161">**Public unverified**   A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="b9792-162">Gli utenti XMPP delle reti di tipo Non verificato pubblico non possono comunicare con gli utenti Lync a meno che non siano stati esplicitamente autorizzati dall'utente Lync con l'aggiunta nell'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="b9792-162">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="b9792-163">Gli utenti XMPP nelle reti di tipo Non verificato pubblico non visualizzano mai le note sullo stato degli utenti Lync.</span><span class="sxs-lookup"><span data-stu-id="b9792-163">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="b9792-164">Questa impostazione è consigliata per le federazioni con provider XMPP pubblici come Google Talk.</span><span class="sxs-lookup"><span data-stu-id="b9792-164">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="b9792-165">**Tipo di connessione** Consente di definire le diverse regole e impostazioni di dialback.</span><span class="sxs-lookup"><span data-stu-id="b9792-165">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="b9792-166">**La negoziazione**   TLS definisce le regole di negoziazione TLS.</span><span class="sxs-lookup"><span data-stu-id="b9792-166">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="b9792-167">Un servizio XMPP può richiedere la negoziazione TLS, può definirla come facoltativa oppure l'utente può specificare che la negoziazione TLS non è supportata.</span><span class="sxs-lookup"><span data-stu-id="b9792-167">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="b9792-168">Se si seleziona Facoltativa, l'eventuale obbligatorietà della negoziazione viene decisa dal servizio XMPP.</span><span class="sxs-lookup"><span data-stu-id="b9792-168">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="b9792-169">Per visualizzare tutte le impostazioni e i dettagli possibili per la negoziazione SASL, TLS e richiamata, incluse le configurazioni degli errori non valide e note, vedere [impostazioni di negoziazione per i partner federati XMPP in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="b9792-169">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="b9792-170">**Required**   il servizio XMPP richiede la negoziazione TLS.</span><span class="sxs-lookup"><span data-stu-id="b9792-170">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="b9792-171">**Facoltativo**   il servizio XMPP indica che TLS è obbligatorio per la negoziazione.</span><span class="sxs-lookup"><span data-stu-id="b9792-171">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="b9792-172">**Non supportato**   il servizio XMPP non supporta TLS.</span><span class="sxs-lookup"><span data-stu-id="b9792-172">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="b9792-173">**La negoziazione**   SASL Definisce le regole di negoziazione SASL.</span><span class="sxs-lookup"><span data-stu-id="b9792-173">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="b9792-174">Un servizio XMPP può richiedere la negoziazione SASL, può definirla come facoltativa oppure l'utente può specificare che la negoziazione SASL non è supportata.</span><span class="sxs-lookup"><span data-stu-id="b9792-174">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="b9792-175">Se si seleziona Facoltativa, l'eventuale obbligatorietà della negoziazione viene decisa dal servizio XMPP del partner.</span><span class="sxs-lookup"><span data-stu-id="b9792-175">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
          - <span></span>  
            <span data-ttu-id="b9792-176">**Required**   il servizio XMPP richiede la negoziazione SASL.</span><span class="sxs-lookup"><span data-stu-id="b9792-176">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="b9792-177">**Facoltativo**   il servizio XMPP indica che SASL è obbligatorio per la negoziazione.</span><span class="sxs-lookup"><span data-stu-id="b9792-177">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="b9792-178">**Non supportato**   il servizio XMPP non supporta SASL.</span><span class="sxs-lookup"><span data-stu-id="b9792-178">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="b9792-179">**Negoziazione richiamata del server di supporto** Il processo di negoziazione del server di supporto richiamata utilizza il DNS (Domain Name System) e un server autorevole per verificare che la richiesta provenisse da un partner XMPP valido.</span><span class="sxs-lookup"><span data-stu-id="b9792-179">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="b9792-180">A tale scopo, il server di origine crea un messaggio di un tipo specifico con una chiave richiamata generata e cerca il server di ricezione in DNS.</span><span class="sxs-lookup"><span data-stu-id="b9792-180">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="b9792-181">Il server di origine invia la chiave in un flusso XML alla ricerca DNS risultante, presumibilmente il server di ricezione.</span><span class="sxs-lookup"><span data-stu-id="b9792-181">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="b9792-182">Al ricevimento della chiave tramite il flusso XML, il server di ricezione non risponde al server di origine, ma invia la chiave a un server autorevole noto.</span><span class="sxs-lookup"><span data-stu-id="b9792-182">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="b9792-183">Il server autorevole verifica che la chiave sia valida o non valida.</span><span class="sxs-lookup"><span data-stu-id="b9792-183">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="b9792-184">Se non è valido, il server di ricezione non risponde al server di origine.</span><span class="sxs-lookup"><span data-stu-id="b9792-184">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="b9792-185">Se la chiave è valida, il server di ricezione informa il server di origine che l'identità e la chiave sono valide e che la conversazione può iniziare.</span><span class="sxs-lookup"><span data-stu-id="b9792-185">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="b9792-186">Sono disponibili due stati validi per la negoziazione di tipo **Dialback**:</span><span class="sxs-lookup"><span data-stu-id="b9792-186">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="b9792-187">**True**   il server XMPP è configurato per l'utilizzo della negoziazione richiamata se una richiesta deve essere ricevuta da un server di origine.</span><span class="sxs-lookup"><span data-stu-id="b9792-187">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
          - <span></span>  
            <span data-ttu-id="b9792-188">**False**   il server XMPP non è configurato per l'utilizzo della negoziazione richiamata e se una richiesta deve essere ricevuta da un server di origine, verrà ignorata.</span><span class="sxs-lookup"><span data-stu-id="b9792-188">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="b9792-189">Fare clic su **Commit** per salvare le modifiche apportate ai criteri utente o sito.</span><span class="sxs-lookup"><span data-stu-id="b9792-189">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="b9792-190">Aggiornare i record DNS per il gateway XMPP di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9792-190">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="b9792-191">Per configurare DNS per la Federazione XMPP, è necessario aggiungere il record SRV seguente al DNS esterno\_: XMPP-server. \_TCP. \<nome\> di dominio il record SRV verrà risolto nell'FQDN del server perimetrale di Access Edge, con un valore di porta pari a 5269.</span><span class="sxs-lookup"><span data-stu-id="b9792-191">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

