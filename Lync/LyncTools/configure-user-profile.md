---
title: Configurare il profilo utente
description: Configurare il profilo utente.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 682297da43797dd2d774094e85e8688ef3c64d98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573092"
---
# <a name="configure-user-profile"></a><span data-ttu-id="30a1a-103">Configurare il profilo utente</span><span class="sxs-lookup"><span data-stu-id="30a1a-103">Configure User Profile</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30a1a-104">_**Ultimo argomento modificato:** 2018-10-11_</span><span class="sxs-lookup"><span data-stu-id="30a1a-104">_**Topic Last Modified:** 2018-10-11_</span></span>

<span data-ttu-id="30a1a-105">Gli strumenti inclusi nel pacchetto dello strumento di stress e prestazioni di Lync Server 2013 consentono di creare e configurare gli account utente di test che è possibile utilizzare per eseguire simulazioni di caricamento.</span><span class="sxs-lookup"><span data-stu-id="30a1a-105">The tools included in the Lync Server 2013 Stress and Performance Tool package enable you to create and configure test user accounts that you can use to run load simulations.</span></span> <span data-ttu-id="30a1a-106">Utilizzare lo strumento di creazione utente di Lync Server 2013 per creare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="30a1a-106">Use the Lync Server 2013 User Creation Tool to create the users.</span></span> <span data-ttu-id="30a1a-107">Per informazioni dettagliate, vedere [creazione di utenti e contatti](create-users-and-contacts.md). Dopo aver creato gli utenti, configurare i profili utente utilizzando lo strumento di configurazione del caricamento di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30a1a-107">(For details, see [Create Users and Contacts](create-users-and-contacts.md).) After users are created, configure the user profiles by using the Lync Server 2013 Load Configuration Tool.</span></span>

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a><span data-ttu-id="30a1a-108">Esecuzione dello strumento di configurazione del carico di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30a1a-108">Running the Lync Server 2013 Load Configuration Tool</span></span>

<span data-ttu-id="30a1a-109">Per configurare i profili utente, eseguire lo strumento di configurazione del carico di Lync Server 2013 (UserProfileGenerator.exe) e compilare tutte le schede.</span><span class="sxs-lookup"><span data-stu-id="30a1a-109">To configure user profiles, run the Lync Server 2013 Load Configuration Tool (UserProfileGenerator.exe) and fill out each of the tabs.</span></span> <span data-ttu-id="30a1a-110">UserProfileGenerator.exe genera una directory per ogni computer client che è necessario eseguire la simulazione.</span><span class="sxs-lookup"><span data-stu-id="30a1a-110">UserProfileGenerator.exe generates a directory for each of the client computers that you need to run the simulation.</span></span> <span data-ttu-id="30a1a-111">Ogni directory client include anche uno script per avviare tutte le istanze dello strumento di stress e prestazioni di Lync Server 2013 (LyncPerfTool.exe).</span><span class="sxs-lookup"><span data-stu-id="30a1a-111">Each client directory also comes with a script to start all the instances of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="30a1a-112">I valori specifici dell'utente specificati in UserProfileGenerator devono corrispondere ai valori specificati nello strumento di creazione degli utenti di Lync Server 2013 (UserProvisioningTool) per il pool.</span><span class="sxs-lookup"><span data-stu-id="30a1a-112">The user-specific values specified in UserProfileGenerator must match the values specified in the Lync Server 2013 User Creation Tool (UserProvisioningTool) for the pool.</span></span>



</div>

<span data-ttu-id="30a1a-113">Compilare i campi di ogni scheda dello strumento di configurazione del carico di Lync Server 2013, come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="30a1a-113">Fill in the fields on each tab of the Lync Server 2013 Load Configuration Tool, as described in the following sections.</span></span>

<div>

## <a name="common-configuration"></a><span data-ttu-id="30a1a-114">Configurazione comune</span><span class="sxs-lookup"><span data-stu-id="30a1a-114">Common Configuration</span></span>

<span data-ttu-id="30a1a-115">La scheda **configurazione comune** dello strumento di configurazione del carico di Lync Server 2013 è illustrata nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="30a1a-115">The **Common Configuration** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span> <span data-ttu-id="30a1a-116">Compilare i campi della scheda **configurazione comune** , come descritto nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="30a1a-116">Fill in the fields of the **Common Configuration** tab, as described in the following steps.</span></span>

<span data-ttu-id="30a1a-117">![Scheda di configurazione comune.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Scheda di configurazione comune.")</span><span class="sxs-lookup"><span data-stu-id="30a1a-117">![Common Configuration tab.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Common Configuration tab.")</span></span>

