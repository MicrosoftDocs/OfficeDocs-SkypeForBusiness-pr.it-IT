---
title: 'Lync Server 2013: configurazione della Federazione XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6cbe8db6b432f8e837e110875881e86adab9c51
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="730bb-102">Configurazione della Federazione XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="730bb-102">Setting up XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="730bb-103">_**Ultimo argomento modificato:** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="730bb-103">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="730bb-p101">Per distribuire il proxy XMPP nel server perimetrale, è necessario configurare il server perimetrale per la federazione XMPP. A tale scopo, eseguire le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="730bb-p101">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation. To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="730bb-106">Configurazione della federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="730bb-106">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="730bb-107">Accedere al computer in cui è installata la Distribuzione guidata di Lync Server come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="730bb-107">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="730bb-p102">Nel Front End Server aprire la Distribuzione guidata di Lync Server. Fare clic su Installa o aggiorna il sistema Lync Server e quindi su Installazione o rimozione componenti di Lync Server. Fare clic su Riesegui.</span><span class="sxs-lookup"><span data-stu-id="730bb-p102">On the Front End server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

3.  <span data-ttu-id="730bb-p103">In Installazione componenti di Lync Server fare clic su Avanti. Nella schermata di riepilogo sono mostrate le azioni che vengono eseguite. Al termine della distribuzione, fare clic su Visualizza log per visualizzare i file di log disponibili. Fare clic su Fine per completare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="730bb-p103">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="730bb-p104">Nel server perimetrale aprire la Distribuzione guidata di Lync Server. Fare clic su Installa o aggiorna il sistema Lync Server e quindi su Installazione o rimozione componenti di Lync Server. Fare clic su Riesegui.</span><span class="sxs-lookup"><span data-stu-id="730bb-p104">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="730bb-p105">In Installazione componenti di Lync Server fare clic su Avanti. Nella schermata di riepilogo verranno visualizzate le azioni in esecuzione. Al termine della distribuzione, fare clic su Visualizza log per visualizzare i file di log disponibili. Fare clic su Fine per completare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="730bb-p105">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="730bb-122">Nel server perimetrale, nella Distribuzione guidata fare clic su Riesegui accanto a Passaggio 3: Richiesta, installazione o assegnazione dei certificati.</span><span class="sxs-lookup"><span data-stu-id="730bb-122">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="730bb-123">Se si tratta della prima distribuzione del server perimetrale, verrà visualizzato il comando Esegui anziché Riesegui.</span><span class="sxs-lookup"><span data-stu-id="730bb-123">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="730bb-124">Nella pagina Attività certificato disponibili fare clic su Crea una nuova richiesta di certificato.</span><span class="sxs-lookup"><span data-stu-id="730bb-124">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="730bb-125">Nella pagina richiesta di certificato fare clic su Certificato perimetro esterno.</span><span class="sxs-lookup"><span data-stu-id="730bb-125">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="730bb-126">Nella pagina Richiesta posticipata o immediata selezionare la casella di controllo Prepara la richiesta per l'invio posticipato.</span><span class="sxs-lookup"><span data-stu-id="730bb-126">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="730bb-127">Nella pagina file richiesta di certificato digitare il percorso completo e il nome del file in cui deve essere salvata la richiesta (ad esempio, c:\\CERT\_esterni\_Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="730bb-127">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="730bb-128">Nella pagina Specifica modello di certificato alternativo selezionare la casella di controllo Utilizza modello di certificato alternativo per l'autorità di certificazione selezionata, per utilizzare un modello diverso dal modello Web Server predefinito.</span><span class="sxs-lookup"><span data-stu-id="730bb-128">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="730bb-129">Nella pagina Impostazioni nome e sicurezza eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="730bb-129">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="730bb-130">In Nome descrittivo digitare un nome visualizzato per il certificato.</span><span class="sxs-lookup"><span data-stu-id="730bb-130">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="730bb-131">In Lunghezza bit specificare la lunghezza in bit (di solito, l'impostazione predefinita 2048).</span><span class="sxs-lookup"><span data-stu-id="730bb-131">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="730bb-132">Verificare che la casella di controllo Contrassegna come esportabile la chiave di certificato privata sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="730bb-132">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="730bb-133">Nella pagina Informazioni sull'organizzazione digitare il nome per l'organizzazione e l'unità organizzativa, ad esempio una divisione o un reparto.</span><span class="sxs-lookup"><span data-stu-id="730bb-133">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="730bb-134">Nella pagina Dati geografici specificare le informazioni sulla località.</span><span class="sxs-lookup"><span data-stu-id="730bb-134">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="730bb-p106">Nella pagina Nome soggetto/Nomi soggetto alternativi verranno visualizzate le informazioni compilate automaticamente dalla procedura guidata. Se sono necessari ulteriori nomi alternativi soggetto, specificarli nei prossimi due passaggi.</span><span class="sxs-lookup"><span data-stu-id="730bb-p106">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="730bb-137">Nella pagina Impostazione dominio SIP su nomi soggetto alternativi (San) selezionare la casella di controllo Domain per aggiungere un SIP. \<voce\> SipDomain all'elenco dei nomi alternativi del soggetto.</span><span class="sxs-lookup"><span data-stu-id="730bb-137">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="730bb-138">Nella pagina Configura nomi alternativi soggetto aggiuntivi specificare eventuali nomi alternativi soggetto aggiuntivi richiesti.</span><span class="sxs-lookup"><span data-stu-id="730bb-138">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="730bb-p107">Se è installato il proxy XMPP, per impostazione predefinita il nome di dominio (ad esempio contoso.com) viene compilato nelle voci SAN. Se sono necessarie ulteriori voci, aggiungerle in questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="730bb-p107">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="730bb-141">Nella pagina Riepilogo richiesta esaminare le informazioni sul certificato da utilizzare per generare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="730bb-141">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="730bb-142">Al termine dell'esecuzione dei comandi è possibile fare clic su Visualizza log o su Avanti per continuare.</span><span class="sxs-lookup"><span data-stu-id="730bb-142">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="730bb-143">Nella pagina File richiesta di certificato è possibile visualizzare il file di richiesta di firma del certificato (CSR) generato facendo clic su Visualizza oppure è possibile fare clic su Fine per uscire dalla Configurazione guidata certificati.</span><span class="sxs-lookup"><span data-stu-id="730bb-143">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="730bb-144">Copiare il file di richiesta e inviarlo all'Autorità di certificazione (CA) pubblica.</span><span class="sxs-lookup"><span data-stu-id="730bb-144">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="730bb-p108">Dopo aver ricevuto, importato e assegnato il certificato pubblico, è necessario arrestare e riavviare i servizi del server perimetrale. A tale scopo, digitare quanto segue nella console di gestione di Lync Server:</span><span class="sxs-lookup"><span data-stu-id="730bb-p108">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. <span data-ttu-id="730bb-147">Per configurare DNS per la Federazione XMPP, è necessario aggiungere il record SRV seguente al DNS\_esterno: XMPP-server. \_TCP. \<nome\> di dominio il record SRV verrà risolto nell'FQDN del server perimetrale di Access Edge, con un valore di porta pari a 5269.</span><span class="sxs-lookup"><span data-stu-id="730bb-147">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="730bb-148">È inoltre necessario configurare un record host 'A' (ad esempio, xmpp.contoso.com) che punta all'indirizzo IP del server Access Edge.</span><span class="sxs-lookup"><span data-stu-id="730bb-148">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="730bb-p110">Se esistono pool di server perimetrali in più siti, è consigliabile aggiungere più record SRV per la federazione XMPP. Aggiungere un record SRV per ogni pool di server perimetrali nell'organizzazione e assegnare una diversa priorità a ognuno di questi record SRV. Quando tutti i pool di server perimetrali sono in esecuzione, le richieste XMPP verranno tutte gestite dal pool di server perimetrali prioritario, ma se tale pool di server perimetrali diventa inattivo sarà necessario aggiungere un nuovo record SRV per ripristinare la funzionalità di federazione XMPP.</span><span class="sxs-lookup"><span data-stu-id="730bb-p110">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation. Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority. When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="730bb-152">Configurare nuovi criteri di accesso esterno per abilitare tutti gli utenti. A tale scopo, aprire Lync Server Management Shell nel Front End Server e digitare:</span><span class="sxs-lookup"><span data-stu-id="730bb-152">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="730bb-153">Abilitare l'accesso XMPP per gli utenti esterni digitando:</span><span class="sxs-lookup"><span data-stu-id="730bb-153">Enable XMPP Access for External Users by typing:</span></span>
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="730bb-154">Nel server perimetrale in cui è distribuito il proxy XMPP, aprire un prompt dei comandi o un'interfaccia della riga di comando di Windows PowerShell™ e digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="730bb-154">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="730bb-155">Il comando **netstat –ano** è un comando per le statistiche di rete, i parametri **–ano** richiedono che il comando netstat visualizzi tutte le connessioni e le porte di attesa, che l'indirizzo e le porte vengano visualizzati in forma numerica e che l'ID del processo proprietario venga associato a ogni connessione.</span><span class="sxs-lookup"><span data-stu-id="730bb-155">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="730bb-156">Il carattere **|** definisce una pipe al comando successivo, **findstr**o trova stringa.</span><span class="sxs-lookup"><span data-stu-id="730bb-156">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="730bb-157">Il numero 5269 e 23456 passato a findstr come parametro indica a findstr di eseguire la ricerca nell'output di netstat per le stringhe 5269 e 23456.</span><span class="sxs-lookup"><span data-stu-id="730bb-157">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="730bb-158">Se XMPP è configurato correttamente, il risultato dei comandi dovrebbe generare connessioni di attesa e stabilite, sia nelle interfacce esterne (porta 5269) sia in quelle interne (porta 23456) del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="730bb-158">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="730bb-159">Se i comandi non restituiscono porte attivate o in attesa per 5269 e 23456, controllare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="730bb-159">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="730bb-160">Risoluzione dei problemi relativi alla federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="730bb-160">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="730bb-161">Per stabilire se il proxy XMPP è in esecuzione, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="730bb-161">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="730bb-162">Accedere al server perimetrale che esegue il servizio proxy XMPP con un account membro del gruppo degli amministratori locali.</span><span class="sxs-lookup"><span data-stu-id="730bb-162">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="730bb-163">Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Strumenti di amministrazione** e quindi **Servizi**.</span><span class="sxs-lookup"><span data-stu-id="730bb-163">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="730bb-p112">In Servizi individuare il servizio Lync Server XMPP Translating Gateway Proxy. Questo servizio dovrebbe essere in stato **Avviato**. In caso contrario, fare clic sull'icona **Avvia** sulla barra degli strumenti. L'icona ha la forma di una freccia verde rivolta a destra.</span><span class="sxs-lookup"><span data-stu-id="730bb-p112">In Services, locate Lync Server XMPP Translating Gateway Proxy. The service should be in the **Started** state. If it is not started, click the **Start** icon in the toolbar. The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="730bb-168">Verificare che lo stato del servizio sia diventato **Avviato**.</span><span class="sxs-lookup"><span data-stu-id="730bb-168">Confirm that the service has changed to **Started**.</span></span> <span data-ttu-id="730bb-169">Se l'avvio è stato completato correttamente, chiudere **Servizi** e continuare.</span><span class="sxs-lookup"><span data-stu-id="730bb-169">If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="730bb-170">Se il servizio non è stato avviato, da Strumenti di amministrazione aprire Visualizzatore eventi e controllare gli errori e gli avvisi nella parte **Lync Server** in **Registri applicazioni e servizi**.</span><span class="sxs-lookup"><span data-stu-id="730bb-170">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="730bb-171">Quando il sevizio **Lync Server XMPP Translating Gateway** è in esecuzione, ricontrollare i comandi netstat utilizzati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="730bb-171">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="730bb-172">Se non si vedono sessioni consolidate o in attesa, controllare e verificare che la **Route di federazione XMPP** sia configurata correttamente in Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="730bb-172">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="730bb-173">Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="730bb-173">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="730bb-174">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="730bb-174">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="730bb-175">In Generatore di topologie selezionare il sito per la route di federazione XMPP e la revisione per confermare che l' **assegnazione della route di Federazione del sito** per la **Federazione XMPP** indichi il server perimetrale o il pool di Edge come assegnazione della route di federazione XMPP selezionata.</span><span class="sxs-lookup"><span data-stu-id="730bb-175">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="730bb-176">Se l'assegnazione della route non è corretta o non è impostata, fare clic con il pulsante destro del mouse sul sito e scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="730bb-176">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="730bb-177">Selezionare la casella di controllo Federazione XMPP e quindi selezionare il server perimetrale o il pool di Edge corretti.</span><span class="sxs-lookup"><span data-stu-id="730bb-177">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="730bb-178">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="730bb-178">Publish the topology.</span></span> <span data-ttu-id="730bb-179">Per ulteriori informazioni, vedere [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="730bb-179">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="730bb-180">Sebbene non sia richiesto e in genere non necessario, è possibile che sia necessario riavviare i server perimetrali</span><span class="sxs-lookup"><span data-stu-id="730bb-180">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="730bb-181">Se si utilizza il processo netstat utilizzato in precedenza, verificare che il server perimetrale sia in attesa o che abbia stabilito sessioni sulla porta 5269 e sulla porta 23456.</span><span class="sxs-lookup"><span data-stu-id="730bb-181">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="730bb-182">Se ancora non vengono visualizzate le sessioni previste, controllare nel Visualizzatore eventi per individuare le possibili cause del problema di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="730bb-182">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="730bb-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="730bb-183">See Also</span></span>


[<span data-ttu-id="730bb-184">Esempio di configurazione XMPP in Lync Server 2013 – Federazione XMPP con Google Talk</span><span class="sxs-lookup"><span data-stu-id="730bb-184">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="730bb-185">Gestire i partner federati XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="730bb-185">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

