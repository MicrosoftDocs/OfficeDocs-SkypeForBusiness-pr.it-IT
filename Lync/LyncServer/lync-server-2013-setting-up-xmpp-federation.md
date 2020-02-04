---
title: 'Lync Server 2013: Configurazione della federazione di XMPP'
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
ms.openlocfilehash: fd61aded33d37e4a1f5f58e9050f3cd62794f9b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="0e0da-102">Configurazione della federazione di XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e0da-102">Setting up XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e0da-103">_**Argomento Ultima modifica:** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="0e0da-103">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="0e0da-104">Per distribuire il proxy XMPP nell'Edge Server, è necessario configurare l'Edge Server per la Federazione XMPP.</span><span class="sxs-lookup"><span data-stu-id="0e0da-104">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation.</span></span> <span data-ttu-id="0e0da-105">A questo scopo, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="0e0da-105">To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="0e0da-106">Configurazione della Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="0e0da-106">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="0e0da-107">Accedere al computer in cui è installata la distribuzione guidata di Lync Server come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="0e0da-107">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="0e0da-108">Nel server front-end aprire la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0e0da-108">On the Front End server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="0e0da-109">Fare clic su Installa o aggiorna Lync Server System, quindi fare clic su Imposta o Rimuovi componenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0e0da-109">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="0e0da-110">Fare di nuovo clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="0e0da-110">Click Run Again.</span></span>

3.  <span data-ttu-id="0e0da-111">In configurazione componenti di Lync Server fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="0e0da-111">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="0e0da-112">La schermata di riepilogo mostrerà le azioni Man mano che vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="0e0da-112">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="0e0da-113">Dopo aver completato la distribuzione, fare clic su Visualizza log per visualizzare i file di log disponibili.</span><span class="sxs-lookup"><span data-stu-id="0e0da-113">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="0e0da-114">Fare clic su fine per completare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0e0da-114">Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="0e0da-115">Nell'Edge Server aprire la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0e0da-115">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="0e0da-116">Fare clic su Installa o aggiorna Lync Server System, quindi fare clic su Imposta o Rimuovi componenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0e0da-116">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="0e0da-117">Fare di nuovo clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="0e0da-117">Click Run Again.</span></span>