1.  <span data-ttu-id="30a1a-118">In **numero di macchine disponibili**Digitare o fare clic sul numero di computer che si desidera utilizzare per eseguire LyncPerfTool.exe.</span><span class="sxs-lookup"><span data-stu-id="30a1a-118">In **Number of Available Machines**, type or click the number of computers that you want to use to run LyncPerfTool.exe.</span></span> <span data-ttu-id="30a1a-119">È consigliabile disporre di un solo computer per ogni 4.500 utenti da simulare.</span><span class="sxs-lookup"><span data-stu-id="30a1a-119">We recommend that you have one computer for every 4,500 users that you will be simulating.</span></span> <span data-ttu-id="30a1a-120">Questo numero può variare se si riduce il livello di carico o se si utilizza solo un sottoinsieme delle funzionalità disponibili.</span><span class="sxs-lookup"><span data-stu-id="30a1a-120">That number may vary if you reduce the load level or if you use only a subset of the available features.</span></span> <span data-ttu-id="30a1a-121">(I livelli di carico sono impostati nella scheda **scenari generali** ).</span><span class="sxs-lookup"><span data-stu-id="30a1a-121">(Load levels are set on the **General Scenarios** tab.)</span></span>

2.  <span data-ttu-id="30a1a-122">In **prefisso per i nomi utente**, digitare il prefisso per il nome utente degli utenti.</span><span class="sxs-lookup"><span data-stu-id="30a1a-122">In **Prefix for User Names**, type the prefix for the user name of the users.</span></span> <span data-ttu-id="30a1a-123">Per eseguire l'accesso, l'URI (Uniform Resource Identifier) sarà: \[ indice di avvio utente di UserPrefix... (Numero di utenti-1) \] @User dominio.</span><span class="sxs-lookup"><span data-stu-id="30a1a-123">To log in, the Uniform Resource Identifier (URI) will be: UserPrefix\[User Start Index…(Number Of Users-1)\]@User Domain.</span></span>

3.  <span data-ttu-id="30a1a-124">In **password per tutti gli utenti**, immettere la password utilizzata per la creazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="30a1a-124">In **Password for All Users**, enter the password that was used for creating the users.</span></span> <span data-ttu-id="30a1a-125">Se si lascia vuoto questo campo, il nome utente verrà utilizzato come password.</span><span class="sxs-lookup"><span data-stu-id="30a1a-125">If you leave this field empty, the username will be used as the password.</span></span>

4.  <span data-ttu-id="30a1a-126">In **Indice inizio utente**fare clic su o digitare l'indice del primo utente da configurare.</span><span class="sxs-lookup"><span data-stu-id="30a1a-126">In **User Start Index**, click or type the index of the first user to be configured.</span></span> <span data-ttu-id="30a1a-127">È possibile configurare diversi intervalli per diversi tipi o livelli di carico, ma è necessario eseguire UserProfileGenerator.exe una volta per l'intervallo che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="30a1a-127">You can configure different ranges for different types or levels of load, but you must run UserProfileGenerator.exe once per the range that you want to configure.</span></span>

5.  <span data-ttu-id="30a1a-128">In **numero di utenti**, fare clic su o digitare il numero totale di utenti che si intende configurare.</span><span class="sxs-lookup"><span data-stu-id="30a1a-128">In **Number of Users**, click or type the total number of users you are going to configure.</span></span>

6.  <span data-ttu-id="30a1a-129">In **dominio utente**Digitare il dominio utilizzato per l'URI SIP.</span><span class="sxs-lookup"><span data-stu-id="30a1a-129">In **User Domain**, type the domain used for the SIP URI.</span></span> <span data-ttu-id="30a1a-130">Viene utilizzato per creare l'URI SIP di ogni utente per accedere al server Lync Server 2013 front end server o allo Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="30a1a-130">This is used to construct the SIP URI of each user to log on to the Lync Server 2013 Front End Server or Standard Edition server.</span></span> <span data-ttu-id="30a1a-131">Può essere diverso dal dominio account.</span><span class="sxs-lookup"><span data-stu-id="30a1a-131">It can be different from the account domain.</span></span>

7.  <span data-ttu-id="30a1a-132">In **dominio account**Digitare l'accesso al dominio di servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="30a1a-132">In **Account Domain**, type the Active Directory Domain Services domain logon.</span></span>

