---
title: Distribuire il portale Web amministrativo di SRS V1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Il portale Web di amministrazione di Skype for Business Server Skype (SRS V1, precedentemente noto come Lync room System) è un portale Web che può essere utilizzato dalle organizzazioni per gestire le sale conferenze dei sistemi in sala Skype. Gli amministratori possono utilizzare il portale Web amministrativo di SRS V1 per monitorare l'integrità del dispositivo, ad esempio monitorando i dispositivi audio/video. Con questo portale, gli amministratori possono raccogliere informazioni diagnostiche in remoto per monitorare l'integrità della sala riunioni.
ms.openlocfilehash: 7d7bef99149d09ebf72c9b633370f262e535b23f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804536"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="5defa-105">Distribuire il portale Web amministrativo di SRS V1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5defa-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="5defa-106">Il portale Web di amministrazione di Skype for Business Server Skype (SRS V1, precedentemente noto come Lync room System) è un portale Web che può essere utilizzato dalle organizzazioni per gestire le sale conferenze dei sistemi in sala Skype.</span><span class="sxs-lookup"><span data-stu-id="5defa-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="5defa-107">Gli amministratori possono utilizzare il portale Web amministrativo di SRS V1 per monitorare l'integrità del dispositivo, ad esempio monitorando i dispositivi audio/video.</span><span class="sxs-lookup"><span data-stu-id="5defa-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="5defa-108">Con questo portale, gli amministratori possono raccogliere informazioni diagnostiche in remoto per monitorare l'integrità della sala riunioni.</span><span class="sxs-lookup"><span data-stu-id="5defa-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="5defa-109">Per utilizzare questa funzionalità, è necessario distribuire il portale Web amministrativo SRS V1 su tutti i server front end di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5defa-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="5defa-110">In questa guida vengono fornite istruzioni per gli amministratori su come installare e configurare il portale Web amministrativo SRS.</span><span class="sxs-lookup"><span data-stu-id="5defa-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="5defa-111">È destinato agli amministratori che dispongono della conoscenza dell'amministrazione di Skype for Business Server e che dispongono di diritti utente di amministratore per modificare la topologia di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5defa-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="5defa-112">Dopo che il portale Web amministrativo SRS V1 è stato distribuito sul server, gli amministratori possono controllare i dispositivi SRS V1 di stato accedendo al sito dai propri computer o laptop.</span><span class="sxs-lookup"><span data-stu-id="5defa-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5defa-113">Scaricare il [portale Web amministrativo per Skype for Business Server 2015 di Microsoft Skype room Systems V1](https://www.microsoft.com/download/details.aspx?id=46906).</span><span class="sxs-lookup"><span data-stu-id="5defa-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="5defa-114">Contenuto dell'argomento:</span><span class="sxs-lookup"><span data-stu-id="5defa-114">In this topic:</span></span>

