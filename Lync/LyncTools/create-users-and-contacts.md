---
title: Creare utenti e contatti
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76b8016079cd130a814da410df5e5a5b151d8702
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a><span data-ttu-id="d200f-102">Creare utenti e contatti</span><span class="sxs-lookup"><span data-stu-id="d200f-102">Create Users and Contacts</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d200f-103">_**Ultimo argomento modificato:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="d200f-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="d200f-104">È necessario utilizzare lo strumento di provisioning degli utenti di Lync Server 2013 (UserProvisioningTool. exe) per creare utenti e contatti in preparazione per i test di carico di stress e prestazioni.</span><span class="sxs-lookup"><span data-stu-id="d200f-104">You must use the Lync Server 2013 User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts in preparation for stress and performance load testing.</span></span>

<span data-ttu-id="d200f-105">Di seguito sono elencati i termini e le definizioni che è possibile trovare utili durante la lettura di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d200f-105">Here is a list of terms and definitions that you might find useful as you read through this topic.</span></span>

  - <span data-ttu-id="d200f-106">Unità organizzativa – unità organizzativa servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d200f-106">Organizational Unit – The Active Directory Domain Services organizational unit (OU).</span></span>

  - <span data-ttu-id="d200f-107">Federati/pool incrociato: utenti che saranno abilitati a comunicare con utenti di altri servizi di messaggistica istantanea, quali la rete MSN di servizi Internet, AOL® e Yahoo\!®.</span><span class="sxs-lookup"><span data-stu-id="d200f-107">Federated / Cross Pool – Users who will be enabled to communicate with users from other Instant Messaging (IM) services, such as MSN network of Internet services, AOL®, and Yahoo\!®.</span></span>

  - <span data-ttu-id="d200f-108">Liste di distribuzione: gli oggetti in servizi di dominio Active Directory che contengono un elenco di utenti di servizi di dominio Active Directory, utilizzati per avviare comunicazioni con gruppi di persone.</span><span class="sxs-lookup"><span data-stu-id="d200f-108">Distribution Lists – The objects in Active Directory Domain Services that contain a list of Active Directory Domain Services users, used for launching communications with groups of people.</span></span>

  - <span data-ttu-id="d200f-109">Servizio informazioni percorso – il servizio Lync Server 2013 che, se abilitato e configurato per telefono, consente di recuperare il percorso fisico per i servizi Enhanced 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="d200f-109">Location Info Service – The Lync Server 2013 service that, when enabled and configured per phone, enables retrieval of physical location for Enhanced 9-1-1 (E9-1-1) services.</span></span>

  - <span data-ttu-id="d200f-110">Numeri di telefono degli Stati Uniti: i numeri di telefono assegnati agli utenti, oltre all'URI SIP utilizzato per il routing delle chiamate in ingresso e in uscita e la ricerca di numeri inversi (inversa).</span><span class="sxs-lookup"><span data-stu-id="d200f-110">U.S. Phone Numbers – The phone numbers that are assigned to users, in addition to the SIP URI that is used for routing inbound and outbound calls and reverse number lookup (RNL).</span></span>

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="d200f-111">Creare utenti e contatti utilizzando UserProvisioningTool. exe</span><span class="sxs-lookup"><span data-stu-id="d200f-111">Create Users and Contacts by Using UserProvisioningTool.exe</span></span>