8.  <span data-ttu-id="30a1a-133">Immettere il numero massimo di endpoint simultanei in **accedi al secondo (per istanza)** per il quale si desidera che lo strumento esegua l'accesso in tutti gli endpoint/utenti.</span><span class="sxs-lookup"><span data-stu-id="30a1a-133">Enter the maximum number of concurrent endpoints in **Sign In Per Second (per instance)** for which you want the tool to log in all the endpoints/users.</span></span> <span data-ttu-id="30a1a-134">La frequenza consigliata è \< = 2 per secondo/standard SKU Fe.</span><span class="sxs-lookup"><span data-stu-id="30a1a-134">The recommended rate is \<=2 per second/standard SKU FE.</span></span>

9.  <span data-ttu-id="30a1a-135">In **FQDN del proxy di accesso o del pool**Digitare il nome di dominio completo (FQDN) del server a cui si desidera connettere i client.</span><span class="sxs-lookup"><span data-stu-id="30a1a-135">In **Access Proxy or Pool FQDN**, type the fully qualified domain name (FQDN) of the server that you want the clients to connect to.</span></span> <span data-ttu-id="30a1a-136">Se gli utenti accedono esternamente, specificare il proxy di accesso.</span><span class="sxs-lookup"><span data-stu-id="30a1a-136">If the users are logging on externally, specify the access proxy.</span></span> <span data-ttu-id="30a1a-137">Se gli utenti sono interni, specificare il nome di dominio completo del pool o del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="30a1a-137">If the users are internal, specify the FQDN of their pool or Standard Edition server.</span></span>

10. <span data-ttu-id="30a1a-138">In **porta**fare clic su o digitare la porta che si desidera venga utilizzata dagli utenti per SIP (il valore predefinito è 5061).</span><span class="sxs-lookup"><span data-stu-id="30a1a-138">In **Port**, click or type the port that you want users to use for SIP (the default is 5061).</span></span>

<span data-ttu-id="30a1a-139">Per le impostazioni del server di rete esterno, specificare il **proxy di accesso o il nome FQDN del pool** e la **porta**.</span><span class="sxs-lookup"><span data-stu-id="30a1a-139">For External Network Server Settings, specify the **Access Proxy or Pool FQDN** and the **Port**.</span></span> <span data-ttu-id="30a1a-140">Queste impostazioni vengono utilizzate solo per la simulazione del caricamento degli endpoint esterni.</span><span class="sxs-lookup"><span data-stu-id="30a1a-140">These settings are used only for External endpoints load simulation.</span></span>

</div>

<div>

## <a name="general-scenarios"></a><span data-ttu-id="30a1a-141">Scenari generali</span><span class="sxs-lookup"><span data-stu-id="30a1a-141">General Scenarios</span></span>

<span data-ttu-id="30a1a-142">La scheda **scenari generali** dello strumento di configurazione del carico di Lync Server 2013 è illustrata nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="30a1a-142">The **General Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="30a1a-143">Configurare i livelli di carico e i parametri per ognuno degli scenari generali che si desidera eseguire oppure lasciare disabilitati.</span><span class="sxs-lookup"><span data-stu-id="30a1a-143">Configure the load levels and parameters for each of the general scenarios that you want to run, or leave disabled.</span></span>

<span data-ttu-id="30a1a-144">![Scheda scenari generali.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "Scheda scenari generali.")</span><span class="sxs-lookup"><span data-stu-id="30a1a-144">![General Scenarios tab.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "General Scenarios tab.")</span></span>

1.  <span data-ttu-id="30a1a-145">In **messaggistica istantanea**, che include peer-to-peer e conferenze, specificare il valore appropriato per il livello di carico.</span><span class="sxs-lookup"><span data-stu-id="30a1a-145">In **Instant Messaging**, which includes peer-to-peer and conferencing, specify the appropriate value for the Load Level.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30a1a-146">I valori dei livelli di carico per tutti i campi (eccetto Location Information Services) sono <STRONG>disattivati</STRONG>, <STRONG>basso</STRONG>, <STRONG>medio</STRONG>, <STRONG>alto</STRONG>e <STRONG>personalizzato</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="30a1a-146">Load level values for all fields (except Location Information Services) are <STRONG>Disabled</STRONG>, <STRONG>Low</STRONG>, <STRONG>Medium</STRONG>, <STRONG>High</STRONG>, and <STRONG>Custom</STRONG>.</span></span> <span data-ttu-id="30a1a-147">Se è selezionata l'opzione basso, medio, alto o personalizzato, verranno generate configurazioni per ogni modalità e client.</span><span class="sxs-lookup"><span data-stu-id="30a1a-147">When Low, Medium, High, or Custom is selected, configurations will be generated for each modality and client.</span></span> <span data-ttu-id="30a1a-148">High provocherà la generazione del carico massimo supportato per il server, il valore medio corrisponde al 60% del carico e basso corrisponde al 30% del carico.</span><span class="sxs-lookup"><span data-stu-id="30a1a-148">High will result in the maximum supported load to be generated for the server, Medium corresponds to 60 percent of the load, and Low corresponds to 30 percent of the load.</span></span>

    
    </div>