5.  <span data-ttu-id="0e0da-118">In configurazione componenti di Lync Server fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="0e0da-118">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="0e0da-119">La schermata di riepilogo mostrerà le azioni Man mano che vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="0e0da-119">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="0e0da-120">Dopo aver completato la distribuzione, fare clic su Visualizza log per visualizzare i file di log disponibili.</span><span class="sxs-lookup"><span data-stu-id="0e0da-120">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="0e0da-121">Fare clic su fine per completare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0e0da-121">Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="0e0da-122">Nel server perimetro, nella distribuzione guidata, accanto a passaggio 3: richiedere, installare o assegnare certificati, fare di nuovo clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="0e0da-122">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="0e0da-123">Se si distribuisce il server perimetrale per la prima volta, verrà visualizzato di nuovo Esegui anziché Esegui.</span><span class="sxs-lookup"><span data-stu-id="0e0da-123">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="0e0da-124">Nella pagina attività certificato disponibili fare clic su Crea una nuova richiesta di certificato.</span><span class="sxs-lookup"><span data-stu-id="0e0da-124">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="0e0da-125">Nella pagina richiesta certificato fare clic su certificato bordo esterno.</span><span class="sxs-lookup"><span data-stu-id="0e0da-125">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="0e0da-126">Nella pagina richiesta posticipata o immediata selezionare la casella di controllo prepara la richiesta ora, ma inviarla in seguito.</span><span class="sxs-lookup"><span data-stu-id="0e0da-126">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="0e0da-127">Nella pagina file di richiesta certificato digitare il percorso completo e il nome file del file in cui deve essere salvata la richiesta, ad esempio c:\\CERT\_exernal\_Edge. cer.</span><span class="sxs-lookup"><span data-stu-id="0e0da-127">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="0e0da-128">Nella pagina specifica modello di certificato alternativo, per usare un modello diverso da quello predefinito del modello webserver, selezionare la casella di controllo Usa il modello di certificato alternativo per l'autorità di certificazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="0e0da-128">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="0e0da-129">Nella pagina impostazioni di sicurezza e nome eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e0da-129">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="0e0da-130">In nome descrittivo digitare un nome visualizzato per il certificato</span><span class="sxs-lookup"><span data-stu-id="0e0da-130">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="0e0da-131">In bit length specificare la lunghezza in bit (in genere, il valore predefinito di 2048)</span><span class="sxs-lookup"><span data-stu-id="0e0da-131">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="0e0da-132">Verificare che la casella di controllo contrassegna la chiave privata del certificato come esportabile sia selezionata</span><span class="sxs-lookup"><span data-stu-id="0e0da-132">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="0e0da-133">Nella pagina informazioni organizzazione digitare il nome dell'organizzazione e dell'unità organizzativa, ad esempio divisione o reparto.</span><span class="sxs-lookup"><span data-stu-id="0e0da-133">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="0e0da-134">Nella pagina informazioni geografiche specificare le informazioni sulla posizione</span><span class="sxs-lookup"><span data-stu-id="0e0da-134">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="0e0da-135">Nella pagina nome oggetto/nomi oggetto alternativo vengono visualizzate le informazioni che verranno inserite automaticamente dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="0e0da-135">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="0e0da-136">Se sono necessari altri nomi alternativi per l'oggetto, è necessario specificarli nei due passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0e0da-136">If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="0e0da-137">Nell'impostazione del dominio SIP nella pagina nome alternativo oggetto (SANs) selezionare la casella di controllo Domain per aggiungere un SIP. \<SipDomain\> voce nell'elenco nomi alternativi oggetto.</span><span class="sxs-lookup"><span data-stu-id="0e0da-137">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="0e0da-138">Nella pagina Configura altri nomi alternativi oggetto specificare eventuali altri nomi alternativi per gli argomenti necessari</span><span class="sxs-lookup"><span data-stu-id="0e0da-138">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="0e0da-139">Se il proxy XMPP è installato, per impostazione predefinita il nome di dominio, ad esempio contoso.com, viene popolato nelle voci SAN.</span><span class="sxs-lookup"><span data-stu-id="0e0da-139">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="0e0da-140">Se sono necessarie altre voci, aggiungerle in questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="0e0da-140">If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="0e0da-141">Nella pagina Riepilogo richieste verificare le informazioni sul certificato da usare per generare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="0e0da-141">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="0e0da-142">Dopo che i comandi hanno terminato l'uso, è possibile visualizzare il log oppure fare clic su Avanti per continuare.</span><span class="sxs-lookup"><span data-stu-id="0e0da-142">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="0e0da-143">Nella pagina file di richiesta di certificato è possibile visualizzare il file della richiesta di firma del certificato (CSR) generato facendo clic su Visualizza o Esci dalla creazione guidata certificato facendo clic su fine.</span><span class="sxs-lookup"><span data-stu-id="0e0da-143">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="0e0da-144">Copiare il file di richiesta e inviarlo all'autorità di certificazione pubblica.</span><span class="sxs-lookup"><span data-stu-id="0e0da-144">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="0e0da-145">Dopo la ricezione, l'importazione e l'assegnazione del certificato pubblico, è necessario arrestare e riavviare i servizi Edge Server.</span><span class="sxs-lookup"><span data-stu-id="0e0da-145">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="0e0da-146">A tale scopo, digitare la console di gestione di Lync Server:</span><span class="sxs-lookup"><span data-stu-id="0e0da-146">You do this by typing in the Lync Server Management console:</span></span>
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. <span data-ttu-id="0e0da-147">Per configurare il DNS per la Federazione XMPP, è possibile aggiungere il record SRV seguente al\_DNS esterno: XMPP-server. \_TCP. \<nome\> di dominio il record SRV verrà risolto nell'FQDN di Access Edge del server Edge, con un valore di porta 5269.</span><span class="sxs-lookup"><span data-stu-id="0e0da-147">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="0e0da-148">Inoltre, configuri un record host "A" (ad esempio xmpp.contoso.com) che punta all'indirizzo IP di Access Edge Server.</span><span class="sxs-lookup"><span data-stu-id="0e0da-148">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0e0da-149">Se si hanno pool di bordi in più siti, è consigliabile aggiungere più record SRV per la Federazione XMPP.</span><span class="sxs-lookup"><span data-stu-id="0e0da-149">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation.</span></span> <span data-ttu-id="0e0da-150">Aggiungere un record SRV per ogni pool di Edge nell'organizzazione e assegnare a ognuno di questi record SRV una priorità diversa.</span><span class="sxs-lookup"><span data-stu-id="0e0da-150">Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority.</span></span> <span data-ttu-id="0e0da-151">Quando tutti i pool di bordi sono in esecuzione, le richieste XMPP verranno gestite dal pool di Edge con la prima priorità, ma se tale pool di Edge scende, non dovrai aggiungere un nuovo record SRV per recuperare le funzionalità federative XMPP.</span><span class="sxs-lookup"><span data-stu-id="0e0da-151">When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="0e0da-152">Configurare un nuovo criterio di accesso esterno per abilitare tutti gli utenti aprendo Lync Server Management Shell sul front-end e digitando:</span><span class="sxs-lookup"><span data-stu-id="0e0da-152">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="0e0da-153">Abilitare l'accesso XMPP per gli utenti esterni digitando:</span><span class="sxs-lookup"><span data-stu-id="0e0da-153">Enable XMPP Access for External Users by typing:</span></span>
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="0e0da-154">Nell'Edge Server in cui è distribuito il proxy XMPP aprire un prompt dei comandi o un'interfaccia della riga di comando™ di Windows PowerShell e digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0e0da-154">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="0e0da-155">Il comando **netstat-ano** è un comando di statistiche di rete, i parametri **-richiesta ano** che netstat Visualizza tutte le connessioni e le porte in ascolto, l'indirizzo e le porte vengono visualizzati in forma numerica e l'ID processo proprietario è associato a ogni connessione.</span><span class="sxs-lookup"><span data-stu-id="0e0da-155">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="0e0da-156">Il carattere **|** definisce una pipe per il comando successivo, **findstr**o trova stringa.</span><span class="sxs-lookup"><span data-stu-id="0e0da-156">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="0e0da-157">Il numero 5269 e 23456 passato a findstr come parametro indica a findstr di cercare l'output di netstat per le stringhe 5269 e 23456.</span><span class="sxs-lookup"><span data-stu-id="0e0da-157">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="0e0da-158">Se XMPP è configurato correttamente, il risultato dei comandi deve comportare connessioni in ascolto e stabilite, sia nelle interfacce esterne (porta 5269) che in quelle interne (porta 23456) del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="0e0da-158">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="0e0da-159">Se i comandi non restituiscono porte stabilite o in ascolto in 5269 e 23456, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e0da-159">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="0e0da-160">Risoluzione dei problemi relativi alla Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="0e0da-160">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="0e0da-161">Per determinare se il proxy XMPP è in uso, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e0da-161">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="0e0da-162">Accedere all'Edge Server che sta usando il servizio proxy XMPP come membro del gruppo dell'amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="0e0da-162">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="0e0da-163">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**e quindi **Servizi**</span><span class="sxs-lookup"><span data-stu-id="0e0da-163">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="0e0da-164">In servizi individuare il proxy del gateway di traduzione XMPP di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0e0da-164">In Services, locate Lync Server XMPP Translating Gateway Proxy.</span></span> <span data-ttu-id="0e0da-165">Il servizio deve essere nello stato **Started** .</span><span class="sxs-lookup"><span data-stu-id="0e0da-165">The service should be in the **Started** state.</span></span> <span data-ttu-id="0e0da-166">Se non è stata avviata, fare clic sull'icona **Start** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="0e0da-166">If it is not started, click the **Start** icon in the toolbar.</span></span> <span data-ttu-id="0e0da-167">L'icona viene visualizzata come freccia verde e rivolta verso destra.</span><span class="sxs-lookup"><span data-stu-id="0e0da-167">The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="0e0da-168">Verificare che il servizio sia stato modificato in **iniziato**.</span><span class="sxs-lookup"><span data-stu-id="0e0da-168">Confirm that the service has changed to **Started**.</span></span> <span data-ttu-id="0e0da-169">Se è stata avviata correttamente, chiudere i **Servizi** e continuare.</span><span class="sxs-lookup"><span data-stu-id="0e0da-169">If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="0e0da-170">Se il servizio non è stato avviato correttamente, da strumenti di amministrazione aprire il Visualizzatore eventi e fare riferimento agli errori e agli avvisi presenti nella parte **Lync Server** in **registri applicazioni e servizi**.</span><span class="sxs-lookup"><span data-stu-id="0e0da-170">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="0e0da-171">Una volta che il servizio **gateway di traduzione XMPP di Lync Server** è in uso, ripetere il controllo dei comandi netstat usati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0e0da-171">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="0e0da-172">Se non si vedono sessioni consolidate o in ascolto, verificare e verificare che la **Route federativo XMPP** sia configurata correttamente in Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="0e0da-172">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="0e0da-173">Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="0e0da-173">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="0e0da-174">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0e0da-174">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="0e0da-175">In Generatore di topologie selezionare il sito per la route della Federazione XMPP e la revisione per verificare che l' **assegnazione della route Federation del sito** per la **Federazione XMPP** indichi il server perimetrale o il pool di Edge come assegnazione della route Federation XMPP selezionata.</span><span class="sxs-lookup"><span data-stu-id="0e0da-175">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="0e0da-176">Se l'assegnazione della route non è corretta o non è impostata, fare clic con il pulsante destro del mouse sul sito, scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0e0da-176">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="0e0da-177">Selezionare la casella di controllo Federazione XMPP e quindi selezionare il server Edge o il pool di Edge corretto.</span><span class="sxs-lookup"><span data-stu-id="0e0da-177">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="0e0da-178">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="0e0da-178">Publish the topology.</span></span> <span data-ttu-id="0e0da-179">Per informazioni dettagliate, vedere [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="0e0da-179">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="0e0da-180">Sebbene non sia richiesto e in genere non necessario, è possibile che sia necessario riavviare gli Edge Server</span><span class="sxs-lookup"><span data-stu-id="0e0da-180">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="0e0da-181">Usando il processo netstat usato in precedenza, verificare che il server perimetrale sia ora in ascolto o abbia stabilito sessioni sulla porta 5269 e la porta 23456.</span><span class="sxs-lookup"><span data-stu-id="0e0da-181">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="0e0da-182">Se non si vedono ancora le sessioni previste, controllare il Visualizzatore eventi per eventuali cause di contributo per il problema di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="0e0da-182">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0e0da-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e0da-183">See Also</span></span>


[<span data-ttu-id="0e0da-184">Esempio di configurazione XMPP in Lync Server 2013 - federazione di XMPP con Google Talk</span><span class="sxs-lookup"><span data-stu-id="0e0da-184">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="0e0da-185">Gestire i partner federati XMPP per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e0da-185">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