<span data-ttu-id="d200f-112">Per creare utenti e contatti per la simulazione di carico, è necessario utilizzare lo strumento di provisioning utente di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d200f-112">You must use the Lync Server User Provisioning Tool to create users and contacts for load simulation.</span></span> <span data-ttu-id="d200f-113">Lo strumento di provisioning degli utenti di Lync Server viene installato con il pacchetto dello strumento di prestazioni e stress di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d200f-113">The Lync Server User Provisioning Tool is installed with the Lync Server Stress and Performance Tool package.</span></span> <span data-ttu-id="d200f-114">Assicurarsi che il programma di installazione del pacchetto (CapacityPlanningTool. msi) sia stato eseguito nel front end server o nel server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d200f-114">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server.</span></span> <span data-ttu-id="d200f-115">Avviare lo strumento di provisioning degli utenti di Lync Server eseguendo il file UserProvisioningTool. exe, che si trova in\\% InstalledDirectory% LyncStressAndPerfTool LyncStress, nel front end server o nel server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d200f-115">Start the Lync Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d200f-116">Per poter eseguire UserProvisioningTool. exe, è necessario essere connessi come membri del gruppo di sicurezza Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="d200f-116">You must be logged on as a member of the Domain Admins security group in order to run UserProvisioningTool.exe.</span></span> <span data-ttu-id="d200f-117">È necessario eseguire da questo contesto perché UserProvisioningTool. exe sarà la creazione e la configurazione di nuovi utenti di servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d200f-117">It is necessary to run from this context because UserProvisioningTool.exe will be creating and configuring new Active Directory Domain Services users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d200f-118">Quando si crea un numero significativo di utenti (10.000 o più), eseguire UserProvisioningTool. exe da un computer high-end.</span><span class="sxs-lookup"><span data-stu-id="d200f-118">When you create a significant number of users (10,000 or more), run UserProvisioningTool.exe from a high-end computer.</span></span> <span data-ttu-id="d200f-119">Si noti che il controller di dominio verificherà un carico elevato anche durante la creazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="d200f-119">Note that the domain controller will also experience high load while the users are being created.</span></span>



</div>

<span data-ttu-id="d200f-120">Quando si apre lo strumento di provisioning dell'utente di Lync Server, fare clic su **configurazione** e selezionare **Carica configurazione**.</span><span class="sxs-lookup"><span data-stu-id="d200f-120">When the Lync Server User Provisioning Tool opens, click **Configuration** and select **Load Configuration**.</span></span> <span data-ttu-id="d200f-121">Per iniziare a configurare utenti e contatti, caricare il file predefinito incluso nel pacchetto SampleData. XML.</span><span class="sxs-lookup"><span data-stu-id="d200f-121">To begin configuring users and contacts, load the default file that is included in the package, SampleData.xml.</span></span> <span data-ttu-id="d200f-122">Verranno precompilati i campi con i dati di esempio che dovranno essere rielaborati per il sistema.</span><span class="sxs-lookup"><span data-stu-id="d200f-122">This will prepopulate the fields with example data that you'll need to revise for your system.</span></span> <span data-ttu-id="d200f-123">Se si dispone di un file XML preconfigurato che già contiene impostazioni personalizzate, caricare il file.</span><span class="sxs-lookup"><span data-stu-id="d200f-123">If you have a preconfigured XML file that already contains customized settings, load that file instead.</span></span> <span data-ttu-id="d200f-124">Compilare i campi dello strumento di provisioning degli utenti di Lync Server, come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d200f-124">Fill in the fields in the Lync Server User Provisioning Tool, as described in the following sections.</span></span>

<span data-ttu-id="d200f-125">![Scheda Creazione utente.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "Scheda Creazione utente.")</span><span class="sxs-lookup"><span data-stu-id="d200f-125">![User Creation tab.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "User Creation tab.")</span></span>

<span data-ttu-id="d200f-126">Per configurare le opzioni del server, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="d200f-126">To configure server options, follow these steps.</span></span>

1.  <span data-ttu-id="d200f-127">Nell' **FQDN del pool Front End**Digitare il nome di dominio completo (FQDN) del server Standard Edition o del pool Front end in cui si desidera ospitare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d200f-127">In **Front End Pool FQDN**, type the fully qualified domain name (FQDN) of the Standard Edition server or Front End pool where you want to host the users.</span></span>

2.  <span data-ttu-id="d200f-128">In **prefisso nome utente**Digitare un prefisso che si desidera utilizzare per creare i nomi utente a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="d200f-128">In **User Name Prefix**, type a prefix that you want to use to build user names for testing purposes.</span></span>

3.  <span data-ttu-id="d200f-129">In **password**specificare una password che verrà applicata a tutti gli account utente di test.</span><span class="sxs-lookup"><span data-stu-id="d200f-129">In **Password**, specify a password that will be applied for all of the test user accounts.</span></span>

4.  <span data-ttu-id="d200f-130">Nel **dominio SIP**, digitare il nome di dominio da utilizzare per gli URI SIP degli utenti di test (Uniform Resource Identifiers).</span><span class="sxs-lookup"><span data-stu-id="d200f-130">In **SIP Domain**, type the domain name to be used for test users’ SIP URIs (Uniform Resource Identifiers).</span></span>