2.  <span data-ttu-id="30a1a-149">In audioconferenza, che è solo audioconferenza, specificare il valore appropriato per il **livello di carico**.</span><span class="sxs-lookup"><span data-stu-id="30a1a-149">In **Audio Conferencing**, which is audio conferencing only, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="30a1a-150">Le chiamate peer-to-peer sono descritte nella sezione Voice Scenarios più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="30a1a-150">Peer-to-peer calls are covered in the Voice Scenarios section later in this topic.</span></span> <span data-ttu-id="30a1a-151">Per abilitare MultiView, aprire la scheda **Avanzate** per tale modalità.</span><span class="sxs-lookup"><span data-stu-id="30a1a-151">To enable MultiView, open the **Advanced** tab for that modality.</span></span>

3.  <span data-ttu-id="30a1a-152">In **condivisione applicazioni**specificare il valore appropriato per il livello di carico.</span><span class="sxs-lookup"><span data-stu-id="30a1a-152">In **Application Sharing**, specify the appropriate value for Load Level.</span></span>

4.  <span data-ttu-id="30a1a-153">In **collaborazione dati**, che include servizi di conferenza dati, specificare il valore appropriato per il livello di carico.</span><span class="sxs-lookup"><span data-stu-id="30a1a-153">In **Data Collaboration**, which includes data conferencing, specify the appropriate value for Load Level.</span></span>

5.  <span data-ttu-id="30a1a-154">Nell' **espansione della lista di distribuzione**, specificare il valore appropriato per il livello di carico.</span><span class="sxs-lookup"><span data-stu-id="30a1a-154">In **Distribution List Expansion**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="30a1a-155">È inoltre necessario fare clic sul pulsante **Avanzate** e quindi compilare i campi con gli stessi valori configurati nella scheda **elenco di distribuzione** dello strumento di creazione utente di Lync Server (UserProvisioningTool.exe).</span><span class="sxs-lookup"><span data-stu-id="30a1a-155">You must also click the **Advanced** button, and then fill in the fields with the same values that you configured on the **Distribution List** tab of the Lync Server User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="30a1a-156">Per informazioni dettagliate su questi campi, vedere [creare utenti e contatti](create-users-and-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="30a1a-156">For details about these fields, see [Create Users and Contacts](create-users-and-contacts.md)</span></span>

6.  <span data-ttu-id="30a1a-157">In **query Web**Rubrica, che è il servizio di ricerca rubrica (non il download dei file della rubrica), specificare il valore appropriato per il livello di carico.</span><span class="sxs-lookup"><span data-stu-id="30a1a-157">In **Address Book Web Query**, which is the address book lookup service (not the address book file download), specify the appropriate value for Load Level.</span></span> <span data-ttu-id="30a1a-158">Per abilitare i download della Rubrica, fare clic sul pulsante **Avanzate** corrispondente e quindi impostare **EnableABSDownload** su true.</span><span class="sxs-lookup"><span data-stu-id="30a1a-158">To enable address book downloads, click the corresponding **Advanced** button, and then set **EnableABSDownload** to true.</span></span>

7.  <span data-ttu-id="30a1a-159">In **Response Group Service**specificare il valore appropriato per il livello di carico.</span><span class="sxs-lookup"><span data-stu-id="30a1a-159">In **Response Group Service**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="30a1a-160">È inoltre necessario fare clic sul pulsante **Avanzate** corrispondente e quindi specificare gli URI dei Response Group già creati durante il provisioning degli agenti del servizio Response Group.</span><span class="sxs-lookup"><span data-stu-id="30a1a-160">You must also click the corresponding **Advanced** button, and then specify the URIs of the response groups you have already created when provisioning Response Group Service agents.</span></span> <span data-ttu-id="30a1a-161">È necessario specificare almeno un Response Group.</span><span class="sxs-lookup"><span data-stu-id="30a1a-161">You must specify at least one response group.</span></span> <span data-ttu-id="30a1a-162">Utilizzare il punto e virgola per separare più gruppi di risposta.</span><span class="sxs-lookup"><span data-stu-id="30a1a-162">Use semicolons to separate multiple response groups.</span></span> <span data-ttu-id="30a1a-163">Aggiornare RGSUriSuffixStartIndex e RGSUriSuffixEndIndex ai valori effettivi.</span><span class="sxs-lookup"><span data-stu-id="30a1a-163">Update RGSUriSuffixStartIndex and RGSUriSuffixEndIndex to the actual values.</span></span>

