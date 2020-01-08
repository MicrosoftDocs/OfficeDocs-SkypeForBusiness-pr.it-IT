---
title: Configurare il gateway XMPP in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49733816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87564835404928a79f9c61974d9581bba68069cd
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "40980611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="12700-102">Configurare il gateway XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12700-102">Configure XMPP gateway on Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12700-103">_**Argomento Ultima modifica:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="12700-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="12700-104">La procedura finale per la migrazione del gateway XMPP consiste nel configurare i certificati per Lync Server 2013 Edge Server, distribuire il gateway XMPP di Lync Server 2013 e aggiornare i record DNS per il gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="12700-104">The final steps for migrating your XMPP Gateway are to configure certificates for the Lync Server 2013 Edge Server, deploy the Lync Server 2013 XMPP Gateway, and update the DNS records for the XMPP Gateway.</span></span> <span data-ttu-id="12700-105">Questi passaggi devono essere eseguiti in parallelo per ridurre al minimo il tempo di discesa del gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="12700-105">These steps should be performed in parallel to minimize the down time of your XMPP Gateway.</span></span> <span data-ttu-id="12700-106">Prima di eseguire questa procedura, tutti gli utenti devono essere spostati nella distribuzione di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12700-106">All users must be moved to your Microsoft Lync Server 2013 deployment before performing these steps.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="12700-107">La Federazione XMPP non è supportata per gli utenti che partecipano a Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="12700-107">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="12700-108">Questo vale sia per vedere le informazioni sulla presenza che per scambiare messaggi di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="12700-108">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="12700-109">Configurare i certificati del gateway XMPP nel server perimetrale di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12700-109">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="12700-110">Nel server perimetro, nella distribuzione guidata, accanto a **passaggio 3: richiedere, installare o assegnare certificati**, fare di nuovo clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="12700-110">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="12700-111">Se si distribuisce il server perimetrale per la prima volta, verrà visualizzato di nuovo Esegui anziché Esegui.</span><span class="sxs-lookup"><span data-stu-id="12700-111">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="12700-112">Nella pagina **attività certificato disponibili** fare clic su **Crea una nuova richiesta di certificato**.</span><span class="sxs-lookup"><span data-stu-id="12700-112">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="12700-113">Nella pagina **richiesta certificato** fare clic su **certificato bordo esterno**.</span><span class="sxs-lookup"><span data-stu-id="12700-113">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="12700-114">Nella pagina **richiesta posticipata o immediata** selezionare la casella di controllo **prepara la richiesta ora, ma inviarla in seguito** .</span><span class="sxs-lookup"><span data-stu-id="12700-114">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="12700-115">Nella pagina **file di richiesta certificato** Digitare il percorso completo e il nome file del file in cui deve essere salvata la richiesta, ad esempio c:\\CERT\_exernal\_Edge. cer.</span><span class="sxs-lookup"><span data-stu-id="12700-115">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="12700-116">Nella pagina **Specifica modello di certificato alternativo** , per usare un modello diverso da quello predefinito del modello webserver, selezionare la casella di controllo **Usa il modello di certificato alternativo per l'autorità di certificazione selezionata** .</span><span class="sxs-lookup"><span data-stu-id="12700-116">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="12700-117">Nella pagina **impostazioni di sicurezza e nome** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="12700-117">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="12700-118">In **nome descrittivo**Digitare un nome visualizzato per il certificato.</span><span class="sxs-lookup"><span data-stu-id="12700-118">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="12700-119">In **bit length**specificare la lunghezza in bit (in genere, il valore predefinito è 2048).</span><span class="sxs-lookup"><span data-stu-id="12700-119">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="12700-120">Verificare che la casella **di controllo contrassegna la chiave privata del certificato come esportabile** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="12700-120">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="12700-121">Nella pagina **informazioni organizzazione** Digitare il nome dell'organizzazione e dell'unità organizzativa, ad esempio divisione o reparto.</span><span class="sxs-lookup"><span data-stu-id="12700-121">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="12700-122">Nella pagina **informazioni geografiche** specificare le informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="12700-122">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="12700-123">Nella pagina **nome oggetto/nomi oggetto alternativo** vengono visualizzate le informazioni che verranno inserite automaticamente dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="12700-123">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="12700-124">Se sono necessari altri nomi alternativi per l'oggetto, è necessario specificarli nei due passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="12700-124">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="12700-125">Nell' **impostazione del dominio SIP nella pagina nome alternativo oggetto (sans)** selezionare la casella di controllo Domain per aggiungere un SIP. \<SipDomain\> voce nell'elenco nomi alternativi oggetto.</span><span class="sxs-lookup"><span data-stu-id="12700-125">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="12700-126">Nella pagina **Configura altri nomi alternativi oggetto** specificare eventuali altri nomi alternativi per gli argomenti necessari.</span><span class="sxs-lookup"><span data-stu-id="12700-126">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="12700-127">Se il proxy XMPP è installato, per impostazione predefinita il nome di dominio, ad esempio contoso.com, viene popolato nelle voci SAN.</span><span class="sxs-lookup"><span data-stu-id="12700-127">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="12700-128">Se sono necessarie altre voci, aggiungerle in questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="12700-128">If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="12700-129">Nella pagina **Riepilogo richieste** verificare le informazioni sul certificato da usare per generare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="12700-129">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="12700-130">Dopo che i comandi hanno terminato l'uso, è possibile **visualizzare il log**oppure fare clic su Avanti per continuare.</span><span class="sxs-lookup"><span data-stu-id="12700-130">After the commands finish running, you can **View Log**, or click Next to continue.</span></span>