5.  <span data-ttu-id="d200f-131">In **dominio account**Digitare il nome di dominio del dominio di servizi di dominio Active Directory corrente, in cui si desidera creare gli utenti di test.</span><span class="sxs-lookup"><span data-stu-id="d200f-131">In **Account Domain**, type the domain name of your current Active Directory Domain Services domain, under which you want to create the test users.</span></span>

6.  <span data-ttu-id="d200f-132">In **unità organizzativa**, digitare il nome dell'unità organizzativa di servizi di dominio Active Directory in cui si desidera creare gli oggetti utente.</span><span class="sxs-lookup"><span data-stu-id="d200f-132">In **Organizational Unit**, type the name of the Active Directory Domain Services OU where you want to create the User objects.</span></span> <span data-ttu-id="d200f-133">Se l'unità organizzativa non esiste, verrà creata.</span><span class="sxs-lookup"><span data-stu-id="d200f-133">If the OU does not exist, it will be created.</span></span>

7.  <span data-ttu-id="d200f-134">In **codice area telefono**Digitare il codice area a tre cifre che verrà utilizzato per gli account utente di test.</span><span class="sxs-lookup"><span data-stu-id="d200f-134">In **Phone Area Code**, type the three-digit area code that will be used for test user accounts.</span></span> <span data-ttu-id="d200f-135">Assicurarsi che il codice area telefono non sia in conflitto con i codici di area di altri utenti in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d200f-135">Be sure that phone area code does not conflict with any other users’ area codes in Active Directory Domain Services.</span></span>

8.  <span data-ttu-id="d200f-136">Selezionare la casella di controllo **abilitata** per la voce se si desidera abilitare gli utenti di test per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="d200f-136">Select the **Voice Enabled** check box if you want to enable the test users for Enterprise Voice.</span></span>

9.  <span data-ttu-id="d200f-137">In **numero di utenti**specificare il numero totale di utenti di test che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="d200f-137">In **Number of Users**, specify the total number of test users that you want to create.</span></span>

10. <span data-ttu-id="d200f-138">In **Start index**specificare il numero iniziale che verrà utilizzato come suffisso per il prefisso del nome utente.</span><span class="sxs-lookup"><span data-stu-id="d200f-138">In **Start Index**, specify the starting number that will be used as suffix to the user name prefix.</span></span>

<div>

## <a name="create-users-button"></a><span data-ttu-id="d200f-139">Pulsante Crea utenti</span><span class="sxs-lookup"><span data-stu-id="d200f-139">Create Users Button</span></span>

<span data-ttu-id="d200f-140">Quando si fa clic sul pulsante Crea utenti, verranno convalidati tutti i parametri di input.</span><span class="sxs-lookup"><span data-stu-id="d200f-140">When you click on the Create Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="d200f-141">Se si verificano errori di convalida, viene richiesto di correggere tali valori di input.</span><span class="sxs-lookup"><span data-stu-id="d200f-141">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="d200f-142">Se tutti i valori di input sono corretti, verrà avviata la creazione di utenti in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d200f-142">If all the input values are correct, it will start creating users in Active Directory Domain Services.</span></span> <span data-ttu-id="d200f-143">La barra di avanzamento verrà visualizzata nella parte inferiore del modulo.</span><span class="sxs-lookup"><span data-stu-id="d200f-143">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="d200f-144">Si consiglia di non chiudere l'applicazione mentre la barra di stato è attiva.</span><span class="sxs-lookup"><span data-stu-id="d200f-144">We recommend that you do not close the application while the progress bar is active.</span></span>

<span data-ttu-id="d200f-145">La creazione di un utente è una procedura lenta.</span><span class="sxs-lookup"><span data-stu-id="d200f-145">User Creation is a slow process.</span></span> <span data-ttu-id="d200f-146">Possono essere necessari alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="d200f-146">It can take several minutes.</span></span> <span data-ttu-id="d200f-147">Se il numero di utenti è molto grande, il processo potrebbe richiedere anche alcune ore.</span><span class="sxs-lookup"><span data-stu-id="d200f-147">If the number of users is very large, the process could even take a few hours.</span></span> <span data-ttu-id="d200f-148">Se gli utenti sono già presenti, vengono aggiornati con le modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="d200f-148">If the users already exist, they are updated with any changes.</span></span> <span data-ttu-id="d200f-149">È possibile verificare che gli utenti siano stati creati accedendo come uno degli utenti nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="d200f-149">You can validate that the users were created by logging on as one of the users in the range.</span></span> <span data-ttu-id="d200f-150">Utilizzare il prefisso utente, il numero di utente e il @sipDomain come nome utente (ad esempio, LyncUser10@contoso.net), insieme alla password specificata.</span><span class="sxs-lookup"><span data-stu-id="d200f-150">Use the user prefix, user number, and @sipDomain as the user name (for example, LyncUser10@contoso.net), along with the specified password.</span></span>

