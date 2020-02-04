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
ms.openlocfilehash: 82c7cec94a65a35f4f5141950c4691fec0b28706
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="25b24-102">Configurare il gateway XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25b24-102">Configure XMPP gateway on Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25b24-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="25b24-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="25b24-104">Quando si configurano i criteri per il supporto dei partner federati di Extensible Messaging and Presence Protocol (XMPP), i criteri si applicano agli utenti di domini federati XMPP, ma non agli utenti dei provider di servizi di messaggistica istantanea SIP (Session Initiation Protocol) (ad esempio, Windows Live) o i domini federati SIP.</span><span class="sxs-lookup"><span data-stu-id="25b24-104">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="25b24-105">Si configura un partner federato XMPP per ogni dominio federato XMPP in cui si vuole consentire agli utenti di aggiungere contatti e comunicare.</span><span class="sxs-lookup"><span data-stu-id="25b24-105">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="25b24-106">Una volta posizionati i criteri, altre attività includono la configurazione dei certificati del gateway XMPP, la distribuzione del gateway XMPP di Lync Server 2013 e infine l'aggiornamento dei record DNS per il gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="25b24-106">Once the policies are in place, additional tasks include configuring the XMPP Gateway certificates, deploying the Lync Server 2013 XMPP Gateway, and finally updating the DNS records for the XMPP Gateway.</span></span>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="25b24-107">Configurare i certificati del gateway XMPP nel server perimetrale di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25b24-107">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="25b24-108">Nel server perimetro, nella distribuzione guidata, accanto a **passaggio 3: richiedere, installare o assegnare certificati**, fare di nuovo clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="25b24-108">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="25b24-109">Se si distribuisce il server perimetrale per la prima volta, verrà visualizzato di nuovo Esegui anziché Esegui.</span><span class="sxs-lookup"><span data-stu-id="25b24-109">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="25b24-110">Nella pagina **attività certificato disponibili** fare clic su **Crea una nuova richiesta di certificato**.</span><span class="sxs-lookup"><span data-stu-id="25b24-110">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="25b24-111">Nella pagina **richiesta certificato** fare clic su **certificato bordo esterno**.</span><span class="sxs-lookup"><span data-stu-id="25b24-111">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="25b24-112">Nella pagina **richiesta posticipata o immediata** selezionare la casella di controllo **prepara la richiesta ora, ma inviarla in seguito** .</span><span class="sxs-lookup"><span data-stu-id="25b24-112">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="25b24-113">Nella pagina **file di richiesta certificato** Digitare il percorso completo e il nome file del file in cui deve essere salvata la richiesta, ad esempio c:\\CERT\_exernal\_Edge. cer.</span><span class="sxs-lookup"><span data-stu-id="25b24-113">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="25b24-114">Nella pagina **Specifica modello di certificato alternativo** , per usare un modello diverso da quello predefinito del modello webserver, selezionare la casella di controllo **Usa il modello di certificato alternativo per l'autorità di certificazione selezionata** .</span><span class="sxs-lookup"><span data-stu-id="25b24-114">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="25b24-115">Nella pagina **impostazioni di sicurezza e nome** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="25b24-115">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="25b24-116">In **nome descrittivo**Digitare un nome visualizzato per il certificato.</span><span class="sxs-lookup"><span data-stu-id="25b24-116">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="25b24-117">In **bit length**specificare la lunghezza in bit (in genere, il valore predefinito è 2048).</span><span class="sxs-lookup"><span data-stu-id="25b24-117">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="25b24-118">Verificare che la casella **di controllo contrassegna la chiave privata del certificato come esportabile** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="25b24-118">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="25b24-119">Nella pagina **informazioni organizzazione** Digitare il nome dell'organizzazione e dell'unità organizzativa, ad esempio divisione o reparto.</span><span class="sxs-lookup"><span data-stu-id="25b24-119">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="25b24-120">Nella pagina **informazioni geografiche** specificare le informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="25b24-120">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="25b24-121">Nella pagina **nome oggetto/nomi oggetto alternativo** vengono visualizzate le informazioni che verranno inserite automaticamente dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="25b24-121">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="25b24-122">Se sono necessari altri nomi alternativi per l'oggetto, è necessario specificarli nei due passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="25b24-122">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="25b24-123">Nell' **impostazione del dominio SIP nella pagina nome alternativo oggetto (sans)** selezionare la casella di controllo Domain per aggiungere un SIP. \<SipDomain\> voce nell'elenco nomi alternativi oggetto.</span><span class="sxs-lookup"><span data-stu-id="25b24-123">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="25b24-124">Nella pagina **Configura altri nomi alternativi oggetto** specificare eventuali altri nomi alternativi per gli argomenti necessari.</span><span class="sxs-lookup"><span data-stu-id="25b24-124">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="25b24-125">Se il proxy XMPP è installato, per impostazione predefinita il nome di dominio, ad esempio contoso.com, viene popolato nelle voci SAN.</span><span class="sxs-lookup"><span data-stu-id="25b24-125">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="25b24-126">Se sono necessarie altre voci, aggiungerle in questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="25b24-126">If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="25b24-127">Nella pagina **Riepilogo richieste** verificare le informazioni sul certificato da usare per generare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="25b24-127">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="25b24-128">Dopo che i comandi hanno terminato l'uso, è possibile **visualizzare il log**oppure fare clic su **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="25b24-128">After the commands finish running, you can **View Log**, or click **Next** to continue.</span></span>

