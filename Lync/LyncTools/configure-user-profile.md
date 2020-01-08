---
title: Configurare il profilo utente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e982156928cf36b4e20eaf86175d7acbdf048b6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a><span data-ttu-id="d1617-102">Configurare il profilo utente</span><span class="sxs-lookup"><span data-stu-id="d1617-102">Configure User Profile</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1617-103">_**Argomento Ultima modifica:** 2018-10-11_</span><span class="sxs-lookup"><span data-stu-id="d1617-103">_**Topic Last Modified:** 2018-10-11_</span></span>

<span data-ttu-id="d1617-104">Gli strumenti inclusi nel pacchetto dello strumento di stress e prestazioni di Lync Server 2013 consentono di creare e configurare gli account utente di test che è possibile usare per eseguire le simulazioni di caricamento.</span><span class="sxs-lookup"><span data-stu-id="d1617-104">The tools included in the Lync Server 2013 Stress and Performance Tool package enable you to create and configure test user accounts that you can use to run load simulations.</span></span> <span data-ttu-id="d1617-105">Usare lo strumento di creazione dell'utente di Lync Server 2013 per creare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d1617-105">Use the Lync Server 2013 User Creation Tool to create the users.</span></span> <span data-ttu-id="d1617-106">Per informazioni dettagliate, vedere [creare utenti e contatti](create-users-and-contacts.md). Dopo aver creato gli utenti, configurare i profili utente usando lo strumento di configurazione del caricamento di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1617-106">(For details, see [Create Users and Contacts](create-users-and-contacts.md).) After users are created, configure the user profiles by using the Lync Server 2013 Load Configuration Tool.</span></span>

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a><span data-ttu-id="d1617-107">Eseguire lo strumento di configurazione del caricamento di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1617-107">Running the Lync Server 2013 Load Configuration Tool</span></span>

<span data-ttu-id="d1617-108">Per configurare i profili utente, eseguire lo strumento di configurazione del carico di Lync Server 2013 (UserProfileGenerator. exe) e compilare tutte le schede.</span><span class="sxs-lookup"><span data-stu-id="d1617-108">To configure user profiles, run the Lync Server 2013 Load Configuration Tool (UserProfileGenerator.exe) and fill out each of the tabs.</span></span> <span data-ttu-id="d1617-109">UserProfileGenerator. exe genera una directory per ogni computer client necessario per eseguire la simulazione.</span><span class="sxs-lookup"><span data-stu-id="d1617-109">UserProfileGenerator.exe generates a directory for each of the client computers that you need to run the simulation.</span></span> <span data-ttu-id="d1617-110">Ogni directory client include anche uno script per avviare tutte le istanze dello strumento di ottimizzazione dello stress e delle prestazioni di Lync Server 2013 (LyncPerfTool. exe).</span><span class="sxs-lookup"><span data-stu-id="d1617-110">Each client directory also comes with a script to start all the instances of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d1617-111">I valori specifici dell'utente specificati in UserProfileGenerator devono corrispondere ai valori specificati nello strumento di creazione degli utenti di Lync Server 2013 (UserProvisioningTool) per il pool.</span><span class="sxs-lookup"><span data-stu-id="d1617-111">The user-specific values specified in UserProfileGenerator must match the values specified in the Lync Server 2013 User Creation Tool (UserProvisioningTool) for the pool.</span></span>



</div>

<span data-ttu-id="d1617-112">Compilare i campi di ogni scheda dello strumento di configurazione del carico di Lync Server 2013, come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d1617-112">Fill in the fields on each tab of the Lync Server 2013 Load Configuration Tool, as described in the following sections.</span></span>

<div>

## <a name="common-configuration"></a><span data-ttu-id="d1617-113">Configurazione comune</span><span class="sxs-lookup"><span data-stu-id="d1617-113">Common Configuration</span></span>

<span data-ttu-id="d1617-114">Nella figura seguente è illustrata la scheda **configurazione comune** dello strumento di configurazione del carico di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1617-114">The **Common Configuration** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span> <span data-ttu-id="d1617-115">Compilare i campi della scheda **configurazione comune** , come descritto nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="d1617-115">Fill in the fields of the **Common Configuration** tab, as described in the following steps.</span></span>

<span data-ttu-id="d1617-116">![Scheda di configurazione comune.] (images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Scheda di configurazione comune.")</span><span class="sxs-lookup"><span data-stu-id="d1617-116">![Common Configuration tab.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Common Configuration tab.")</span></span>