</div>

<div>

## <a name="delete-users-button"></a><span data-ttu-id="d200f-151">Pulsante Elimina utenti</span><span class="sxs-lookup"><span data-stu-id="d200f-151">Delete Users Button</span></span>

<span data-ttu-id="d200f-152">Quando si fa clic sul pulsante Elimina utenti, verranno convalidati tutti i parametri di input.</span><span class="sxs-lookup"><span data-stu-id="d200f-152">When you click on Delete Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="d200f-153">Se si verificano errori di convalida, viene richiesto di correggere tali valori di input.</span><span class="sxs-lookup"><span data-stu-id="d200f-153">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="d200f-154">Se tutti i valori di input sono corretti, inizierà a disabilitare ed eliminare gli utenti in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d200f-154">If all the input values are correct, it will start disabling and deleting users in Active Directory Domain Services.</span></span> <span data-ttu-id="d200f-155">La barra di avanzamento verrà visualizzata nella parte inferiore del modulo.</span><span class="sxs-lookup"><span data-stu-id="d200f-155">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="d200f-156">Si consiglia di non chiudere l'applicazione mentre la barra di stato è attiva.</span><span class="sxs-lookup"><span data-stu-id="d200f-156">We recommend that you do not close the application while the progress bar is active.</span></span>

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P><span data-ttu-id="d200f-157">Sono supportati solo i numeri di telefono formattati negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="d200f-157">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="d200f-158">I numeri di telefono vengono sempre assegnati agli utenti e tutti gli utenti creati da UserProvisioningTool. exe sono abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="d200f-158">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice.</span></span> <span data-ttu-id="d200f-159">Tutti gli scenari che utilizzano il numero di telefono, ad esempio l'operatore automatico di conferenza o le chiamate di UC-PSTN, utilizzano questo numero di telefono per instradare correttamente le chiamate.</span><span class="sxs-lookup"><span data-stu-id="d200f-159">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="d200f-160">Per questo motivo, ogni utente deve disporre di un numero di telefono univoco.</span><span class="sxs-lookup"><span data-stu-id="d200f-160">For this reason, every user must have a unique phone number.</span></span> <span data-ttu-id="d200f-161">Se è necessario creare due volte gli utenti, il comando avrà esito negativo a meno che non si utilizzi un codice area diverso o se gli utenti precedenti sono stati disabilitati utilizzando il cmdlet <STRONG>Disable-CsUser</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="d200f-161">If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the <STRONG>Disable-CsUser</STRONG> cmdlet.</span></span></P>
> <LI>
> <P><span data-ttu-id="d200f-162">Prima di creare contatti, è necessario prima completare la replica utente, eseguita dalla scheda utenti. Se gli utenti sono stati appena creati, è necessario attendere il completamento della replica di Lync Server e la compilazione degli account utente nel database.</span><span class="sxs-lookup"><span data-stu-id="d200f-162">Before you create contacts, you must first complete user replication, performed from the Users tab. If you have just created your users, you must wait until Lync Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="d200f-163">Se gli utenti non hanno completato la replica, verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="d200f-163">If the users have not finished replicating, you will see an error.</span></span> <span data-ttu-id="d200f-164">È possibile sapere quando gli utenti hanno finito di replicare se Lync Server 2013 front end Service è stato avviato o se il cmdlet <STRONG>Get-CsUser</STRONG> è stato eseguito correttamente nell'ultimo utente.</span><span class="sxs-lookup"><span data-stu-id="d200f-164">You will know when users have finished replicating if Lync Server 2013 Front End service has started, or by successfully running the <STRONG>Get-CsUser</STRONG> cmdlet on the last user.</span></span></P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a><span data-ttu-id="d200f-165">Scheda creazione contatti</span><span class="sxs-lookup"><span data-stu-id="d200f-165">Contacts Creation Tab</span></span>