8.  <span data-ttu-id="30a1a-164">In **Location Information Services**selezionare il valore appropriato per il livello di carico.</span><span class="sxs-lookup"><span data-stu-id="30a1a-164">In **Location Information Services**, select the appropriate value for Load Level.</span></span> <span data-ttu-id="30a1a-165">Il livello di carico per i servizi di informazioni percorso deve essere **abilitato** o **disabilitato**.</span><span class="sxs-lookup"><span data-stu-id="30a1a-165">The load level for Location Information Services must be **Enabled** or **Disabled**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="30a1a-166">A ognuno degli scenari è associato un pulsante <STRONG>avanzato</STRONG> e un set di caselle di controllo che consentono varianti degli scenari.</span><span class="sxs-lookup"><span data-stu-id="30a1a-166">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it, and a set of check boxes that enable variations of the scenarios.</span></span> <span data-ttu-id="30a1a-167">Strumenti ad <STRONG>hoc</STRONG> per generare una simulazione delle conferenze che verranno create per tutta l'ora.</span><span class="sxs-lookup"><span data-stu-id="30a1a-167"><STRONG>Ad-hoc</STRONG> means to generate simulation of conferences that will be created throughout the hour.</span></span> <span data-ttu-id="30a1a-168"><STRONG>Grande conf</STRONG> significa che verrà simulato uno scenario di conferenza di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="30a1a-168"><STRONG>Large Conf</STRONG> means that Large Conference Scenario will be simulated.</span></span> <span data-ttu-id="30a1a-169">Mezzi <STRONG>esterni</STRONG> per simulare anche gli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="30a1a-169"><STRONG>External</STRONG> means to also simulate external users.</span></span><BR><span data-ttu-id="30a1a-170">Questi pulsanti e le caselle di controllo consentono l'accesso ai valori specifici di ogni scenario che modificherà il comportamento dello strumento di verifica dello stress e delle prestazioni di Lync Server 2013 (LyncPerfTool) e renderà possibile la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="30a1a-170">These buttons and check boxes allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and make customization possible.</span></span> <span data-ttu-id="30a1a-171">Per ogni scenario nella scheda <STRONG>scenari generali</STRONG> (ad eccezione di Location Information Services), se il valore del livello di carico è <STRONG>Custom</STRONG>, la frequenza di conversazione viene calcolata utilizzando il campo corrispondente nella finestra di dialogo <STRONG>Avanzate</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="30a1a-171">For each scenario on the <STRONG>General Scenarios</STRONG> tab (except for Location Information Services), if the value of Load Level is <STRONG>Custom</STRONG>, then the conversation rate will be calculated using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="30a1a-172">Il nome del campo è diverso, a seconda dello scenario, ma la descrizione del campo diventerà "Nota: questo numero verrà utilizzato solo se è selezionata l'opzione personalizzato dal menu a discesa".</span><span class="sxs-lookup"><span data-stu-id="30a1a-172">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span> <span data-ttu-id="30a1a-173">In generale, i valori <STRONG>High</STRONG>, <STRONG>medium</STRONG>e <STRONG>low</STRONG> modificheranno i tassi di conversazione per ogni modalità in linea con il modello utente che rappresenta un bilanciamento di tutti gli scenari.</span><span class="sxs-lookup"><span data-stu-id="30a1a-173">In general, the values <STRONG>High</STRONG>, <STRONG>Medium</STRONG>, and <STRONG>Low</STRONG> will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="30a1a-174">Se è necessario modificare il livello di carico per modalità a causa di una differenza nell'utilizzo previsto, è consigliabile utilizzare un tasso di conversazione <STRONG>personalizzato</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="30a1a-174">If there is a need to change the load level per modality due to a difference in expected usage, we recommend using a <STRONG>Custom</STRONG> conversation rate.</span></span><BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a><span data-ttu-id="30a1a-175">Scenari vocali</span><span class="sxs-lookup"><span data-stu-id="30a1a-175">Voice Scenarios</span></span>

<span data-ttu-id="30a1a-176">La scheda **scenari vocali** dello strumento di configurazione del carico di Lync Server 2013 è illustrata nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="30a1a-176">The **Voice Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="30a1a-177">Utilizzare la scheda **scenari vocali** per configurare tutti gli scenari relativi alla voce.</span><span class="sxs-lookup"><span data-stu-id="30a1a-177">Use the **Voice Scenarios** tab to configure all of the voice-related scenarios.</span></span>

<span data-ttu-id="30a1a-178">![Scheda scenari vocali.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Scheda scenari vocali.")</span><span class="sxs-lookup"><span data-stu-id="30a1a-178">![Voice Scenarios tab.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Voice Scenarios tab.")</span></span>