15. <span data-ttu-id="12700-131">Nella pagina **file di richiesta di certificato** è possibile visualizzare il file della richiesta di firma del certificato (CSR) generato facendo clic su **Visualizza** o Esci dalla creazione guidata certificato facendo clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="12700-131">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking **View** or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="12700-132">Copiare il file di richiesta e inviarlo all'autorità di certificazione pubblica.</span><span class="sxs-lookup"><span data-stu-id="12700-132">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="12700-133">Dopo la ricezione, l'importazione e l'assegnazione del certificato pubblico, è necessario arrestare e riavviare i servizi Edge Server.</span><span class="sxs-lookup"><span data-stu-id="12700-133">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="12700-134">A tale scopo, digitare la console di gestione di Lync Server:</span><span class="sxs-lookup"><span data-stu-id="12700-134">You do this by typing in the Lync Server Management console:</span></span>
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="12700-135">Configurare un nuovo gateway XMPP di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12700-135">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="12700-136">Aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12700-136">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="12700-137">Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** , quindi fare clic su **partner federati XMPP**.</span><span class="sxs-lookup"><span data-stu-id="12700-137">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="12700-138">Per creare una nuova configurazione, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="12700-138">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="12700-139">Definire le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="12700-139">Define the following settings:</span></span>

5.  <span data-ttu-id="12700-140">**Dominio principale (**     obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="12700-140">**Primary domain**    (Required).</span></span> <span data-ttu-id="12700-141">Il dominio principale è il dominio di base del partner XMPP.</span><span class="sxs-lookup"><span data-stu-id="12700-141">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="12700-142">Ad esempio, immetti **Fabrikam.com** per il nome di dominio partner XMPP.</span><span class="sxs-lookup"><span data-stu-id="12700-142">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="12700-143">Questa è una voce obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="12700-143">This is a required entry.</span></span>

6.  <span data-ttu-id="12700-144">**Descrizione**   la descrizione riguarda le note o altre informazioni di identificazione per questa particolare configurazione.</span><span class="sxs-lookup"><span data-stu-id="12700-144">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="12700-145">Questa voce è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="12700-145">This entry is optional.</span></span>

7.  <span data-ttu-id="12700-146">**Altri**   domini i domini aggiuntivi sono domini che fanno parte del dominio del partner XMPP che deve essere incluso come parte della comunicazione XMPP consentita.</span><span class="sxs-lookup"><span data-stu-id="12700-146">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="12700-147">Ad esempio, se il dominio principale è **Fabrikam.com**, devi elencare tutti gli altri domini in Fabrikam.com con cui comunicherai per mezzo di XMPP.</span><span class="sxs-lookup"><span data-stu-id="12700-147">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="12700-148">**Tipo di partner**   il **tipo di partner** è un'impostazione obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="12700-148">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="12700-149">È necessario scegliere una delle opzioni seguenti per descrivere e applicare i contatti che è possibile aggiungere.</span><span class="sxs-lookup"><span data-stu-id="12700-149">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="12700-150">È possibile selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="12700-150">You can select from:</span></span>
    
      - <span data-ttu-id="12700-151">**Federati**   un tipo di partner **federato** rappresenta un livello elevato di attendibilità tra la distribuzione di Lync Server e il partner XMPP.</span><span class="sxs-lookup"><span data-stu-id="12700-151">**Federated**   A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="12700-152">Questo tipo di partner è consigliato per la Federazione con i server XMPP all'interno della stessa organizzazione o dove esiste una relazione commerciale stabilita.</span><span class="sxs-lookup"><span data-stu-id="12700-152">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="12700-153">I contatti XMPP in partner federati possono:</span><span class="sxs-lookup"><span data-stu-id="12700-153">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="12700-154">Aggiungere contatti di Lync e visualizzare la presenza senza autorizzazione espressa da parte dell'utente di Lync.</span><span class="sxs-lookup"><span data-stu-id="12700-154">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="12700-155">Inviare messaggi istantanei ai contatti di Lync indipendentemente dal fatto che l'utente di Lync li abbia aggiunti nell'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="12700-155">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="12700-156">Vedere le note sullo stato di un utente di Lync.</span><span class="sxs-lookup"><span data-stu-id="12700-156">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="12700-157">**Public Verified**   un partner pubblico **verificato** è un provider XMPP pubblico considerato attendibile per verificare l'identità degli utenti.</span><span class="sxs-lookup"><span data-stu-id="12700-157">**Public verified**   A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="12700-158">I contatti XMPP nelle reti pubbliche verificate possono aggiungere contatti di Lync e visualizzarne la presenza e inviare messaggi istantanei senza autorizzazione espressa degli utenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="12700-158">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="12700-159">I contatti XMPP nelle reti verificate pubbliche non vedono mai le note sullo stato degli utenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="12700-159">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="12700-160">Questa impostazione non è consigliata.</span><span class="sxs-lookup"><span data-stu-id="12700-160">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="12700-161">**Pubblico non verificato**   un partner **pubblico non verificato** è un provider XMPP pubblico che non è considerato attendibile per verificare l'identità degli utenti.</span><span class="sxs-lookup"><span data-stu-id="12700-161">**Public unverified**   A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="12700-162">Gli utenti XMPP su reti pubbliche non verificate non possono comunicare con gli utenti di Lync, a meno che l'utente di Lync non li abbia espressamente autorizzati aggiungendoli all'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="12700-162">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="12700-163">Gli utenti XMPP su reti pubbliche non verificate non vedono mai le note di stato degli utenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="12700-163">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="12700-164">Questa impostazione è consigliata per qualsiasi federazione con provider XMPP pubblici, ad esempio Google Talk.</span><span class="sxs-lookup"><span data-stu-id="12700-164">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="12700-165">**Tipo di connessione:** Definisce le varie regole e le impostazioni di richiamata.</span><span class="sxs-lookup"><span data-stu-id="12700-165">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="12700-166">**La negoziazione**   TLS definisce le regole di negoziazione TLS.</span><span class="sxs-lookup"><span data-stu-id="12700-166">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="12700-167">Un servizio XMPP può richiedere TLS, può rendere facoltativo TLS oppure definire che TLS non è supportato.</span><span class="sxs-lookup"><span data-stu-id="12700-167">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="12700-168">La scelta facoltativa lascia il requisito fino al servizio XMPP per una decisione obbligatorio-negoziare.</span><span class="sxs-lookup"><span data-stu-id="12700-168">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="12700-169">Per visualizzare tutte le impostazioni e i dettagli possibili per la negoziazione SASL, TLS e richiamata, incluse le configurazioni di errore non valide e note, vedere [impostazioni di negoziazione per partner federati XMPP in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="12700-169">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="12700-170">**Obbligatorio**   il servizio XMPP richiede la negoziazione TLS.</span><span class="sxs-lookup"><span data-stu-id="12700-170">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="12700-171">**Facoltativo**   il servizio XMPP indica che TLS è obbligatorio da negoziare.</span><span class="sxs-lookup"><span data-stu-id="12700-171">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="12700-172">**Non supportato**   il servizio XMPP non supporta TLS.</span><span class="sxs-lookup"><span data-stu-id="12700-172">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="12700-173">**La negoziazione**   SASL Definisce le regole di negoziazione SASL.</span><span class="sxs-lookup"><span data-stu-id="12700-173">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="12700-174">Un servizio XMPP può richiedere SASL, può rendere SASL facoltativo o Definisci che SASL non è supportato.</span><span class="sxs-lookup"><span data-stu-id="12700-174">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="12700-175">La scelta facoltativa lascia il requisito fino al servizio XMPP partner per una decisione obbligatorio-to-negotiate.</span><span class="sxs-lookup"><span data-stu-id="12700-175">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
          - <span></span>  
            <span data-ttu-id="12700-176">**Obbligatorio**   il servizio XMPP richiede la negoziazione SASL.</span><span class="sxs-lookup"><span data-stu-id="12700-176">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="12700-177">**Facoltativo**   il servizio XMPP indica che SASL è obbligatorio-negoziare.</span><span class="sxs-lookup"><span data-stu-id="12700-177">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="12700-178">**Non supportato**   il servizio XMPP non supporta SASL.</span><span class="sxs-lookup"><span data-stu-id="12700-178">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="12700-179">**Negoziazione richiamata del server di supporto** Il processo di negoziazione richiamata del server di supporto usa il DNS (Domain Name System) e un server autorevole per verificare che la richiesta provenisse da un partner XMPP valido.</span><span class="sxs-lookup"><span data-stu-id="12700-179">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="12700-180">A questo scopo, il server di origine crea un messaggio di un tipo specifico con una chiave richiamata generata e cerca il server di ricezione nel DNS.</span><span class="sxs-lookup"><span data-stu-id="12700-180">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="12700-181">Il server di origine invia la chiave in un flusso XML alla ricerca DNS risultante, presumibilmente il server di ricezione.</span><span class="sxs-lookup"><span data-stu-id="12700-181">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="12700-182">Al ricevimento della chiave sul flusso XML, il server di ricezione non risponde al server di origine, ma invia la chiave a un server autorevole noto.</span><span class="sxs-lookup"><span data-stu-id="12700-182">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="12700-183">Il server autorevole verifica che la chiave sia valida o non valida.</span><span class="sxs-lookup"><span data-stu-id="12700-183">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="12700-184">Se non è valido, il server di ricezione non risponde al server di origine.</span><span class="sxs-lookup"><span data-stu-id="12700-184">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="12700-185">Se la chiave è valida, il server di ricezione informa il server di origine che l'identità e la chiave sono valide e che la conversazione può iniziare.</span><span class="sxs-lookup"><span data-stu-id="12700-185">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="12700-186">Esistono due stati validi per la **negoziazione richiamata**:</span><span class="sxs-lookup"><span data-stu-id="12700-186">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="12700-187">**True**   il server XMPP è configurato per l'uso della negoziazione richiamata se una richiesta deve essere ricevuta da un server di origine.</span><span class="sxs-lookup"><span data-stu-id="12700-187">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
          - <span></span>  
            <span data-ttu-id="12700-188">**Falso**   il server XMPP non è configurato per l'uso della negoziazione richiamata e se una richiesta deve essere ricevuta da un server di origine, verrà ignorata.</span><span class="sxs-lookup"><span data-stu-id="12700-188">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="12700-189">Fare clic su **conferma** per salvare le modifiche apportate ai criteri per il sito o per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="12700-189">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="12700-190">Aggiornare i record DNS per il gateway XMPP di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12700-190">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="12700-191">Per configurare il DNS per la Federazione XMPP, è possibile aggiungere il record SRV seguente al DNS\_esterno: XMPP-server. \_TCP. \<nome\> di dominio il record SRV verrà risolto nell'FQDN di Access Edge del server Edge, con un valore di porta 5269.</span><span class="sxs-lookup"><span data-stu-id="12700-191">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