<span data-ttu-id="d200f-166">La scheda creazione contatti consente di specificare i dettagli per i contatti degli utenti.</span><span class="sxs-lookup"><span data-stu-id="d200f-166">The Contacts Creation tab enables you to specify details for users’ contacts.</span></span>

<span data-ttu-id="d200f-167">![Scheda creazione contatti.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Scheda creazione contatti.")</span><span class="sxs-lookup"><span data-stu-id="d200f-167">![Contacts Creation tab.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Contacts Creation tab.")</span></span>

<span data-ttu-id="d200f-168">Per configurare i contatti degli utenti, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="d200f-168">To configure users’ contacts, follow these steps.</span></span>

1.  <span data-ttu-id="d200f-169">In media contatti per utente, specificare il numero medio di contatti da popolare negli elenchi di contatti per ciascuno degli utenti.</span><span class="sxs-lookup"><span data-stu-id="d200f-169">In Average Contacts per User, specify the average number of contacts to populate in contact lists for each of the users.</span></span>

2.  <span data-ttu-id="d200f-170">Selezionare la casella di controllo fisso se si desidera creare un numero uguale di contatti per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="d200f-170">Select the Fixed check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="d200f-171">Se si desidera variare il numero di contatti creati per gli utenti, deselezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="d200f-171">If you want to vary the number of contacts created for users, clear the check box.</span></span>

3.  <span data-ttu-id="d200f-172">In media gruppi di contatti per utente, specificare il numero di gruppi di contatti per utente.</span><span class="sxs-lookup"><span data-stu-id="d200f-172">In Average Contact Groups per User, specify the number of contact groups per user.</span></span> <span data-ttu-id="d200f-173">Questo numero deve essere inferiore ai contatti medi per utente.</span><span class="sxs-lookup"><span data-stu-id="d200f-173">This number must be smaller than Average Contacts per User.</span></span>

4.  <span data-ttu-id="d200f-174">Nella percentuale contatti federati/pool incrociato specificare un numero compreso tra 0 e 100.</span><span class="sxs-lookup"><span data-stu-id="d200f-174">In Federated / Cross Pool Contacts Percentage, specify a number between 0 and 100.</span></span> <span data-ttu-id="d200f-175">Questa percentuale di contatti verrà creata con gli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="d200f-175">This percentage of contacts will be created with the federated users.</span></span>

5.  <span data-ttu-id="d200f-176">In prefisso utente federativo/pool incrociato specificare il nome utente per gli utenti federati che verranno aggiunti agli elenchi di contatti degli utenti locali.</span><span class="sxs-lookup"><span data-stu-id="d200f-176">In Federated / Cross Pool User Prefix, specify the username for federated users that will be added to the contact lists of local users.</span></span>

6.  <span data-ttu-id="d200f-177">Nel dominio SIP dell'utente federata o di pool incrociato specificare il nome di dominio SIP degli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="d200f-177">In Federated / Cross Pool User SIP Domain, specify the SIP Domain Name of the federated users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d200f-178">Nessuno degli utenti deve essere connesso quando si creano contatti.</span><span class="sxs-lookup"><span data-stu-id="d200f-178">None of the users should be signed in when creating contacts.</span></span>

    
    </div>

7.  <span data-ttu-id="d200f-179">Nella scheda Creazione utente, verificare che i parametri siano corretti.</span><span class="sxs-lookup"><span data-stu-id="d200f-179">In User Creation tab, verify that the parameters are correct.</span></span> <span data-ttu-id="d200f-180">L'intervallo di utenti per il quale verranno creati i contatti viene ottenuto dalla scheda Creazione utente.</span><span class="sxs-lookup"><span data-stu-id="d200f-180">The range of users for which contacts will be created is obtained from the User Creation tab.</span></span>