1.  <span data-ttu-id="d1617-117">In **numero di macchine disponibili**Digitare o fare clic sul numero di computer che si desidera utilizzare per eseguire LyncPerfTool. exe.</span><span class="sxs-lookup"><span data-stu-id="d1617-117">In **Number of Available Machines**, type or click the number of computers that you want to use to run LyncPerfTool.exe.</span></span> <span data-ttu-id="d1617-118">Ti consigliamo di avere un computer per ogni utente di 4.500 che dovrai simulare.</span><span class="sxs-lookup"><span data-stu-id="d1617-118">We recommend that you have one computer for every 4,500 users that you will be simulating.</span></span> <span data-ttu-id="d1617-119">Questo numero può variare se si riduce il livello di carico o se si usa solo un sottoinsieme delle funzionalità disponibili.</span><span class="sxs-lookup"><span data-stu-id="d1617-119">That number may vary if you reduce the load level or if you use only a subset of the available features.</span></span> <span data-ttu-id="d1617-120">(I livelli di carico sono impostati nella scheda **scenari generali** ).</span><span class="sxs-lookup"><span data-stu-id="d1617-120">(Load levels are set on the **General Scenarios** tab.)</span></span>

2.  <span data-ttu-id="d1617-121">In **prefisso per i nomi utente**Digitare il prefisso per il nome utente degli utenti.</span><span class="sxs-lookup"><span data-stu-id="d1617-121">In **Prefix for User Names**, type the prefix for the user name of the users.</span></span> <span data-ttu-id="d1617-122">Per eseguire l'accesso, l'URI (Uniform Resource Identifier) sarà: Indice\[di inizio dell'utente di UserPrefix... (Numero di utenti-1) \]@User dominio.</span><span class="sxs-lookup"><span data-stu-id="d1617-122">To log in, the Uniform Resource Identifier (URI) will be: UserPrefix\[User Start Index…(Number Of Users-1)\]@User Domain.</span></span>

3.  <span data-ttu-id="d1617-123">Nella **password per tutti gli utenti**immettere la password usata per la creazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="d1617-123">In **Password for All Users**, enter the password that was used for creating the users.</span></span> <span data-ttu-id="d1617-124">Se si lascia vuoto questo campo, il nome utente verrà usato come password.</span><span class="sxs-lookup"><span data-stu-id="d1617-124">If you leave this field empty, the username will be used as the password.</span></span>

4.  <span data-ttu-id="d1617-125">Nell' **Indice Start utente**fare clic o digitare l'indice del primo utente da configurare.</span><span class="sxs-lookup"><span data-stu-id="d1617-125">In **User Start Index**, click or type the index of the first user to be configured.</span></span> <span data-ttu-id="d1617-126">È possibile configurare intervalli diversi per diversi tipi o livelli di carico, ma è necessario eseguire UserProfileGenerator. exe una volta per l'intervallo che si vuole configurare.</span><span class="sxs-lookup"><span data-stu-id="d1617-126">You can configure different ranges for different types or levels of load, but you must run UserProfileGenerator.exe once per the range that you want to configure.</span></span>

5.  <span data-ttu-id="d1617-127">In **numero di utenti**fare clic o digitare il numero totale di utenti che si vuole configurare.</span><span class="sxs-lookup"><span data-stu-id="d1617-127">In **Number of Users**, click or type the total number of users you are going to configure.</span></span>

6.  <span data-ttu-id="d1617-128">In **dominio utente**Digitare il dominio usato per l'URI SIP.</span><span class="sxs-lookup"><span data-stu-id="d1617-128">In **User Domain**, type the domain used for the SIP URI.</span></span> <span data-ttu-id="d1617-129">Viene usato per creare l'URI SIP di ogni utente per accedere al server front end server o Standard Edition di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1617-129">This is used to construct the SIP URI of each user to log on to the Lync Server 2013 Front End Server or Standard Edition server.</span></span> <span data-ttu-id="d1617-130">Può essere diverso dal dominio dell'account.</span><span class="sxs-lookup"><span data-stu-id="d1617-130">It can be different from the account domain.</span></span>

7.  <span data-ttu-id="d1617-131">In **dominio account**Digitare l'accesso al dominio servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d1617-131">In **Account Domain**, type the Active Directory Domain Services domain logon.</span></span>

8.  <span data-ttu-id="d1617-132">Immettere il numero massimo di endpoint simultanei in **accesso al secondo (per istanza)** per cui si vuole che lo strumento acceda a tutti gli endpoint/utenti.</span><span class="sxs-lookup"><span data-stu-id="d1617-132">Enter the maximum number of concurrent endpoints in **Sign In Per Second (per instance)** for which you want the tool to log in all the endpoints/users.</span></span> <span data-ttu-id="d1617-133">La frequenza consigliata \<è = 2 per secondo/standard SKU Fe.</span><span class="sxs-lookup"><span data-stu-id="d1617-133">The recommended rate is \<=2 per second/standard SKU FE.</span></span>

9.  <span data-ttu-id="d1617-134">In **FQDN del proxy o del pool di Access**Digitare il nome di dominio completo (FQDN) del server a cui si vuole connettere i client.</span><span class="sxs-lookup"><span data-stu-id="d1617-134">In **Access Proxy or Pool FQDN**, type the fully qualified domain name (FQDN) of the server that you want the clients to connect to.</span></span> <span data-ttu-id="d1617-135">Se gli utenti accedono esternamente, specificare il proxy di accesso.</span><span class="sxs-lookup"><span data-stu-id="d1617-135">If the users are logging on externally, specify the access proxy.</span></span> <span data-ttu-id="d1617-136">Se gli utenti sono interni, specificare il nome di dominio completo del pool o del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d1617-136">If the users are internal, specify the FQDN of their pool or Standard Edition server.</span></span>

10. <span data-ttu-id="d1617-137">In **porta**fare clic o digitare la porta che si vuole che gli utenti usino per SIP (il valore predefinito è 5061).</span><span class="sxs-lookup"><span data-stu-id="d1617-137">In **Port**, click or type the port that you want users to use for SIP (the default is 5061).</span></span>

<span data-ttu-id="d1617-138">Per le impostazioni del server di rete esterno, specificare il **proxy di accesso o il nome FQDN del pool** e la **porta**.</span><span class="sxs-lookup"><span data-stu-id="d1617-138">For External Network Server Settings, specify the **Access Proxy or Pool FQDN** and the **Port**.</span></span> <span data-ttu-id="d1617-139">Queste impostazioni vengono usate solo per la simulazione di caricamento degli endpoint esterni.</span><span class="sxs-lookup"><span data-stu-id="d1617-139">These settings are used only for External endpoints load simulation.</span></span>

</div>

<div>

## <a name="general-scenarios"></a><span data-ttu-id="d1617-140">Scenari generali</span><span class="sxs-lookup"><span data-stu-id="d1617-140">General Scenarios</span></span>

<span data-ttu-id="d1617-141">Nella figura seguente è illustrata la scheda **scenari generali** dello strumento di configurazione del carico di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1617-141">The **General Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="d1617-142">Configurare i livelli di carico e i parametri per ognuno degli scenari generali che si desidera eseguire o uscire da Disabled.</span><span class="sxs-lookup"><span data-stu-id="d1617-142">Configure the load levels and parameters for each of the general scenarios that you want to run, or leave disabled.</span></span>

<span data-ttu-id="d1617-143">![Scheda scenari generali.] (images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "Scheda scenari generali.")</span><span class="sxs-lookup"><span data-stu-id="d1617-143">![General Scenarios tab.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "General Scenarios tab.")</span></span>

1.  <span data-ttu-id="d1617-144">Nella **messaggistica istantanea**, che include peer-to-peer e conferenze, specificare il valore appropriato per il livello di carico.</span><span class="sxs-lookup"><span data-stu-id="d1617-144">In **Instant Messaging**, which includes peer-to-peer and conferencing, specify the appropriate value for the Load Level.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1617-145">I valori del livello di caricamento per tutti i campi (ad eccezione dei servizi di informazioni sulla posizione) sono <STRONG>disabilitati</STRONG>, <STRONG>Bassi</STRONG>, <STRONG>medi</STRONG>, <STRONG>alti</STRONG>e <STRONG>personalizzati</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d1617-145">Load level values for all fields (except Location Information Services) are <STRONG>Disabled</STRONG>, <STRONG>Low</STRONG>, <STRONG>Medium</STRONG>, <STRONG>High</STRONG>, and <STRONG>Custom</STRONG>.</span></span> <span data-ttu-id="d1617-146">Quando è selezionata l'opzione bassa, media, alta o personalizzata, le configurazioni verranno generate per ogni modalità e client.</span><span class="sxs-lookup"><span data-stu-id="d1617-146">When Low, Medium, High, or Custom is selected, configurations will be generated for each modality and client.</span></span> <span data-ttu-id="d1617-147">Alto comporterà il carico massimo supportato da generare per il server, media corrisponde a 60% del carico e basso corrisponde al 30% del carico.</span><span class="sxs-lookup"><span data-stu-id="d1617-147">High will result in the maximum supported load to be generated for the server, Medium corresponds to 60 percent of the load, and Low corresponds to 30 percent of the load.</span></span>

    
    </div>

2.  <span data-ttu-id="d1617-148">In **servizi di audioconferenza,** che è solo audioconferenza, specificare il valore appropriato per il livello di carico.</span><span class="sxs-lookup"><span data-stu-id="d1617-148">In **Audio Conferencing**, which is audio conferencing only, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="d1617-149">Le chiamate peer-to-peer sono descritte nella sezione scenari vocali più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d1617-149">Peer-to-peer calls are covered in the Voice Scenarios section later in this topic.</span></span> <span data-ttu-id="d1617-150">Per abilitare MultiView, aprire la scheda **Avanzate** per tale modalità.</span><span class="sxs-lookup"><span data-stu-id="d1617-150">To enable MultiView, open the **Advanced** tab for that modality.</span></span>

3.  <span data-ttu-id="d1617-151">In **condivisione applicazioni**specificare il valore appropriato per il livello di carico.</span><span class="sxs-lookup"><span data-stu-id="d1617-151">In **Application Sharing**, specify the appropriate value for Load Level.</span></span>

4.  <span data-ttu-id="d1617-152">In **collaborazione**con i dati, che include i servizi di conferenza dati, specificare il valore appropriato per il livello di carico.</span><span class="sxs-lookup"><span data-stu-id="d1617-152">In **Data Collaboration**, which includes data conferencing, specify the appropriate value for Load Level.</span></span>

5.  <span data-ttu-id="d1617-153">In **espansione elenco di distribuzione**specificare il valore appropriato per il livello di carico.</span><span class="sxs-lookup"><span data-stu-id="d1617-153">In **Distribution List Expansion**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="d1617-154">Devi anche fare clic sul pulsante **Avanzate** e quindi compilare i campi con gli stessi valori configurati nella scheda lista di **distribuzione** dello strumento di creazione degli utenti di Lync Server (UserProvisioningTool. exe).</span><span class="sxs-lookup"><span data-stu-id="d1617-154">You must also click the **Advanced** button, and then fill in the fields with the same values that you configured on the **Distribution List** tab of the Lync Server User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="d1617-155">Per informazioni dettagliate su questi campi, vedere [creare utenti e contatti](create-users-and-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="d1617-155">For details about these fields, see [Create Users and Contacts](create-users-and-contacts.md)</span></span>

6.  <span data-ttu-id="d1617-156">In **query Web**Rubrica, che è il servizio di ricerca rubrica (non il download di file della rubrica), specificare il valore appropriato per il livello di carico.</span><span class="sxs-lookup"><span data-stu-id="d1617-156">In **Address Book Web Query**, which is the address book lookup service (not the address book file download), specify the appropriate value for Load Level.</span></span> <span data-ttu-id="d1617-157">Per abilitare i download della Rubrica, fare clic sul pulsante **Avanzate** corrispondente e quindi impostare **EnableABSDownload** su true.</span><span class="sxs-lookup"><span data-stu-id="d1617-157">To enable address book downloads, click the corresponding **Advanced** button, and then set **EnableABSDownload** to true.</span></span>

7.  <span data-ttu-id="d1617-158">In **Response Group Service**specificare il valore appropriato per il livello di carico.</span><span class="sxs-lookup"><span data-stu-id="d1617-158">In **Response Group Service**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="d1617-159">Devi anche fare clic sul pulsante **avanzato** corrispondente e quindi specificare gli URI dei gruppi di risposte già creati durante il provisioning degli agenti del servizio Response Group.</span><span class="sxs-lookup"><span data-stu-id="d1617-159">You must also click the corresponding **Advanced** button, and then specify the URIs of the response groups you have already created when provisioning Response Group Service agents.</span></span> <span data-ttu-id="d1617-160">Devi specificare almeno un gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="d1617-160">You must specify at least one response group.</span></span> <span data-ttu-id="d1617-161">Usare i punti e virgola per separare più gruppi di risposta.</span><span class="sxs-lookup"><span data-stu-id="d1617-161">Use semicolons to separate multiple response groups.</span></span> <span data-ttu-id="d1617-162">Aggiornare RGSUriSuffixStartIndex e RGSUriSuffixEndIndex ai valori effettivi.</span><span class="sxs-lookup"><span data-stu-id="d1617-162">Update RGSUriSuffixStartIndex and RGSUriSuffixEndIndex to the actual values.</span></span>

8.  <span data-ttu-id="d1617-163">In **Servizi informazioni sulla posizione**selezionare il valore appropriato per il livello di carico.</span><span class="sxs-lookup"><span data-stu-id="d1617-163">In **Location Information Services**, select the appropriate value for Load Level.</span></span> <span data-ttu-id="d1617-164">Il livello di carico per i servizi di informazioni sulla posizione deve essere **abilitato** o **disabilitato**.</span><span class="sxs-lookup"><span data-stu-id="d1617-164">The load level for Location Information Services must be **Enabled** or **Disabled**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1617-165">Ogni scenario include un pulsante <STRONG>avanzato</STRONG> che si trova accanto a esso e un set di caselle di controllo che consentono varianti degli scenari.</span><span class="sxs-lookup"><span data-stu-id="d1617-165">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it, and a set of check boxes that enable variations of the scenarios.</span></span> <span data-ttu-id="d1617-166">Mezzi <STRONG>ad hoc</STRONG> per generare una simulazione di conferenze che verranno create per tutta l'ora.</span><span class="sxs-lookup"><span data-stu-id="d1617-166"><STRONG>Ad-hoc</STRONG> means to generate simulation of conferences that will be created throughout the hour.</span></span> <span data-ttu-id="d1617-167"><STRONG>Grande conf</STRONG> significa che verrà simulato lo scenario di conferenza di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d1617-167"><STRONG>Large Conf</STRONG> means that Large Conference Scenario will be simulated.</span></span> <span data-ttu-id="d1617-168">Mezzi <STRONG>esterni</STRONG> per simulare anche utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="d1617-168"><STRONG>External</STRONG> means to also simulate external users.</span></span><BR><span data-ttu-id="d1617-169">I pulsanti e le caselle di controllo consentono l'accesso a valori specifici di ogni scenario che cambierà il comportamento dello strumento di LyncPerfTool (stress and performance) di Lync Server 2013 e renderanno possibile la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="d1617-169">These buttons and check boxes allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and make customization possible.</span></span> <span data-ttu-id="d1617-170">Per ogni scenario nella scheda <STRONG>scenari generali</STRONG> (ad eccezione di servizi di informazioni sulla posizione), se il valore del livello di carico è <STRONG>personalizzato</STRONG>, la frequenza di conversazione verrà calcolata usando il campo corrispondente nella finestra di dialogo <STRONG>Avanzate</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="d1617-170">For each scenario on the <STRONG>General Scenarios</STRONG> tab (except for Location Information Services), if the value of Load Level is <STRONG>Custom</STRONG>, then the conversation rate will be calculated using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="d1617-171">Il nome del campo è diverso, a seconda dello scenario, ma la descrizione del campo verrà visualizzata "Nota: questo numero verrà usato solo se è selezionato personalizzato dal menu a discesa."</span><span class="sxs-lookup"><span data-stu-id="d1617-171">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span> <span data-ttu-id="d1617-172">In generale, i valori <STRONG>alto</STRONG>, <STRONG>medio</STRONG>e <STRONG>basso</STRONG> altereranno i tassi di conversazione per modalità in linea con il modello utente che rappresenta un bilanciamento di tutti gli scenari.</span><span class="sxs-lookup"><span data-stu-id="d1617-172">In general, the values <STRONG>High</STRONG>, <STRONG>Medium</STRONG>, and <STRONG>Low</STRONG> will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="d1617-173">Se è necessario modificare il livello di carico per modalità a causa di una differenza nell'utilizzo previsto, è consigliabile usare una frequenza di conversazione <STRONG>personalizzata</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="d1617-173">If there is a need to change the load level per modality due to a difference in expected usage, we recommend using a <STRONG>Custom</STRONG> conversation rate.</span></span><BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a><span data-ttu-id="d1617-174">Scenari vocali</span><span class="sxs-lookup"><span data-stu-id="d1617-174">Voice Scenarios</span></span>

<span data-ttu-id="d1617-175">Nella figura seguente è illustrata la scheda **scenari vocali** dello strumento di configurazione del carico di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1617-175">The **Voice Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="d1617-176">Usare la scheda **scenari vocali** per configurare tutti gli scenari relativi alla voce.</span><span class="sxs-lookup"><span data-stu-id="d1617-176">Use the **Voice Scenarios** tab to configure all of the voice-related scenarios.</span></span>

<span data-ttu-id="d1617-177">![Scheda scenari vocali.] (images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Scheda scenari vocali.")</span><span class="sxs-lookup"><span data-stu-id="d1617-177">![Voice Scenarios tab.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Voice Scenarios tab.")</span></span>

1.  <span data-ttu-id="d1617-178">In **VoIP**fare clic sul pulsante **Avanzate** e quindi specificare i valori per i campi **PhoneAreaCode** e **LocationProfile** (dial plan).</span><span class="sxs-lookup"><span data-stu-id="d1617-178">In **VoIP**, click the **Advanced** button, and then provide values for the **PhoneAreaCode** and **LocationProfile** (dial plan) fields.</span></span> <span data-ttu-id="d1617-179">Devi anche specificare un valore per il **livello di carico**.</span><span class="sxs-lookup"><span data-stu-id="d1617-179">You must also specify a value for **Load Level**.</span></span> <span data-ttu-id="d1617-180">Se il livello di carico per **VoIP** e **gateway UC/PSTN** è abilitato, viene sempre generato un file di configurazione PSTN (Public Switched Telephone Network) to Unified Communications (UC) che simula le chiamate esterne.</span><span class="sxs-lookup"><span data-stu-id="d1617-180">If Load Level for **VoIP** and **UC/PSTN Gateway** is Enabled, then a public switched telephone network (PSTN) to unified communications (UC) configuration file will always be generated that will simulate external calls.</span></span>

2.  <span data-ttu-id="d1617-181">Nel **gateway UC/PSTN**specificare un valore per il livello di carico.</span><span class="sxs-lookup"><span data-stu-id="d1617-181">In **UC/PSTN Gateway**, specify a value for Load Level.</span></span> <span data-ttu-id="d1617-182">Se si seleziona un livello di carico diverso da **disabled**, è necessario specificare un valore per il **codice dell'area PSTN** facendo clic sul pulsante **Aggiungi** in Mediation Server e PSTN.</span><span class="sxs-lookup"><span data-stu-id="d1617-182">If you select a load level other than **Disabled**, you must supply a value for **PSTN Area Code** by clicking the **Add** button under Mediation Server and PSTN.</span></span> <span data-ttu-id="d1617-183">Verificare di avere una route configurata per il prefisso.</span><span class="sxs-lookup"><span data-stu-id="d1617-183">Verify that you have a route configured for that area code.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1617-184">È possibile usare il pannello di controllo di Lync Server o Lync Server Management Shell per verificare la configurazione della route vocale.</span><span class="sxs-lookup"><span data-stu-id="d1617-184">You can use either the Lync Server Control Panel or the Lync Server Management Shell to verify voice route configuration.</span></span>

    
    </div>

3.  <span data-ttu-id="d1617-185">In **Operatore Conferenza**specificare un valore per il livello di carico.</span><span class="sxs-lookup"><span data-stu-id="d1617-185">In **Conferencing Attendant**, specify a value for Load Level.</span></span> <span data-ttu-id="d1617-186">La selezione di un livello di carico (diverso da **disabled**) consentirà il campo **numero di telefono** .</span><span class="sxs-lookup"><span data-stu-id="d1617-186">Selecting a load level (other than **Disabled**) will enable the **Telephone Number** field.</span></span> <span data-ttu-id="d1617-187">Immettere il numero di telefono dell'operatore automatico che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="d1617-187">Enter the telephone number of the Auto Attendant that you want to use.</span></span> <span data-ttu-id="d1617-188">Fai anche clic sul pulsante **Avanzate** e quindi specifica un valore per il campo **LocationProfile** .</span><span class="sxs-lookup"><span data-stu-id="d1617-188">Also, click the **Advanced** button, and then specify a value for the **LocationProfile** field.</span></span>

4.  <span data-ttu-id="d1617-189">In **servizio parcheggio di chiamata**specificare il valore appropriato per il **livello di carico**.</span><span class="sxs-lookup"><span data-stu-id="d1617-189">In **Call Park Service**, specify the appropriate value for **Load Level**.</span></span>

5.  <span data-ttu-id="d1617-190">In **Mediation Server e PSTN**, per ogni Mediation Server che si vuole usare, è necessario disporre di un simulatore PSTN distinto.</span><span class="sxs-lookup"><span data-stu-id="d1617-190">In **Mediation Server and PSTN**, for each Mediation Server that you want to use, you must have a separate PSTN simulator.</span></span> <span data-ttu-id="d1617-191">Dopo aver determinato il client che si vuole usare come simulatore, è necessario configurare il Mediation Server per instradare le chiamate al computer nella porta di simulazione PSTN configurata.</span><span class="sxs-lookup"><span data-stu-id="d1617-191">After you have determined which client you are going to use as the simulator, you need to configure your Mediation Server to route calls to that computer on the PSTN Simulator port that you configured.</span></span> <span data-ttu-id="d1617-192">Fare clic su **Aggiungi** per configurare il valore per il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d1617-192">Click **Add** to configure the value for the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1617-193">Ogni scenario contiene un pulsante <STRONG>avanzato</STRONG> che si trova accanto.</span><span class="sxs-lookup"><span data-stu-id="d1617-193">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="d1617-194">Questi pulsanti consentono l'accesso a valori specifici di ogni scenario che cambierà il comportamento dello strumento di LyncPerfTool (stress and Performance Tool) di Lync Server 2013 e consentirà la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="d1617-194">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="d1617-195">Per ogni scenario della scheda <STRONG>scenari vocali</STRONG> , se il valore del <STRONG>livello di carico</STRONG> è <STRONG>personalizzato</STRONG>, la frequenza di conversazione verrà calcolata utilizzando il campo corrispondente nella finestra di dialogo <STRONG>Avanzate</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="d1617-195">For each scenario on the <STRONG>Voice Scenarios</STRONG> tab, if the value of <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the conversation rate will be calculated by using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="d1617-196">Il nome del campo è diverso, a seconda dello scenario, ma la descrizione del campo verrà visualizzata "Nota: questo numero verrà usato solo se è selezionato personalizzato dal menu a discesa."</span><span class="sxs-lookup"><span data-stu-id="d1617-196">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span>



</div>

</div>

<div>

## <a name="reach"></a><span data-ttu-id="d1617-197">Raggiungere</span><span class="sxs-lookup"><span data-stu-id="d1617-197">Reach</span></span>

<span data-ttu-id="d1617-198">REACH è una nuova esperienza in Lync Server 2013 che supporta scenari di conferenza tramite il server UCWA (Unified Communications Web API) installato nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="d1617-198">Reach is a new experience in Lync Server 2013 that supports conferencing scenarios through the Unified Communications Web API (UCWA) server that is installed on the Front-End server.</span></span> <span data-ttu-id="d1617-199">La scheda **REACH** dello strumento di configurazione del carico di Lync Server 2013 è illustrata nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="d1617-199">The **Reach** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="d1617-200">Usare la scheda **REACH** per configurare tutti gli scenari correlati a REACH.</span><span class="sxs-lookup"><span data-stu-id="d1617-200">Use the **Reach** tab to configure all the reach-related scenarios.</span></span>

<span data-ttu-id="d1617-201">![Scheda REACH.] (images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Scheda REACH.")</span><span class="sxs-lookup"><span data-stu-id="d1617-201">![Reach tab.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Reach tab.")</span></span>

1.  <span data-ttu-id="d1617-202">Fare clic sul pulsante **Avanzate** accanto a **Impostazioni generali di REACH**.</span><span class="sxs-lookup"><span data-stu-id="d1617-202">Click the **Advanced** button next to **General Reach Settings**.</span></span> <span data-ttu-id="d1617-203">Impostare il campo **UcwaTargetServerUrl** sul Virtual IP del pool di Director (VIP) o sul pool VIP di front-end.</span><span class="sxs-lookup"><span data-stu-id="d1617-203">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="d1617-204">Nella **condivisione delle applicazioni**, nella **collaborazione ai dati**e nella **messaggistica istantanea**selezionare il valore appropriato per il **livello di carico**.</span><span class="sxs-lookup"><span data-stu-id="d1617-204">In **Application Sharing**, **Data Collaboration**, and **IM**, select the appropriate value for **Load Level**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1617-205">Ogni scenario contiene un pulsante <STRONG>avanzato</STRONG> che si trova accanto.</span><span class="sxs-lookup"><span data-stu-id="d1617-205">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="d1617-206">Questi pulsanti consentono l'accesso a valori specifici di ogni scenario che cambierà il comportamento dello strumento di LyncPerfTool (stress and Performance Tool) di Lync Server 2013 e consentirà la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="d1617-206">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="d1617-207">Per ogni scenario REACH, se il livello di <STRONG>carico</STRONG> è <STRONG>personalizzato</STRONG>, viene usato il valore specificato nel campo <STRONG>ConversationsPerHour</STRONG> al posto di quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="d1617-207">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default</span></span>



</div>

<span data-ttu-id="d1617-208">Usare la scheda **mobilità** per configurare tutti gli scenari relativi alla mobilità.</span><span class="sxs-lookup"><span data-stu-id="d1617-208">Use the **Mobility** tab to configure all of the mobility-related scenarios.</span></span>

<span data-ttu-id="d1617-209">![Scheda mobilità.] (images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Scheda mobilità.")</span><span class="sxs-lookup"><span data-stu-id="d1617-209">![Mobility tab.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Mobility tab.")</span></span>

1.  <span data-ttu-id="d1617-210">Fare clic sul pulsante **Avanzate** accanto a **mobilità (UCWA)**.</span><span class="sxs-lookup"><span data-stu-id="d1617-210">Click the **Advanced** button next to **Mobility (UCWA)**.</span></span> <span data-ttu-id="d1617-211">Impostare il campo **UcwaTargetServerUrl** sul Virtual IP del pool di Director (VIP) o sul pool VIP di front-end.</span><span class="sxs-lookup"><span data-stu-id="d1617-211">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="d1617-212">In **presenza e audio di messaggistica\\istantanea P2P**Selezionare il valore appropriato per il **livello di carico** per abilitare la simulazione dello scenario di mobilità.</span><span class="sxs-lookup"><span data-stu-id="d1617-212">In **Presence and P2P Instant Messaging\\Audio**, select the appropriate value for **Load Level** to enable Mobility Scenario simulation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1617-213">Ogni scenario contiene un pulsante <STRONG>avanzato</STRONG> che si trova accanto.</span><span class="sxs-lookup"><span data-stu-id="d1617-213">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="d1617-214">Questi pulsanti consentono l'accesso a valori specifici di ogni scenario che cambierà il comportamento dello strumento di LyncPerfTool (stress and Performance Tool) di Lync Server 2013 e consentirà la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="d1617-214">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="d1617-215">Per ogni scenario REACH, se il livello di <STRONG>carico</STRONG> è <STRONG>personalizzato</STRONG>, viene usato il valore specificato nel campo <STRONG>ConversationsPerHour</STRONG> al posto di quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="d1617-215">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default.</span></span>



</div>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="d1617-216">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="d1617-216">Summary</span></span>

<span data-ttu-id="d1617-217">La scheda **Riepilogo** dello strumento di configurazione del carico di Lync Server 2013 è illustrata nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="d1617-217">The **Summary** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="d1617-218">![Scheda Riepilogo.] (images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Scheda Riepilogo.")</span><span class="sxs-lookup"><span data-stu-id="d1617-218">![Summary tab.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Summary tab.")</span></span>

<span data-ttu-id="d1617-219">La scheda **Riepilogo** indica gli utenti da usare per ogni scenario.</span><span class="sxs-lookup"><span data-stu-id="d1617-219">The **Summary** tab indicates which users to use for each of the scenarios.</span></span> <span data-ttu-id="d1617-220">È possibile configurare manualmente gli intervalli di numeri degli utenti selezionando la casella di controllo Abilita generazione di intervalli di **utenti personalizzati** e facendo doppio clic sullo scenario nella tabella che contiene l' **intervallo di utenti** che si vuole personalizzare.</span><span class="sxs-lookup"><span data-stu-id="d1617-220">It is possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the **User Range** that you want to customize.</span></span> <span data-ttu-id="d1617-221">Selezionare (RunClient. bat) il ritardo di accesso per includere i ritardi nei file batch generati in modo che corrispondano alla frequenza di accesso.</span><span class="sxs-lookup"><span data-stu-id="d1617-221">Check (RunClient.bat) Add sign-in delay when starting, in order to include delays in the generated batch files to correspond with the sign-in rate.</span></span> <span data-ttu-id="d1617-222">Questa operazione è utile per impedire l'overload del server quando si esegue l'accesso a un numero elevato di utenti.</span><span class="sxs-lookup"><span data-stu-id="d1617-222">This is useful to prevent server overload when signing in a large number of users.</span></span> <span data-ttu-id="d1617-223">Fare clic su **genera file**e selezionare la cartella in cui si vuole generare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="d1617-223">Click **Generate Files**, and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="d1617-224">Quando i file sono stati creati correttamente, verrà visualizzata una finestra di dialogo simile alla figura seguente.</span><span class="sxs-lookup"><span data-stu-id="d1617-224">A dialog box similar to the following figure will appear when your files have been successfully created.</span></span>

<span data-ttu-id="d1617-225">![Conferma che i file sono stati creati.] (images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Conferma che i file sono stati creati.")</span><span class="sxs-lookup"><span data-stu-id="d1617-225">![Acknowledgement that files have been created.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Acknowledgement that files have been created.")</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d1617-226">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1617-226">See Also</span></span>


[<span data-ttu-id="d1617-227">Creare utenti e contatti</span><span class="sxs-lookup"><span data-stu-id="d1617-227">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
