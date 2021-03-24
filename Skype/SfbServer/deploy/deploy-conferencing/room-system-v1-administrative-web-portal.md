---
title: Distribuire il portale Web amministrativo di SRS v1 in Skype for Business Server
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
description: Il portale Web amministrativo Skype for Business Server Skype Room Systems v1 (SRS v1, in precedenza noto come Lync Room System) è un portale Web che le organizzazioni possono utilizzare per gestire le proprie sale riunioni Skype Room Systems. Gli amministratori possono utilizzare il portale Web di amministrazione di SRS v1 per monitorare l'integrità dei dispositivi, ad esempio monitorando i dispositivi audio/video. Con questo portale, gli amministratori possono raccogliere in remoto informazioni di diagnostica per monitorare l'integrità delle sale riunioni.
ms.openlocfilehash: 94e163ccbeff3bde78569aa864b44525b267ccd8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103882"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="79b44-105">Distribuire il portale Web amministrativo di SRS v1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="79b44-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="79b44-106">Il portale Web amministrativo Skype for Business Server Skype Room Systems v1 (SRS v1, in precedenza noto come Lync Room System) è un portale Web che le organizzazioni possono utilizzare per gestire le proprie sale riunioni Skype Room Systems.</span><span class="sxs-lookup"><span data-stu-id="79b44-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="79b44-107">Gli amministratori possono utilizzare il portale Web di amministrazione di SRS v1 per monitorare l'integrità dei dispositivi, ad esempio monitorando i dispositivi audio/video.</span><span class="sxs-lookup"><span data-stu-id="79b44-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="79b44-108">Con questo portale, gli amministratori possono raccogliere in remoto informazioni di diagnostica per monitorare l'integrità delle sale riunioni.</span><span class="sxs-lookup"><span data-stu-id="79b44-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="79b44-109">Per usare questa funzionalità, il portale Web amministrativo di SRS v1 deve essere distribuito in ogni Front End Server di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="79b44-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="79b44-110">In questa guida vengono fornite istruzioni per gli amministratori su come installare e configurare il portale Web amministrativo SRS.</span><span class="sxs-lookup"><span data-stu-id="79b44-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="79b44-111">È destinato agli amministratori che hanno conoscenza dell'amministrazione di Skype for Business Server e che dispongono dei diritti utente di amministratore per modificare la topologia di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="79b44-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="79b44-112">Dopo la distribuzione del portale Web amministrativo SRS v1 nel server, gli amministratori possono controllare lo stato dei dispositivi SRS v1 accedendo al sito dai propri computer o laptop.</span><span class="sxs-lookup"><span data-stu-id="79b44-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79b44-113">Scaricare microsoft [Skype Room Systems v1 Administrative Web Portal per Skype for Business Server 2015.](https://www.microsoft.com/download/details.aspx?id=46906)</span><span class="sxs-lookup"><span data-stu-id="79b44-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="79b44-114">Contenuto dell'argomento:</span><span class="sxs-lookup"><span data-stu-id="79b44-114">In this topic:</span></span>