1.  <span data-ttu-id="30a1a-179">In **VoIP**fare clic sul pulsante **Avanzate** e quindi specificare i valori per i campi **PhoneAreaCode** e **LocationProfile** (dial plan).</span><span class="sxs-lookup"><span data-stu-id="30a1a-179">In **VoIP**, click the **Advanced** button, and then provide values for the **PhoneAreaCode** and **LocationProfile** (dial plan) fields.</span></span> <span data-ttu-id="30a1a-180">È inoltre necessario specificare un valore per il **livello di carico**.</span><span class="sxs-lookup"><span data-stu-id="30a1a-180">You must also specify a value for **Load Level**.</span></span> <span data-ttu-id="30a1a-181">Se il livello di carico per **VoIP** e **gateway UC/PSTN** è abilitato, verrà sempre generato un file di configurazione della rete PSTN (Public Switched Telephone Network) a Unified Communications (UC) in grado di simulare le chiamate esterne.</span><span class="sxs-lookup"><span data-stu-id="30a1a-181">If Load Level for **VoIP** and **UC/PSTN Gateway** is Enabled, then a public switched telephone network (PSTN) to unified communications (UC) configuration file will always be generated that will simulate external calls.</span></span>

2.  <span data-ttu-id="30a1a-182">Nel **gateway UC/PSTN**, specificare un valore per il livello di carico.</span><span class="sxs-lookup"><span data-stu-id="30a1a-182">In **UC/PSTN Gateway**, specify a value for Load Level.</span></span> <span data-ttu-id="30a1a-183">Se si seleziona un livello di carico diverso da **disabled**, è necessario specificare un valore per il **codice area PSTN** facendo clic sul pulsante **Aggiungi** in Mediation Server e PSTN.</span><span class="sxs-lookup"><span data-stu-id="30a1a-183">If you select a load level other than **Disabled**, you must supply a value for **PSTN Area Code** by clicking the **Add** button under Mediation Server and PSTN.</span></span> <span data-ttu-id="30a1a-184">Verificare di disporre di una route configurata per il prefisso.</span><span class="sxs-lookup"><span data-stu-id="30a1a-184">Verify that you have a route configured for that area code.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30a1a-185">È possibile utilizzare il pannello di controllo di Lync Server o Lync Server Management Shell per verificare la configurazione della route vocale.</span><span class="sxs-lookup"><span data-stu-id="30a1a-185">You can use either the Lync Server Control Panel or the Lync Server Management Shell to verify voice route configuration.</span></span>

    
    </div>

3.  <span data-ttu-id="30a1a-186">In **Operatore Conferenza**specificare un valore per il livello di carico.</span><span class="sxs-lookup"><span data-stu-id="30a1a-186">In **Conferencing Attendant**, specify a value for Load Level.</span></span> <span data-ttu-id="30a1a-187">La selezione di un livello di carico (diverso da **disabled**) consentirà il campo **numero di telefono** .</span><span class="sxs-lookup"><span data-stu-id="30a1a-187">Selecting a load level (other than **Disabled**) will enable the **Telephone Number** field.</span></span> <span data-ttu-id="30a1a-188">Immettere il numero di telefono dell'operatore automatico che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="30a1a-188">Enter the telephone number of the Auto Attendant that you want to use.</span></span> <span data-ttu-id="30a1a-189">Fare inoltre clic sul pulsante **Avanzate** e quindi specificare un valore per il campo **LocationProfile** .</span><span class="sxs-lookup"><span data-stu-id="30a1a-189">Also, click the **Advanced** button, and then specify a value for the **LocationProfile** field.</span></span>

4.  <span data-ttu-id="30a1a-190">In **servizio parcheggio di chiamata**specificare il valore appropriato per il **livello di carico**.</span><span class="sxs-lookup"><span data-stu-id="30a1a-190">In **Call Park Service**, specify the appropriate value for **Load Level**.</span></span>