15. <span data-ttu-id="25b24-129">Nella pagina **file di richiesta di certificato** è possibile visualizzare il file della richiesta di firma del certificato (CSR) generato facendo clic su Visualizza o Esci dalla creazione guidata certificato facendo clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="25b24-129">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="25b24-130">Copiare il file di richiesta e inviarlo all'autorità di certificazione pubblica.</span><span class="sxs-lookup"><span data-stu-id="25b24-130">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="25b24-131">Dopo la ricezione, l'importazione e l'assegnazione del certificato pubblico, è necessario arrestare e riavviare i servizi Edge Server.</span><span class="sxs-lookup"><span data-stu-id="25b24-131">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="25b24-132">A tale scopo, digitare la console di gestione di Lync Server:</span><span class="sxs-lookup"><span data-stu-id="25b24-132">You do this by typing in the Lync Server Management console:</span></span>
    
       ```console
        Stop-CsWindowsService
       ```
    
       ```console
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="25b24-133">Configurare un nuovo gateway XMPP di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25b24-133">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="25b24-134">Aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="25b24-134">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="25b24-135">Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** , quindi fare clic su **partner federati XMPP**.</span><span class="sxs-lookup"><span data-stu-id="25b24-135">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="25b24-136">Per creare una nuova configurazione, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="25b24-136">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="25b24-137">Definire le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="25b24-137">Define the following settings:</span></span>

5.  <span data-ttu-id="25b24-138">**Dominio principale (**     obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="25b24-138">**Primary domain**    (Required).</span></span> <span data-ttu-id="25b24-139">Il dominio principale è il dominio di base del partner XMPP.</span><span class="sxs-lookup"><span data-stu-id="25b24-139">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="25b24-140">Ad esempio, immetti **Fabrikam.com** per il nome di dominio partner XMPP.</span><span class="sxs-lookup"><span data-stu-id="25b24-140">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="25b24-141">Questa è una voce obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="25b24-141">This is a required entry.</span></span>

6.  <span data-ttu-id="25b24-142">**Descrizione**   la descrizione riguarda le note o altre informazioni di identificazione per questa particolare configurazione.</span><span class="sxs-lookup"><span data-stu-id="25b24-142">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="25b24-143">Questa voce è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="25b24-143">This entry is optional.</span></span>

7.  <span data-ttu-id="25b24-144">**Altri**   domini i domini aggiuntivi sono domini che fanno parte del dominio del partner XMPP che deve essere incluso come parte della comunicazione XMPP consentita.</span><span class="sxs-lookup"><span data-stu-id="25b24-144">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="25b24-145">Ad esempio, se il dominio principale è **Fabrikam.com**, devi elencare tutti gli altri domini in Fabrikam.com con cui comunicherai per mezzo di XMPP.</span><span class="sxs-lookup"><span data-stu-id="25b24-145">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="25b24-146">**Tipo di partner**   il **tipo di partner** è un'impostazione obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="25b24-146">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="25b24-147">È necessario scegliere una delle opzioni seguenti per descrivere e applicare i contatti che è possibile aggiungere.</span><span class="sxs-lookup"><span data-stu-id="25b24-147">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="25b24-148">È possibile selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="25b24-148">You can select from:</span></span>
    
      - <span data-ttu-id="25b24-149">**Federati** Un tipo di partner **federato** rappresenta un livello elevato di attendibilità tra la distribuzione di Lync Server e il partner XMPP.</span><span class="sxs-lookup"><span data-stu-id="25b24-149">**Federated** A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="25b24-150">Questo tipo di partner è consigliato per la Federazione con i server XMPP all'interno della stessa organizzazione o dove esiste una relazione commerciale stabilita.</span><span class="sxs-lookup"><span data-stu-id="25b24-150">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="25b24-151">I contatti XMPP in partner federati possono:</span><span class="sxs-lookup"><span data-stu-id="25b24-151">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="25b24-152">Aggiungere contatti di Lync e visualizzare la presenza senza autorizzazione espressa da parte dell'utente di Lync.</span><span class="sxs-lookup"><span data-stu-id="25b24-152">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="25b24-153">Inviare messaggi istantanei ai contatti di Lync indipendentemente dal fatto che l'utente di Lync li abbia aggiunti nell'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="25b24-153">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="25b24-154">Vedere le note sullo stato di un utente di Lync.</span><span class="sxs-lookup"><span data-stu-id="25b24-154">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="25b24-155">**Public Verified** un partner pubblico **verificato** è un provider XMPP pubblico considerato attendibile per verificare l'identità degli utenti.</span><span class="sxs-lookup"><span data-stu-id="25b24-155">**Public verified** A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="25b24-156">I contatti XMPP nelle reti pubbliche verificate possono aggiungere contatti di Lync e visualizzarne la presenza e inviare messaggi istantanei senza autorizzazione espressa degli utenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="25b24-156">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="25b24-157">I contatti XMPP nelle reti verificate pubbliche non vedono mai le note sullo stato degli utenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="25b24-157">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="25b24-158">Questa impostazione non è consigliata.</span><span class="sxs-lookup"><span data-stu-id="25b24-158">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="25b24-159">**Pubblico non verificato** Un partner **pubblico non verificato** è un provider XMPP pubblico che non è considerato attendibile per verificare l'identità degli utenti.</span><span class="sxs-lookup"><span data-stu-id="25b24-159">**Public unverified** A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="25b24-160">Gli utenti XMPP su reti pubbliche non verificate non possono comunicare con gli utenti di Lync, a meno che l'utente di Lync non li abbia espressamente autorizzati aggiungendoli all'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="25b24-160">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="25b24-161">Gli utenti XMPP su reti pubbliche non verificate non vedono mai le note di stato degli utenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="25b24-161">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="25b24-162">Questa impostazione è consigliata per qualsiasi federazione con provider XMPP pubblici, ad esempio Google Talk.</span><span class="sxs-lookup"><span data-stu-id="25b24-162">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="25b24-163">**Tipo di connessione:** Definisce le varie regole e le impostazioni di richiamata.</span><span class="sxs-lookup"><span data-stu-id="25b24-163">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="25b24-164">**La negoziazione**   TLS definisce le regole di negoziazione TLS.</span><span class="sxs-lookup"><span data-stu-id="25b24-164">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="25b24-165">Un servizio XMPP può richiedere TLS, può rendere facoltativo TLS oppure definire che TLS non è supportato.</span><span class="sxs-lookup"><span data-stu-id="25b24-165">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="25b24-166">La scelta facoltativa lascia il requisito fino al servizio XMPP per una decisione obbligatorio-negoziare.</span><span class="sxs-lookup"><span data-stu-id="25b24-166">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="25b24-167">Per visualizzare tutte le impostazioni e i dettagli possibili per la negoziazione SASL, TLS e richiamata, incluse le configurazioni di errore non valide e note, vedere [impostazioni di negoziazione per partner federati XMPP in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span><span class="sxs-lookup"><span data-stu-id="25b24-167">To view all possible settings and details for SASL, TLS and Dialback negotiation – including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span></span>
        
           - <span data-ttu-id="25b24-168">**Obbligatorio**   il servizio XMPP richiede la negoziazione TLS.</span><span class="sxs-lookup"><span data-stu-id="25b24-168">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
           - <span data-ttu-id="25b24-169">**Facoltativo**   il servizio XMPP indica che TLS è obbligatorio da negoziare.</span><span class="sxs-lookup"><span data-stu-id="25b24-169">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="25b24-170">**Non supportato**   il servizio XMPP non supporta TLS.</span><span class="sxs-lookup"><span data-stu-id="25b24-170">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="25b24-171">**La negoziazione**   SASL Definisce le regole di negoziazione SASL.</span><span class="sxs-lookup"><span data-stu-id="25b24-171">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="25b24-172">Un servizio XMPP può richiedere SASL, può rendere SASL facoltativo o Definisci che SASL non è supportato.</span><span class="sxs-lookup"><span data-stu-id="25b24-172">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="25b24-173">La scelta facoltativa lascia il requisito fino al servizio XMPP partner per una decisione obbligatorio-to-negotiate.</span><span class="sxs-lookup"><span data-stu-id="25b24-173">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
           - <span data-ttu-id="25b24-174">**Obbligatorio**   il servizio XMPP richiede la negoziazione SASL.</span><span class="sxs-lookup"><span data-stu-id="25b24-174">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
           - <span data-ttu-id="25b24-175">**Facoltativo**   il servizio XMPP indica che SASL è obbligatorio-negoziare.</span><span class="sxs-lookup"><span data-stu-id="25b24-175">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="25b24-176">**Non supportato**   il servizio XMPP non supporta SASL.</span><span class="sxs-lookup"><span data-stu-id="25b24-176">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="25b24-177">**Negoziazione richiamata del server di supporto** Il processo di negoziazione richiamata del server di supporto usa il DNS (Domain Name System) e un server autorevole per verificare che la richiesta provenisse da un partner XMPP valido.</span><span class="sxs-lookup"><span data-stu-id="25b24-177">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="25b24-178">A questo scopo, il server di origine crea un messaggio di un tipo specifico con una chiave richiamata generata e cerca il server di ricezione nel DNS.</span><span class="sxs-lookup"><span data-stu-id="25b24-178">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="25b24-179">Il server di origine invia la chiave in un flusso XML alla ricerca DNS risultante, presumibilmente il server di ricezione.</span><span class="sxs-lookup"><span data-stu-id="25b24-179">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="25b24-180">Al ricevimento della chiave sul flusso XML, il server di ricezione non risponde al server di origine, ma invia la chiave a un server autorevole noto.</span><span class="sxs-lookup"><span data-stu-id="25b24-180">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="25b24-181">Il server autorevole verifica che la chiave sia valida o non valida.</span><span class="sxs-lookup"><span data-stu-id="25b24-181">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="25b24-182">Se non è valido, il server di ricezione non risponde al server di origine.</span><span class="sxs-lookup"><span data-stu-id="25b24-182">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="25b24-183">Se la chiave è valida, il server di ricezione informa il server di origine che l'identità e la chiave sono valide e che la conversazione può iniziare.</span><span class="sxs-lookup"><span data-stu-id="25b24-183">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="25b24-184">Esistono due stati validi per la **negoziazione richiamata**:</span><span class="sxs-lookup"><span data-stu-id="25b24-184">There are two valid states for **Dialback negotiation**:</span></span>
        
           - <span data-ttu-id="25b24-185">**True**   il server XMPP è configurato per l'uso della negoziazione richiamata se una richiesta deve essere ricevuta da un server di origine.</span><span class="sxs-lookup"><span data-stu-id="25b24-185">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
           - <span data-ttu-id="25b24-186">**Falso**   il server XMPP non è configurato per l'uso della negoziazione richiamata e se una richiesta deve essere ricevuta da un server di origine, verrà ignorata.</span><span class="sxs-lookup"><span data-stu-id="25b24-186">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="25b24-187">Fare clic su **conferma** per salvare le modifiche apportate ai criteri per il sito o per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="25b24-187">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="25b24-188">Aggiornare i record DNS per il gateway XMPP di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25b24-188">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="25b24-189">Per configurare il DNS per la Federazione XMPP, è possibile aggiungere il record SRV seguente al DNS\_esterno: XMPP-server. \_TCP. \<nome\> di dominio il record SRV verrà risolto nell'FQDN di Access Edge del server Edge, con un valore di porta 5269.</span><span class="sxs-lookup"><span data-stu-id="25b24-189">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