8.  <span data-ttu-id="d200f-181">Fare clic su Crea contatti per iniziare la creazione dei contatti.</span><span class="sxs-lookup"><span data-stu-id="d200f-181">Click Create Contacts to begin the contact creation.</span></span> <span data-ttu-id="d200f-182">Questo processo può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="d200f-182">This process can take several minutes.</span></span> <span data-ttu-id="d200f-183">Al termine dell'operazione, verrà visualizzata una finestra di dialogo con il messaggio "Operation completed successfully".</span><span class="sxs-lookup"><span data-stu-id="d200f-183">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="d200f-184">È possibile convalidare i contatti creati accedendo come utente creato dalla scheda Creazione utente.</span><span class="sxs-lookup"><span data-stu-id="d200f-184">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d200f-185">Dopo la creazione dei contatti, questo strumento riavvierà tutti i Front End Server nel pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d200f-185">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="d200f-186">Potrebbe essere necessario più tempo (fino a 2 ore) per l'avvio dei Front End Server, a seconda del numero di contatti creati dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="d200f-186">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span>

    
    </div>

</div>

<div>

## <a name="distribution-list"></a><span data-ttu-id="d200f-187">Lista di distribuzione</span><span class="sxs-lookup"><span data-stu-id="d200f-187">Distribution List</span></span>

<span data-ttu-id="d200f-188">Una delle caratteristiche dello strumento di sviluppo dello stress e delle prestazioni di Lync Server 2013 è quella di simulare la funzionalità di espansione della lista di distribuzione (DL) in Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d200f-188">One of the features of the Lync Server 2013 Stress and Performance Tool is to simulate the distribution list (DL) expansion feature in Lync 2013.</span></span> <span data-ttu-id="d200f-189">Se non si intende abilitare l'espansione DL in UserProvisioningTool, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="d200f-189">If you are not going to enable DL expansion in UserProvisioningTool, you can skip this step.</span></span>

<span data-ttu-id="d200f-190">![Scheda Creazione elenco di distribuzione.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Scheda Creazione elenco di distribuzione.")</span><span class="sxs-lookup"><span data-stu-id="d200f-190">![Distribution List Creation tab.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Distribution List Creation tab.")</span></span>

<span data-ttu-id="d200f-191">La scheda della lista di distribuzione consente di creare un DLs che lo strumento di stress e prestazioni utilizzerà per la funzionalità di espansione della lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d200f-191">The Distribution List tab enables you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="d200f-192">Prima di creare DLs, è necessario che Lync Server 2013 sia già installato.</span><span class="sxs-lookup"><span data-stu-id="d200f-192">Prior to creating DLs, Lync Server 2013 must already be installed.</span></span> <span data-ttu-id="d200f-193">È necessario aver eseguito Lync Server 2013 ForestPrep.</span><span class="sxs-lookup"><span data-stu-id="d200f-193">You must have run Lync Server 2013 ForestPrep.</span></span> <span data-ttu-id="d200f-194">In caso contrario, gli attributi DL non sono presenti nello schema dei servizi di dominio Active Directory e lo strumento non sarà in grado di creare DLs.</span><span class="sxs-lookup"><span data-stu-id="d200f-194">Otherwise, the DL attributes do not exist in the Active Directory Domain Services schema and the tool will not be able to create DLs.</span></span>

<span data-ttu-id="d200f-195">Per configurare le liste di distribuzione, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="d200f-195">To configure distribution lists, follow these steps.</span></span>

1.  <span data-ttu-id="d200f-196">In numero di liste di distribuzione specificare il numero totale di DLs che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="d200f-196">In Number of Distribution Lists, specify the total number of DLs that you want to create.</span></span> <span data-ttu-id="d200f-197">(Si consiglia di iniziare con il doppio del numero di utenti).</span><span class="sxs-lookup"><span data-stu-id="d200f-197">(We recommend that you start with twice the number of users).</span></span> <span data-ttu-id="d200f-198">Sono numerati da 0 a n-1.</span><span class="sxs-lookup"><span data-stu-id="d200f-198">They are numbered from 0 to n-1.</span></span>

2.  <span data-ttu-id="d200f-199">Nel prefisso della lista di distribuzione, specificare il prefisso che avrà il DLs.</span><span class="sxs-lookup"><span data-stu-id="d200f-199">In Distribution List Prefix, specify the prefix that the DLs will have.</span></span> <span data-ttu-id="d200f-200">Ad esempio, se si specifica 100 DLs e un prefisso di testDL, il DLs sarà denominato testDL0, testDL1 e così via, tramite testDL99.</span><span class="sxs-lookup"><span data-stu-id="d200f-200">For example if you specify 100 DLs and a prefix of testDL, the DLs will be named testDL0, testDL1, and so on, through testDL99.</span></span>