- [<span data-ttu-id="79b44-115">Configurare l'ambiente per il portale Web amministrativo di SRS v1</span><span class="sxs-lookup"><span data-stu-id="79b44-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="79b44-116">Installare il portale Web amministrativo di SRS v1</span><span class="sxs-lookup"><span data-stu-id="79b44-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="79b44-117">Usare il portale Web amministrativo SRS</span><span class="sxs-lookup"><span data-stu-id="79b44-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="79b44-118">Configurare l'ambiente per il portale Web amministrativo di SRS v1</span><span class="sxs-lookup"><span data-stu-id="79b44-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="79b44-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="79b44-119"><a name="Config_Env"> </a></span></span>

<span data-ttu-id="79b44-120">Per utilizzare il portale Web amministrativo di SRS v1, è necessario installare o configurare i prerequisiti seguenti.</span><span class="sxs-lookup"><span data-stu-id="79b44-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79b44-121">Se il server è configurato con l'autenticazione Kerberos e NTLM e SRS è in esecuzione in un computer che non fa parte del dominio, l'autenticazione Kerberos avrà esito negativo e l'utente non sarà in grado di visualizzare lo stato di SRS nel portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="79b44-121">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal.</span></span> <span data-ttu-id="79b44-122">Per risolvere questo problema, configurare il server con l'autenticazione NTLM o l'autenticazione NTLM e TLS-DSK (senza Kerberos) oppure aggiungere il computer SRS al dominio.</span><span class="sxs-lookup"><span data-stu-id="79b44-122">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="79b44-123">Installare gli aggiornamenti cumulativi di Skype for Business Server nella topologia di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="79b44-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="79b44-124">Per ottenere l'aggiornamento o vedere cosa include, vedere [Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="79b44-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="79b44-125">Creare un utente di Active Directory abilitato per SIP.</span><span class="sxs-lookup"><span data-stu-id="79b44-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="79b44-126">Il portale Web amministrativo di SRS v1 usa queste credenziali per eseguire query sulle informazioni da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="79b44-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="79b44-127">Il nome utente negli esempi forniti è LRSApp.</span><span class="sxs-lookup"><span data-stu-id="79b44-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="79b44-128">Creare un gruppo di sicurezza di Active Directory con nome LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="79b44-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="79b44-129">Creare il gruppo con Ambito gruppo come Globale e Tipo di gruppo come Sicurezza.</span><span class="sxs-lookup"><span data-stu-id="79b44-129">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="79b44-130">Gli utenti abilitati per SIP aggiunti a questo gruppo saranno autorizzati a visualizzare l'elenco delle sale ed eseguire determinati comandi, ad esempio la raccolta dei registri.</span><span class="sxs-lookup"><span data-stu-id="79b44-130">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="79b44-131">Creare un gruppo di sicurezza di Active Directory con nome LRSFullAccessAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="79b44-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="79b44-132">Creare il gruppo con Ambito gruppo come Globale e Tipo di gruppo come Security.SIP gli utenti che vengono aggiunti a questo gruppo sono autorizzati a utilizzare tutte le funzionalità del portale di amministrazione in una singola sala Skype.</span><span class="sxs-lookup"><span data-stu-id="79b44-132">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room.</span></span> <span data-ttu-id="79b44-133">Per includere il supporto per la gestione in blocco delle sale Skype, fare riferimento al passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="79b44-133">To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![Elenco di gruppi di amministratori con ruolo gruppo di sicurezza](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="79b44-135">Creare un gruppo di sicurezza di Active Directory con nome LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="79b44-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="79b44-136">Creare il gruppo con Ambito gruppo come Globale e Tipo di gruppo come Sicurezza.</span><span class="sxs-lookup"><span data-stu-id="79b44-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="79b44-137">Gli utenti abilitati per SIP aggiunti a questo gruppo sono autorizzati a utilizzare tutte le funzionalità del portale di amministrazione, inclusa la gestione in blocco delle sale Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="79b44-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="79b44-138">Aggiungere LRSFullAccessAdminGroup come membro di LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="79b44-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![Pagina Membri proprietà LRSSupportAdminGroup](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="79b44-140">Creare un utente di Active Directory abilitato per SIP con nome LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="79b44-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="79b44-141">Aggiungi questo utente a LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="79b44-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![Pagina Membri proprietà LRSSupportAdminGroup](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="79b44-143">Installare [ASP.NET MVC 4 per Visual Studio 2010 SP1 e Visual Web Developer 2010 SP1.](https://go.microsoft.com/fwlink/p/?LinkId=323967)</span><span class="sxs-lookup"><span data-stu-id="79b44-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="79b44-144">Installare il portale Web amministrativo di SRS v1</span><span class="sxs-lookup"><span data-stu-id="79b44-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="79b44-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="79b44-145"><a name="Install_SRS"> </a></span></span>

<span data-ttu-id="79b44-146">Scaricare microsoft [Skype Room Systems v1 Administrative Web Portal per Skype for Business Server 2015.](https://www.microsoft.com/download/details.aspx?id=46906)</span><span class="sxs-lookup"><span data-stu-id="79b44-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="79b44-147">Per installare il portale Web amministrativo di SRS v1, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="79b44-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="79b44-148">Configurare la porta dell'applicazione attendibile eseguendo il cmdlet seguente in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="79b44-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="79b44-149">Per installare il portale della sala riunioni, scaricare **MeetingRoomPortalInstaller.msi** ed eseguirlo come amministratore.</span><span class="sxs-lookup"><span data-stu-id="79b44-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="79b44-150">Aprire il Web.config file dal percorso seguente:</span><span class="sxs-lookup"><span data-stu-id="79b44-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="79b44-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span><span class="sxs-lookup"><span data-stu-id="79b44-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span></span>\

4. <span data-ttu-id="79b44-152">Nel file Web.Config modificare PortalUserName con il nome utente creato nel passaggio 2 nella sezione "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (il nome consigliato nel passaggio è LRSApp):</span><span class="sxs-lookup"><span data-stu-id="79b44-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="79b44-153">Poiché il portale di amministrazione di SRS v1 è un'applicazione attendibile, non è necessario fornire la password nella configurazione del portale.</span><span class="sxs-lookup"><span data-stu-id="79b44-153">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="79b44-154">Se l'utente utilizza un registrar diverso da quello locale, è necessario specificarlo aggiungendo la riga seguente nel file Web.Config:</span><span class="sxs-lookup"><span data-stu-id="79b44-154">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="79b44-155">Se la porta utilizzata è diversa da 5061, aggiungere la riga seguente nel file Web.Config:</span><span class="sxs-lookup"><span data-stu-id="79b44-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="79b44-156">Verificare l'installazione del portale Web amministrativo SRS</span><span class="sxs-lookup"><span data-stu-id="79b44-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="79b44-157">Per verificare l'installazione del portale Web amministrativo di SRS v1, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="79b44-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="79b44-158">In un front-end server passare all'URL seguente:</span><span class="sxs-lookup"><span data-stu-id="79b44-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="79b44-159">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="79b44-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="79b44-160">Non dovrebbe essere visualizzato alcun errore, come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="79b44-160">You should not see any errors, as shown in the following image:</span></span>

     ![Schermata di accesso al portale di amministrazione di Lync Room System](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="79b44-162">Se non vengono visualizzati errori, provare ad accedere all'URL seguente da qualsiasi altro computer della topologia:</span><span class="sxs-lookup"><span data-stu-id="79b44-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="79b44-163">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="79b44-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="79b44-164">Per accedere alla pagina, è necessario aggiungere i record DNS come descritto in "[Record DNS necessari per l'accesso](/previous-versions/office/communications-server/bb663700(v=office.12))automatico al client ".</span><span class="sxs-lookup"><span data-stu-id="79b44-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](/previous-versions/office/communications-server/bb663700(v=office.12))."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="79b44-165">Usare il portale Web amministrativo SRS</span><span class="sxs-lookup"><span data-stu-id="79b44-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="79b44-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="79b44-166"><a name="Use_Portal"> </a></span></span>

<span data-ttu-id="79b44-167">Dopo aver distribuito SRS nel server, è possibile controllare lo stato di tutte le sale SRS accedendo al portale Web amministrativo SRS v1 da un browser.</span><span class="sxs-lookup"><span data-stu-id="79b44-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="79b44-168">Accesso</span><span class="sxs-lookup"><span data-stu-id="79b44-168">Sign in</span></span>

1. <span data-ttu-id="79b44-169">Passare all'URL seguente:</span><span class="sxs-lookup"><span data-stu-id="79b44-169">Browse to the following URL:</span></span>

    <span data-ttu-id="79b44-170">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="79b44-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="79b44-171">Immettere le credenziali per l'account LRSSupport o un account aggiunto al gruppo di sicurezza LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="79b44-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Schermata di accesso al portale di amministrazione di Lync Room System](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="79b44-173">Pagina di riepilogo del portale Web amministrativo SRS</span><span class="sxs-lookup"><span data-stu-id="79b44-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="79b44-174">Nella pagina di riepilogo sono disponibili le informazioni seguenti per tutte le sale SRS distribuite nel server:</span><span class="sxs-lookup"><span data-stu-id="79b44-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="79b44-175">**Tag** Nome personalizzato che l'amministratore assegna alla sala.</span><span class="sxs-lookup"><span data-stu-id="79b44-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="79b44-176">Il tag può essere impostato nel portale facendo clic sul nome della sala.</span><span class="sxs-lookup"><span data-stu-id="79b44-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="79b44-177">**Integrità** Lo stato di integrità della sala, derivato dallo stato Aggrega integrità della sala, visualizzato nella sezione Integrità della pagina Impostazioni sala.</span><span class="sxs-lookup"><span data-stu-id="79b44-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="79b44-178">**Riunione successiva** Data e ora di pianificazione della riunione successiva.</span><span class="sxs-lookup"><span data-stu-id="79b44-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="79b44-179">**Versione SRS, produttore, modello** Questi valori sono preimpostati in SRS.</span><span class="sxs-lookup"><span data-stu-id="79b44-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="79b44-180">A seconda del produttore, questi campi potrebbero essere lasciati vuoti.</span><span class="sxs-lookup"><span data-stu-id="79b44-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="79b44-181">**Last Refresh** Visualizza l'ultima volta che la pagina Web è stata aggiornata.</span><span class="sxs-lookup"><span data-stu-id="79b44-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Visualizzazione di riepilogo del portale di amministrazione di Lync Room System](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="79b44-183">Il menu Gestione in blocco verrà visualizzato solo se si fa parte del gruppo di sicurezza LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="79b44-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="79b44-184">Informazioni sala SRS</span><span class="sxs-lookup"><span data-stu-id="79b44-184">SRS Room Information</span></span>

<span data-ttu-id="79b44-185">La sezione Informazioni sala del portale consente di visualizzare e configurare singole sale SRS.</span><span class="sxs-lookup"><span data-stu-id="79b44-185">The Room Info section of the portal allows you to view and configure individual SRS rooms.</span></span> <span data-ttu-id="79b44-186">Contiene quattro sezioni: Impostazioni, Dettagli, Registrazione e Integrità.</span><span class="sxs-lookup"><span data-stu-id="79b44-186">It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="79b44-187">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="79b44-187">Settings</span></span>

<span data-ttu-id="79b44-188">Nella sezione Impostazioni puoi impostare la password, il tag sala e i livelli di volume predefiniti per la sala.</span><span class="sxs-lookup"><span data-stu-id="79b44-188">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="79b44-189">Se si configurano queste impostazioni, le modifiche vengono replicate solo dopo il riavvio della console SRS.</span><span class="sxs-lookup"><span data-stu-id="79b44-189">If you configure these settings, the changes are replicated only after you restart the SRS console.</span></span> <span data-ttu-id="79b44-190">Verranno visualizzati solo gli aggiornamenti di sistema per i dispositivi SRS che usano la versione 15.12 e successive.</span><span class="sxs-lookup"><span data-stu-id="79b44-190">You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Impostazioni della chat room del portale di amministrazione di Lync Room](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="79b44-192">Dettagli</span><span class="sxs-lookup"><span data-stu-id="79b44-192">Details</span></span>

<span data-ttu-id="79b44-193">La sezione Dettagli fornisce un riepilogo di sola lettura delle impostazioni della sala SRS, tra cui: l'ora dell'ultimo aggiornamento; riunione successiva; ultimi aggiornamenti, manutenzione e calibrazione; impostazioni predefinite di altoparlante, microfono e suoneria; version; URI SIP; numero di schermate e dettagli su ogni schermata; stato e attività.</span><span class="sxs-lookup"><span data-stu-id="79b44-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Visualizzazione dettagli portale di amministrazione di Lync Room System](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="79b44-195">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="79b44-195">Troubleshooting</span></span>

<span data-ttu-id="79b44-196">La sezione Risoluzione dei problemi può essere utilizzata per raccogliere in remoto i log e salvarli in un percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="79b44-196">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="79b44-197">È inoltre possibile riavviare la console SRS (interfaccia utente SRS) o riavviare l'intero sistema.</span><span class="sxs-lookup"><span data-stu-id="79b44-197">You can also restart the SRS console (SRS user interface) or restart the entire system.</span></span> <span data-ttu-id="79b44-198">Per raccogliere i registri, specificare un percorso di cartella nel formato specificato e assicurarsi che la cartella abbia le autorizzazioni di scrittura concesse all'account computer SRS.</span><span class="sxs-lookup"><span data-stu-id="79b44-198">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account.</span></span> <span data-ttu-id="79b44-199">Se le dimensioni del registro sono troppo grandi, la raccolta dei registri può richiedere fino a 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="79b44-199">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="79b44-200">Aggiornando la pagina verrà visualizzato lo stato più recente.</span><span class="sxs-lookup"><span data-stu-id="79b44-200">Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="79b44-201">Sanità</span><span class="sxs-lookup"><span data-stu-id="79b44-201">Health</span></span>

<span data-ttu-id="79b44-202">La sezione Health fornisce un'indicazione visiva dell'integrità della connessione a Skype for Business Server, del dispositivo audio, del dispositivo video, dello stato di resilienza e del dispositivo schermo.</span><span class="sxs-lookup"><span data-stu-id="79b44-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Lync Room System Admin Portal Room Health](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="79b44-204">Note aggiuntive sul portale Web amministrativo</span><span class="sxs-lookup"><span data-stu-id="79b44-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="79b44-205">Le modifiche alle impostazioni vengono applicate solo dopo il riavvio del sistema SRS.> Se la password dell'account LRSApp scade, non sarà possibile visualizzare lo stato delle chat room.</span><span class="sxs-lookup"><span data-stu-id="79b44-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="79b44-206">Configurare la password dell'account LRSAppuser in modo che non scada mai o assicurarsi di aggiornarla quando è prossima alla scadenza.> Il portale Web di amministrazione di SRS è supportato solo per le distribuzioni locali.</span><span class="sxs-lookup"><span data-stu-id="79b44-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="79b44-207">Gestione in blocco</span><span class="sxs-lookup"><span data-stu-id="79b44-207">Bulk management</span></span>

<span data-ttu-id="79b44-208">La gestione in blocco delle sale SRS è una funzionalità progettata per gli amministratori IT avanzati, per semplificare il flusso di lavoro e abilitarle con uno strumento conveniente per risparmiare tempo per gestire in remoto più sale in blocco.</span><span class="sxs-lookup"><span data-stu-id="79b44-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="79b44-209">Per visualizzare questa funzionalità, è necessario eseguire il provisioning dell'utente come membro del gruppo di sicurezza speciale **LRSPowerUserAdminsGroup.**</span><span class="sxs-lookup"><span data-stu-id="79b44-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="79b44-210">Non esiste alcun limite al numero di sale SRS che è possibile selezionare per la gestione in blocco.</span><span class="sxs-lookup"><span data-stu-id="79b44-210">There is no limit to the number of SRS rooms you can select for bulk management.</span></span> <span data-ttu-id="79b44-211">Tuttavia, è possibile eseguire una sola operazione di gestione in blocco alla volta.</span><span class="sxs-lookup"><span data-stu-id="79b44-211">However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="79b44-212">Per eseguire un'operazione di gestione in blocco, selezionare le sale che si desidera monitorare e fare clic sul menu Gestione in blocco.</span><span class="sxs-lookup"><span data-stu-id="79b44-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="79b44-213">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="79b44-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="79b44-214">Perché non è possibile accedere al portale Web amministrativo?</span><span class="sxs-lookup"><span data-stu-id="79b44-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="79b44-215">Quando si apre , sarà possibile visualizzare la pagina di accesso, ma quando si digitano le credenziali, non è https://localhost/lrs possibile accedere.</span><span class="sxs-lookup"><span data-stu-id="79b44-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="79b44-216">In questo caso, è necessario aprire https://FQDNofFEserver/SRS per accedere al portale Web amministrativo.</span><span class="sxs-lookup"><span data-stu-id="79b44-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="79b44-217">Perché non è possibile visualizzare SRS v1 nel portale Web di amministrazione?</span><span class="sxs-lookup"><span data-stu-id="79b44-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="79b44-218">Assicurarsi di disporre di account SRS nella distribuzione e che siano creati in base alle indicazioni per la distribuzione del portale Web amministrativo SRS.</span><span class="sxs-lookup"><span data-stu-id="79b44-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="79b44-219">Assicurati che il provisioning degli account SRS sia eseguito tramite Enable-CsMeetingRoom, non Enable-CsUser, in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="79b44-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="79b44-220">Se sono stati creati account SRS e non è possibile visualizzare gli account nel portale Web amministrativo, raccogliere i log del server utilizzando lo strumento di registrazione di Skype for Business Server con il **componente MeetingPortal** selezionato e quindi inviarli al contatto di supporto SRS.</span><span class="sxs-lookup"><span data-stu-id="79b44-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="79b44-221">Se sono stati creati account SRS e non è possibile visualizzare gli account nel portale Web di amministrazione, raccogliere i log client utilizzando Fiddler e copiare il registro della console dagli strumenti di sviluppo del browser e quindi inviarli al contatto di supporto SRS.</span><span class="sxs-lookup"><span data-stu-id="79b44-221">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact.</span></span> <span data-ttu-id="79b44-222">È inoltre possibile modificare il valore del livello di traccia nel Web.config per ottenere un registro più dettagliato.</span><span class="sxs-lookup"><span data-stu-id="79b44-222">You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="79b44-223">Perché non è possibile visualizzare lo stato di SRS nel portale Web amministrativo?</span><span class="sxs-lookup"><span data-stu-id="79b44-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="79b44-224">Verificare che l'account utente LRSApp sia abilitato per SIP.</span><span class="sxs-lookup"><span data-stu-id="79b44-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="79b44-225">Se si verificano ancora problemi, raccogliere il file **Trace.log** nel sistema SRS da D:\Tracing\LRSAdminLogs e inviarlo al contatto di supporto \, SRS.</span><span class="sxs-lookup"><span data-stu-id="79b44-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="79b44-226">Perché non è possibile visualizzare i menu di gestione in blocco per SRS nel portale Web amministrativo?</span><span class="sxs-lookup"><span data-stu-id="79b44-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="79b44-227">Verificare che l'account utente LRSApp sia abilitato per SIP e che sia parte del gruppo di sicurezza LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="79b44-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="79b44-228">Il portale Web amministrativo di SRS v1 funziona con Microsoft Teams Rooms?</span><span class="sxs-lookup"><span data-stu-id="79b44-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="79b44-229">No.</span><span class="sxs-lookup"><span data-stu-id="79b44-229">No.</span></span>