5.  <span data-ttu-id="30a1a-191">In **Mediation Server e PSTN**, per ogni Mediation Server che si desidera utilizzare, è necessario disporre di un simulatore PSTN separato.</span><span class="sxs-lookup"><span data-stu-id="30a1a-191">In **Mediation Server and PSTN**, for each Mediation Server that you want to use, you must have a separate PSTN simulator.</span></span> <span data-ttu-id="30a1a-192">Dopo aver determinato il client che si intende utilizzare come simulatore, è necessario configurare il Mediation Server per instradare le chiamate al computer sulla porta del simulatore PSTN configurata.</span><span class="sxs-lookup"><span data-stu-id="30a1a-192">After you have determined which client you are going to use as the simulator, you need to configure your Mediation Server to route calls to that computer on the PSTN Simulator port that you configured.</span></span> <span data-ttu-id="30a1a-193">Fare clic su **Aggiungi** per configurare il valore per il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="30a1a-193">Click **Add** to configure the value for the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="30a1a-194">A ognuno degli scenari è associato un pulsante <STRONG>avanzato</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="30a1a-194">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="30a1a-195">Questi pulsanti consentono l'accesso a valori specifici di ogni scenario in cui verrà modificato il comportamento dello strumento di LyncPerfTool (stress and Performance Tool) di Lync Server 2013 e l'abilitazione della personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="30a1a-195">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="30a1a-196">Per ogni scenario nella scheda <STRONG>scenari vocali</STRONG> , se il valore del <STRONG>livello di carico</STRONG> è <STRONG>Custom</STRONG>, la frequenza di conversazione viene calcolata utilizzando il campo corrispondente nella finestra di dialogo <STRONG>Avanzate</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="30a1a-196">For each scenario on the <STRONG>Voice Scenarios</STRONG> tab, if the value of <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the conversation rate will be calculated by using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="30a1a-197">Il nome del campo è diverso, a seconda dello scenario, ma la descrizione del campo diventerà "Nota: questo numero verrà utilizzato solo se è selezionata l'opzione personalizzato dal menu a discesa".</span><span class="sxs-lookup"><span data-stu-id="30a1a-197">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span>



</div>

</div>

<div>

## <a name="reach"></a><span data-ttu-id="30a1a-198">Raggiungere</span><span class="sxs-lookup"><span data-stu-id="30a1a-198">Reach</span></span>

<span data-ttu-id="30a1a-199">REACH è una nuova esperienza in Lync Server 2013 che supporta gli scenari di conferenza tramite il server Unified Communications Web API (UCWA) installato nel server Front-End.</span><span class="sxs-lookup"><span data-stu-id="30a1a-199">Reach is a new experience in Lync Server 2013 that supports conferencing scenarios through the Unified Communications Web API (UCWA) server that is installed on the Front-End server.</span></span> <span data-ttu-id="30a1a-200">La scheda **REACH** dello strumento di configurazione del carico di Lync Server 2013 è illustrata nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="30a1a-200">The **Reach** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="30a1a-201">Utilizzare la scheda **portata** per configurare tutti gli scenari relativi a REACH.</span><span class="sxs-lookup"><span data-stu-id="30a1a-201">Use the **Reach** tab to configure all the reach-related scenarios.</span></span>

<span data-ttu-id="30a1a-202">![Scheda REACH.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Scheda REACH.")</span><span class="sxs-lookup"><span data-stu-id="30a1a-202">![Reach tab.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Reach tab.")</span></span>

1.  <span data-ttu-id="30a1a-203">Fare clic sul pulsante **Avanzate** accanto a **Impostazioni generali di accesso**.</span><span class="sxs-lookup"><span data-stu-id="30a1a-203">Click the **Advanced** button next to **General Reach Settings**.</span></span> <span data-ttu-id="30a1a-204">Impostare il campo **UcwaTargetServerUrl** sul server IP virtuale (VIP) del pool di server Director o sul VIP del pool Front end.</span><span class="sxs-lookup"><span data-stu-id="30a1a-204">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="30a1a-205">In **condivisione applicazioni**, **collaborazione dati**e **messaggistica istantanea**selezionare il valore appropriato per il **livello di carico**.</span><span class="sxs-lookup"><span data-stu-id="30a1a-205">In **Application Sharing**, **Data Collaboration**, and **IM**, select the appropriate value for **Load Level**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="30a1a-206">A ognuno degli scenari è associato un pulsante <STRONG>avanzato</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="30a1a-206">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="30a1a-207">Questi pulsanti consentono l'accesso a valori specifici di ogni scenario in cui verrà modificato il comportamento dello strumento di LyncPerfTool (stress and Performance Tool) di Lync Server 2013 e l'abilitazione della personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="30a1a-207">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="30a1a-208">Per ognuno degli scenari di portata, se il <STRONG>livello di carico</STRONG> è <STRONG>personalizzato</STRONG>, viene utilizzato il valore specificato nel campo <STRONG>ConversationsPerHour</STRONG> anziché quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="30a1a-208">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default</span></span>



</div>

<span data-ttu-id="30a1a-209">La scheda **dispositivi mobili** consente di configurare tutti gli scenari relativi alla mobilità.</span><span class="sxs-lookup"><span data-stu-id="30a1a-209">Use the **Mobility** tab to configure all of the mobility-related scenarios.</span></span>