3.  <span data-ttu-id="d200f-201">Nei membri minimi di un elenco dist specificare il numero minimo di utenti da aggiungere in ogni lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d200f-201">In Minimum Members in a Dist. List, specify the minimum number of users to add in each Distribution List.</span></span>

4.  <span data-ttu-id="d200f-202">Nei membri massimi di un elenco di dist. specificare il numero massimo di utenti da aggiungere in ogni lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d200f-202">In Maximum Members in a Dist. List, specify the maximum number of users to add in each Distribution List.</span></span>

<div>

## <a name="create-distribution-lists-button"></a><span data-ttu-id="d200f-203">Pulsante Crea liste di distribuzione</span><span class="sxs-lookup"><span data-stu-id="d200f-203">Create Distribution Lists Button</span></span>

<span data-ttu-id="d200f-204">Quando si fa clic sul pulsante Crea liste di distribuzione, lo strumento esegue una query nei servizi di dominio Active Directory per verificare se sono già presenti liste di distribuzione corrispondenti al prefisso e ai numeri.</span><span class="sxs-lookup"><span data-stu-id="d200f-204">When you click the Create Distribution Lists button, the tool queries Active Directory Domain Services to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="d200f-205">Lo strumento creerà solo quelli che non esistono già.</span><span class="sxs-lookup"><span data-stu-id="d200f-205">The tool will create only the ones that do not already exist.</span></span> <span data-ttu-id="d200f-206">Quando si aggiungono membri a queste liste di distribuzione appena create, verranno scelti gli utenti dall'intervallo specificato nella scheda Creazione utente.</span><span class="sxs-lookup"><span data-stu-id="d200f-206">When adding members to these newly created Distribution Lists, it will pick the users from the range specified on the User Creation tab.</span></span>

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a><span data-ttu-id="d200f-207">Scheda configurazione del servizio informazioni percorso</span><span class="sxs-lookup"><span data-stu-id="d200f-207">Location Info Service Config Tab</span></span>

<span data-ttu-id="d200f-208">Una delle caratteristiche dello strumento Lync Server 2013 stress and performance è quella di generare file di configurazione fittizi per il servizio informazioni percorso.</span><span class="sxs-lookup"><span data-stu-id="d200f-208">One of the features of the Lync Server 2013 Stress and Performance Tool is to generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="d200f-209">Il servizio informazioni percorso in genere non ha un impatto significativo sulle prestazioni nei server.</span><span class="sxs-lookup"><span data-stu-id="d200f-209">The Location Information Service typically does not have any significant performance impact on the servers.</span></span>

<span data-ttu-id="d200f-210">![Scheda configurazione del servizio informazioni percorso.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Scheda configurazione del servizio informazioni percorso.")</span><span class="sxs-lookup"><span data-stu-id="d200f-210">![Location Info Service Config tab.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Location Info Service Config tab.")</span></span>

<span data-ttu-id="d200f-211">Se si sceglie di verificare questa funzionalità, è possibile inserire i valori indicati nel modulo e quindi fare clic sul pulsante genera file di configurazione LIS.</span><span class="sxs-lookup"><span data-stu-id="d200f-211">If you choose to test this feature, you can fill in the values mentioned in the form and then click the Generate LIS Config Files button.</span></span> <span data-ttu-id="d200f-212">Genererà file CSV denominati\_LIS subnet. csv,\_LIS switches. csv\_, LIS Ports. csv\_e LIS WAP. csv.</span><span class="sxs-lookup"><span data-stu-id="d200f-212">It will generate CSV files called LIS\_Subnet.csv, LIS\_Switches.csv, LIS\_Ports.csv, and LIS\_WAP.csv.</span></span> <span data-ttu-id="d200f-213">È quindi possibile importare questi file CSV nel database LIS utilizzando il cmdlet **Set-CsLisSubnet** , il cmdlet **Set-CsLisSwitch** , il cmdlet **Set-CsLisPort** e il cmdlet **set-CsWirelessAccessPoint** , rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="d200f-213">You can then import these CSV files into LIS database by using the **Set-CsLisSubnet** cmdlet, the **Set-CsLisSwitch** cmdlet, the **Set-CsLisPort** cmdlet, and the **Set-CsWirelessAccessPoint** cmdlet, respectively.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