- [<span data-ttu-id="5defa-115">Configurare l'ambiente per il portale Web amministrativo di SRS V1</span><span class="sxs-lookup"><span data-stu-id="5defa-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="5defa-116">Installare il portale Web amministrativo di SRS V1</span><span class="sxs-lookup"><span data-stu-id="5defa-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="5defa-117">Utilizzare il portale Web amministrativo SRS</span><span class="sxs-lookup"><span data-stu-id="5defa-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="5defa-118">Configurare l'ambiente per il portale Web amministrativo di SRS V1</span><span class="sxs-lookup"><span data-stu-id="5defa-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="5defa-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="5defa-119"><a name="Config_Env"> </a></span></span>

<span data-ttu-id="5defa-120">Per utilizzare il portale Web amministrativo SRS V1, è necessario installare o configurare i prerequisiti seguenti.</span><span class="sxs-lookup"><span data-stu-id="5defa-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5defa-121">Se il server è configurato con l'autenticazione Kerberos e NTLM e l'interfaccia SRS è in esecuzione in un computer che non è stato aggiunto al dominio, l'autenticazione Kerberos avrà esito negativo e l'utente non visualizzerà lo stato del servizio SRS nel portale amministrativo.</span><span class="sxs-lookup"><span data-stu-id="5defa-121">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal.</span></span> <span data-ttu-id="5defa-122">Per risolvere il problema, configurare il server con l'autenticazione NTLM o sia l'autenticazione NTLM che TLS-DSK (senza Kerberos) oppure aggiungere il computer SRS al dominio.</span><span class="sxs-lookup"><span data-stu-id="5defa-122">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="5defa-123">Installare gli aggiornamenti cumulativi di Skype for Business Server nella topologia di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5defa-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="5defa-124">Per ottenere l'aggiornamento o vedere cosa è incluso in esso, vedere [Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="5defa-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="5defa-125">Creare un utente di Active Directory abilitato per SIP.</span><span class="sxs-lookup"><span data-stu-id="5defa-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="5defa-126">Il portale Web amministrativo SRS V1 utilizza queste credenziali per eseguire query su informazioni da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5defa-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="5defa-127">Il nome utente negli esempi specificati è LRSApp.</span><span class="sxs-lookup"><span data-stu-id="5defa-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="5defa-128">Creare un gruppo di sicurezza di Active Directory con nome LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="5defa-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="5defa-129">Creare il gruppo con ambito gruppo come globale e come tipo di gruppo come protezione.</span><span class="sxs-lookup"><span data-stu-id="5defa-129">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="5defa-130">Gli utenti abilitati per SIP che sono stati aggiunti a questo gruppo saranno autorizzati a visualizzare l'elenco delle sale ed eseguire alcuni comandi, ad esempio la raccolta di registri.</span><span class="sxs-lookup"><span data-stu-id="5defa-130">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="5defa-131">Creare un gruppo di sicurezza di Active Directory con nome LRSFullAccessAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="5defa-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="5defa-132">Creare il gruppo con ambito gruppo come globale e come tipo di gruppo come protezione. gli utenti abilitati per SIP aggiunti a questo gruppo sono autorizzati a utilizzare tutte le funzionalità del portale di amministrazione in una singola sala Skype.</span><span class="sxs-lookup"><span data-stu-id="5defa-132">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room.</span></span> <span data-ttu-id="5defa-133">Per includere il supporto per la gestione in blocco delle sale Skype, fare riferimento al passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="5defa-133">To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![Elenco dei gruppi di amministratori con il ruolo di gruppo di sicurezza](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="5defa-135">Creare un gruppo di sicurezza di Active Directory con nome LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="5defa-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="5defa-136">Creare il gruppo con ambito gruppo come globale e come tipo di gruppo come protezione.</span><span class="sxs-lookup"><span data-stu-id="5defa-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="5defa-137">Gli utenti abilitati al SIP che sono stati aggiunti a questo gruppo sono autorizzati a utilizzare tutte le funzionalità del portale di amministrazione, inclusa la gestione in blocco delle sale di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="5defa-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="5defa-138">Aggiungere LRSFullAccessAdminGroup come membro di LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="5defa-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![Pagina membri proprietà LRSSupportAdminGroup](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="5defa-140">Creare un utente di Active Directory SIP abilitato con nome LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="5defa-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="5defa-141">Aggiungere l'utente a LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="5defa-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![Pagina membri proprietà LRSSupportAdminGroup](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="5defa-143">Installare [ASP.NET MVC 4 per Visual Studio 2010 SP1 e Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span><span class="sxs-lookup"><span data-stu-id="5defa-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="5defa-144">Installare il portale Web amministrativo di SRS V1</span><span class="sxs-lookup"><span data-stu-id="5defa-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="5defa-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="5defa-145"><a name="Install_SRS"> </a></span></span>

<span data-ttu-id="5defa-146">Scaricare il [portale Web amministrativo per Skype for Business Server 2015 di Microsoft Skype room Systems V1](https://www.microsoft.com/download/details.aspx?id=46906).</span><span class="sxs-lookup"><span data-stu-id="5defa-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="5defa-147">Per installare il portale Web amministrativo di SRS V1, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="5defa-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="5defa-148">Configurare la porta dell'applicazione attendibile eseguendo il cmdlet seguente in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="5defa-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="5defa-149">Per installare il portale della sala riunioni, scaricare **MeetingRoomPortalInstaller.msi** e quindi eseguirlo come amministratore.</span><span class="sxs-lookup"><span data-stu-id="5defa-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="5defa-150">Aprire il file Web.config dal percorso seguente:</span><span class="sxs-lookup"><span data-stu-id="5defa-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="5defa-151">% Program Files%\Skype for Business Server 2015 \ Web Components\Meeting room Portal\Int\Handler</span><span class="sxs-lookup"><span data-stu-id="5defa-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span></span>\

4. <span data-ttu-id="5defa-152">Nel file Web.Config cambiare PortalUserName con il nome utente creato nel passaggio 2 sotto la sezione "[Configure your environment for the SRS V1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (il nome consigliato nel passaggio è LRSApp):</span><span class="sxs-lookup"><span data-stu-id="5defa-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="5defa-153">Poiché il portale di amministrazione di SRS V1 è un'applicazione attendibile, non è necessario fornire la password nella configurazione del portale.</span><span class="sxs-lookup"><span data-stu-id="5defa-153">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="5defa-154">Se l'utente utilizza un registrar diverso da quello locale, è necessario specificare il registrar per il servizio di registrazione aggiungendo la riga seguente nel file Web.Config:</span><span class="sxs-lookup"><span data-stu-id="5defa-154">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="5defa-155">Se la porta utilizzata è diversa da 5061, aggiungere la riga seguente nel file Web.Config:</span><span class="sxs-lookup"><span data-stu-id="5defa-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="5defa-156">Verificare l'installazione del portale Web amministrativo di SRS</span><span class="sxs-lookup"><span data-stu-id="5defa-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="5defa-157">Per verificare l'installazione del portale Web amministrativo di SRS V1, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5defa-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="5defa-158">In un front end Server passare all'URL seguente:</span><span class="sxs-lookup"><span data-stu-id="5defa-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="5defa-159">https:// \<fe-server\> /LRS</span><span class="sxs-lookup"><span data-stu-id="5defa-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="5defa-160">Non è possibile visualizzare errori, come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="5defa-160">You should not see any errors, as shown in the following image:</span></span>

     ![Schermata di accesso al portale di amministrazione di Lync room System](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="5defa-162">Se non vengono visualizzati errori, provare a accedere all'URL seguente da qualsiasi altro computer della topologia:</span><span class="sxs-lookup"><span data-stu-id="5defa-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="5defa-163">https:// \<fe-server\> /LRS</span><span class="sxs-lookup"><span data-stu-id="5defa-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="5defa-164">Per accedere alla pagina, sarà necessario aggiungere i record DNS come descritto in "[record DNS necessari per](https://go.microsoft.com/fwlink/p/?LinkId=318056)l'accesso automatico dei client".</span><span class="sxs-lookup"><span data-stu-id="5defa-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="5defa-165">Utilizzare il portale Web amministrativo SRS</span><span class="sxs-lookup"><span data-stu-id="5defa-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="5defa-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="5defa-166"><a name="Use_Portal"> </a></span></span>

<span data-ttu-id="5defa-167">Dopo aver distribuito il servizio SRS nel server, è possibile controllare lo stato di tutte le stanze SRS accedendo al portale Web amministrativo SRS V1 da un browser.</span><span class="sxs-lookup"><span data-stu-id="5defa-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="5defa-168">Accesso</span><span class="sxs-lookup"><span data-stu-id="5defa-168">Sign in</span></span>

1. <span data-ttu-id="5defa-169">Passare all'URL seguente:</span><span class="sxs-lookup"><span data-stu-id="5defa-169">Browse to the following URL:</span></span>

    <span data-ttu-id="5defa-170">https:// \<fe-server\> /LRS</span><span class="sxs-lookup"><span data-stu-id="5defa-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="5defa-171">Immettere le credenziali per l'account di LRSSupport o un account aggiunto al gruppo di sicurezza di LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="5defa-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Schermata di accesso al portale di amministrazione di Lync room System](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="5defa-173">Pagina di riepilogo del portale Web amministrativo SRS</span><span class="sxs-lookup"><span data-stu-id="5defa-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="5defa-174">Nella pagina Riepilogo sono disponibili le informazioni seguenti per tutte le stanze SRS distribuite nel server:</span><span class="sxs-lookup"><span data-stu-id="5defa-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="5defa-175">**Tag** Nome personalizzato che viene fornito dall'amministratore per la sala.</span><span class="sxs-lookup"><span data-stu-id="5defa-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="5defa-176">Il tag può essere impostato nel portale facendo clic sul nome della sala.</span><span class="sxs-lookup"><span data-stu-id="5defa-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="5defa-177">**Integrità** Lo stato di integrità della sala, che deriva dallo stato di integrità di aggregazione della sala, visualizzata nella sezione integrità della pagina impostazioni sala.</span><span class="sxs-lookup"><span data-stu-id="5defa-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="5defa-178">**Prossima riunione** Data e ora in cui viene pianificata la riunione successiva.</span><span class="sxs-lookup"><span data-stu-id="5defa-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="5defa-179">**Versione SRS, produttore, modello** Questi valori sono preimpostati in SRS.</span><span class="sxs-lookup"><span data-stu-id="5defa-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="5defa-180">A seconda del produttore, questi campi potrebbero essere lasciati vuoti.</span><span class="sxs-lookup"><span data-stu-id="5defa-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="5defa-181">**Ultimo aggiornamento** Visualizza l'ultima volta che la pagina Web è stata aggiornata.</span><span class="sxs-lookup"><span data-stu-id="5defa-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Visualizzazione di riepilogo del portale di amministrazione di Lync room System](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="5defa-183">Se si fa parte del gruppo di sicurezza di LRSPowerUserAdminsGroup, verrà visualizzato solo il menu gestione in blocco.</span><span class="sxs-lookup"><span data-stu-id="5defa-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="5defa-184">Informazioni sulla sala SRS</span><span class="sxs-lookup"><span data-stu-id="5defa-184">SRS Room Information</span></span>

<span data-ttu-id="5defa-185">La sezione informazioni sala del portale consente di visualizzare e configurare le singole stanze SRS.</span><span class="sxs-lookup"><span data-stu-id="5defa-185">The Room Info section of the portal allows you to view and configure individual SRS rooms.</span></span> <span data-ttu-id="5defa-186">Contiene quattro sezioni: impostazioni, dettagli, registrazione e integrità.</span><span class="sxs-lookup"><span data-stu-id="5defa-186">It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="5defa-187">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="5defa-187">Settings</span></span>

<span data-ttu-id="5defa-188">Nella sezione impostazioni è possibile impostare la password, il tag sala e i livelli di volume predefiniti per la sala.</span><span class="sxs-lookup"><span data-stu-id="5defa-188">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="5defa-189">Se si configurano queste impostazioni, le modifiche vengono replicate solo dopo aver riavviato la console SRS.</span><span class="sxs-lookup"><span data-stu-id="5defa-189">If you configure these settings, the changes are replicated only after you restart the SRS console.</span></span> <span data-ttu-id="5defa-190">Verranno visualizzate solo le impostazioni degli aggiornamenti di sistema per i dispositivi SRS che utilizzano la versione 15,12 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="5defa-190">You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Impostazioni delle sale del portale di amministrazione di Lync room System](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="5defa-192">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5defa-192">Details</span></span>

<span data-ttu-id="5defa-193">La sezione dettagli fornisce un riepilogo di sola lettura delle impostazioni della sala SRS, tra cui: l'ora dell'ultimo aggiornamento. prossima riunione; ultimi aggiornamenti, manutenzione e calibrazione; impostazioni predefinite per altoparlanti, MIC e suonerie; versione URI SIP; numero di schermate e dettagli relativi a ogni schermata; stato e attività.</span><span class="sxs-lookup"><span data-stu-id="5defa-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Visualizzazione dettagli del portale di amministrazione di Lync room System](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="5defa-195">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="5defa-195">Troubleshooting</span></span>

<span data-ttu-id="5defa-196">La sezione risoluzione dei problemi può essere utilizzata per raccogliere i log in remoto e salvarli in una posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="5defa-196">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="5defa-197">È inoltre possibile riavviare la console SRS (interfaccia utente SRS) o riavviare l'intero sistema.</span><span class="sxs-lookup"><span data-stu-id="5defa-197">You can also restart the SRS console (SRS user interface) or restart the entire system.</span></span> <span data-ttu-id="5defa-198">Per raccogliere i registri, specificare un percorso di cartella nel formato specificato e verificare che la cartella disponga delle autorizzazioni di scrittura concesse all'account del computer SRS.</span><span class="sxs-lookup"><span data-stu-id="5defa-198">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account.</span></span> <span data-ttu-id="5defa-199">Se la dimensione del registro è troppo grande, è possibile richiedere fino a 5 minuti per completare la raccolta dei registri.</span><span class="sxs-lookup"><span data-stu-id="5defa-199">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="5defa-200">L'aggiornamento della pagina consente di ottenere lo stato più recente.</span><span class="sxs-lookup"><span data-stu-id="5defa-200">Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="5defa-201">Sanità</span><span class="sxs-lookup"><span data-stu-id="5defa-201">Health</span></span>

<span data-ttu-id="5defa-202">La sezione Health fornisce un'indicazione visiva dell'integrità della connessione di Skype for Business Server, del dispositivo audio, del dispositivo video, dello stato di resilienza e del dispositivo schermo.</span><span class="sxs-lookup"><span data-stu-id="5defa-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Integrità della sala del portale di amministrazione di Lync room System](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="5defa-204">Note aggiuntive sul portale Web amministrativo</span><span class="sxs-lookup"><span data-stu-id="5defa-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="5defa-205">Le modifiche apportate alle impostazioni vengono applicate solo dopo il riavvio del sistema SRS. > se la password dell'account LRSApp scade, non sarà possibile visualizzare lo stato delle chat room.</span><span class="sxs-lookup"><span data-stu-id="5defa-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="5defa-206">Configurare la password dell'account LRSAppuser in modo che non scada mai o accertarsi di aggiornare la password al termine della scadenza. > il portale Web amministrativo SRS è supportato solo per le distribuzioni locali.</span><span class="sxs-lookup"><span data-stu-id="5defa-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="5defa-207">Gestione in blocco</span><span class="sxs-lookup"><span data-stu-id="5defa-207">Bulk management</span></span>

<span data-ttu-id="5defa-208">La gestione in blocco delle sale SRS è una funzionalità progettata per gli amministratori IT avanzati, per semplificare il flusso di lavoro e per consentire loro di gestire in remoto più ambienti in modo più semplice.</span><span class="sxs-lookup"><span data-stu-id="5defa-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="5defa-209">Per visualizzare questa funzionalità, è necessario eseguire il provisioning dell'utente come membro del gruppo di sicurezza speciale **LRSPowerUserAdminsGroup**.</span><span class="sxs-lookup"><span data-stu-id="5defa-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="5defa-210">Non esiste alcun limite al numero di stanze SRS che è possibile selezionare per la gestione in blocco.</span><span class="sxs-lookup"><span data-stu-id="5defa-210">There is no limit to the number of SRS rooms you can select for bulk management.</span></span> <span data-ttu-id="5defa-211">Tuttavia, è possibile eseguire una sola operazione di gestione in blocco alla volta.</span><span class="sxs-lookup"><span data-stu-id="5defa-211">However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="5defa-212">Per eseguire un'operazione di gestione in blocco, selezionare le sale che si desidera monitorare e fare clic sul menu gestione in blocco.</span><span class="sxs-lookup"><span data-stu-id="5defa-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="5defa-213">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="5defa-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="5defa-214">Perché non è possibile accedere al portale Web amministrativo?</span><span class="sxs-lookup"><span data-stu-id="5defa-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="5defa-215">Quando si apre https://localhost/lrs , si sarà in grado di visualizzare la pagina di accesso, ma quando si digita le credenziali, non è possibile accedere.</span><span class="sxs-lookup"><span data-stu-id="5defa-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="5defa-216">In questo caso, è necessario aprire https://FQDNofFEserver/SRS per accedere al portale Web amministrativo.</span><span class="sxs-lookup"><span data-stu-id="5defa-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="5defa-217">Perché non è possibile visualizzare il servizio SRS V1 nel portale Web di amministrazione?</span><span class="sxs-lookup"><span data-stu-id="5defa-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="5defa-218">Verificare di disporre degli account SRS nella distribuzione e che vengano creati in base ai suggerimenti relativi alla distribuzione del portale Web amministrativo di SRS.</span><span class="sxs-lookup"><span data-stu-id="5defa-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="5defa-219">Verificare che gli account SRS siano stati provisionati usando Enable-CsMeetingRoom, not Enable-CsUser, su Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5defa-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="5defa-220">Se sono stati creati account SRS e non è possibile visualizzare gli account nel portale Web amministrativo, raccogliere i registri del server utilizzando lo strumento di registrazione di Skype for Business Server con il componente **MeetingPortal** selezionato e quindi inviarli al contatto di supporto SRS.</span><span class="sxs-lookup"><span data-stu-id="5defa-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="5defa-221">Se sono stati creati account SRS e non è possibile visualizzare gli account nel portale Web amministrativo, raccogliere i registri client utilizzando Fiddler e copiare anche il registro della console dagli strumenti di sviluppo del browser e quindi inviarli al contatto di supporto SRS.</span><span class="sxs-lookup"><span data-stu-id="5defa-221">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact.</span></span> <span data-ttu-id="5defa-222">È inoltre possibile modificare il valore del livello di traccia nell'Web.config per ottenere un log più dettagliato.</span><span class="sxs-lookup"><span data-stu-id="5defa-222">You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

  ```xml
  <system.diagnostics>
    <switches>
      <!--
      This switch controls logging message levels. 0 implies
      logging is turned off. 1 implies only errors are logged,
      2 implies errors &amp; warnings. 4 is the most detailed.
      -->
      <add name="TraceLevelSwitch" value="3" />
    </switches>
  </system.diagnostics>
  ```

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="5defa-223">Perché non è possibile visualizzare lo stato di SRS nel portale Web di amministrazione?</span><span class="sxs-lookup"><span data-stu-id="5defa-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="5defa-224">Verificare che l'account utente di LRSApp sia abilitato per SIP.</span><span class="sxs-lookup"><span data-stu-id="5defa-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="5defa-225">Se si verificano ancora problemi, raccogliere il file **Trace. log** nel sistema SRS da D:\Tracing\LRSAdminLogs \, e quindi inviarlo al contatto di supporto SRS.</span><span class="sxs-lookup"><span data-stu-id="5defa-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="5defa-226">Perché non è possibile visualizzare i menu di gestione di massa per il servizio SRS nel portale Web di amministrazione?</span><span class="sxs-lookup"><span data-stu-id="5defa-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="5defa-227">Assicurarsi che l'account utente di LRSApp sia abilitato per SIP e faccia parte del gruppo di sicurezza LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="5defa-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="5defa-228">Il portale Web amministrativo SRS V1 funziona con le sale di Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="5defa-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="5defa-229">No.</span><span class="sxs-lookup"><span data-stu-id="5defa-229">No.</span></span>