<span data-ttu-id="30a1a-210">![Scheda dispositivi mobili.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Scheda dispositivi mobili.")</span><span class="sxs-lookup"><span data-stu-id="30a1a-210">![Mobility tab.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Mobility tab.")</span></span>

1.  <span data-ttu-id="30a1a-211">Fare clic sul pulsante **Avanzate** accanto a **mobilità (UCWA)**.</span><span class="sxs-lookup"><span data-stu-id="30a1a-211">Click the **Advanced** button next to **Mobility (UCWA)**.</span></span> <span data-ttu-id="30a1a-212">Impostare il campo **UcwaTargetServerUrl** sul server IP virtuale (VIP) del pool di server Director o sul VIP del pool Front end.</span><span class="sxs-lookup"><span data-stu-id="30a1a-212">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="30a1a-213">In **presenza e \\ audio di messaggistica istantanea P2P**, selezionare il valore appropriato per il **livello di carico** per abilitare la simulazione dello scenario per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="30a1a-213">In **Presence and P2P Instant Messaging\\Audio**, select the appropriate value for **Load Level** to enable Mobility Scenario simulation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="30a1a-214">A ognuno degli scenari è associato un pulsante <STRONG>avanzato</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="30a1a-214">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="30a1a-215">Questi pulsanti consentono l'accesso a valori specifici di ogni scenario in cui verrà modificato il comportamento dello strumento di LyncPerfTool (stress and Performance Tool) di Lync Server 2013 e l'abilitazione della personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="30a1a-215">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="30a1a-216">Per ognuno degli scenari di portata, se il <STRONG>livello di carico</STRONG> è <STRONG>personalizzato</STRONG>, viene utilizzato il valore specificato nel campo <STRONG>ConversationsPerHour</STRONG> anziché quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="30a1a-216">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default.</span></span>



</div>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="30a1a-217">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="30a1a-217">Summary</span></span>

<span data-ttu-id="30a1a-218">La scheda **Riepilogo** dello strumento di configurazione del carico di Lync Server 2013 è illustrata nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="30a1a-218">The **Summary** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="30a1a-219">![Scheda Riepilogo.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Scheda Riepilogo.")</span><span class="sxs-lookup"><span data-stu-id="30a1a-219">![Summary tab.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Summary tab.")</span></span>

<span data-ttu-id="30a1a-220">La scheda **Riepilogo** indica gli utenti da utilizzare per ogni scenario.</span><span class="sxs-lookup"><span data-stu-id="30a1a-220">The **Summary** tab indicates which users to use for each of the scenarios.</span></span> <span data-ttu-id="30a1a-221">È possibile configurare manualmente gli intervalli di numeri utente selezionando la casella di controllo **Abilita generazione di un intervallo di utenti personalizzato** e quindi facendo doppio clic sullo scenario nella tabella che include l' **intervallo di utenti** che si desidera personalizzare.</span><span class="sxs-lookup"><span data-stu-id="30a1a-221">It is possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the **User Range** that you want to customize.</span></span> <span data-ttu-id="30a1a-222">Controllare (RunClient.bat) aggiungere il ritardo di accesso all'avvio, per includere i ritardi nei file batch generati in modo che corrispondano alla frequenza di accesso.</span><span class="sxs-lookup"><span data-stu-id="30a1a-222">Check (RunClient.bat) Add sign-in delay when starting, in order to include delays in the generated batch files to correspond with the sign-in rate.</span></span> <span data-ttu-id="30a1a-223">Questa operazione è utile per impedire l'overload del server quando si effettua l'accesso a un numero elevato di utenti.</span><span class="sxs-lookup"><span data-stu-id="30a1a-223">This is useful to prevent server overload when signing in a large number of users.</span></span> <span data-ttu-id="30a1a-224">Fare clic su **genera file**e selezionare la cartella in cui si desidera generare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="30a1a-224">Click **Generate Files**, and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="30a1a-225">Una finestra di dialogo simile alla figura seguente comparirà quando i file sono stati creati correttamente.</span><span class="sxs-lookup"><span data-stu-id="30a1a-225">A dialog box similar to the following figure will appear when your files have been successfully created.</span></span>

<span data-ttu-id="30a1a-226">![Conferma che i file sono stati creati.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Conferma che i file sono stati creati.")</span><span class="sxs-lookup"><span data-stu-id="30a1a-226">![Acknowledgement that files have been created.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Acknowledgement that files have been created.")</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="30a1a-227">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30a1a-227">See Also</span></span>


[<span data-ttu-id="30a1a-228">Creare utenti e contatti</span><span class="sxs-lookup"><span data-stu-id="30a1a-228">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
