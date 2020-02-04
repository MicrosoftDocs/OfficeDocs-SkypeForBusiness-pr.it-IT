---
title: 'Lync Server 2013: Assegnare i criteri di conferenza per supportare gli utenti anonimi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bab1c3da15bd72bb03233ca05d86e355eebbb233
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a><span data-ttu-id="3a845-102">Assegnare i criteri di conferenza per supportare gli utenti anonimi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a845-102">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a845-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3a845-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3a845-104">Per impostazione predefinita, a tutti gli utenti viene impedito di invitare utenti anonimi a partecipare a una riunione.</span><span class="sxs-lookup"><span data-stu-id="3a845-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="3a845-105">Puoi controllare chi può invitare utenti anonimi configurando un criterio di conferenza per supportare utenti anonimi e applicando i criteri di conferenza a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="3a845-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="3a845-106">Per informazioni dettagliate su come configurare i criteri di conferenza per il supporto degli utenti anonimi, vedere [creare o modificare criteri di conferenza in Lync server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) e [gestire la Federazione e l'accesso esterno a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="3a845-106">For details about how to configure a conferencing policies to support anonymous users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span>

<span data-ttu-id="3a845-107">Usare la procedura descritta in questa sezione per applicare un criterio di conferenza già creato a uno o più utenti o gruppi di utente.</span><span class="sxs-lookup"><span data-stu-id="3a845-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3a845-108">Oltre a configurare e applicare un criterio per consentire agli utenti di invitare utenti anonimi, è anche necessario abilitare il supporto per gli utenti anonimi per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3a845-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="3a845-109">Per informazioni dettagliate, vedere <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">configurare i criteri per controllare l'accesso degli utenti pubblici in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3a845-109">For details, see <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="3a845-110">Per configurare un criterio utente per la partecipazione anonima alle riunioni</span><span class="sxs-lookup"><span data-stu-id="3a845-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="3a845-111">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3a845-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3a845-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3a845-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3a845-113">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3a845-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3a845-114">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a845-114">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="3a845-115">Per creare un nuovo criterio utente, fare clic su **nuovo**e quindi su **criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="3a845-115">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="3a845-116">Creare un nome univoco nel campo **nome** che indichi le informazioni relative ai criteri utente, ad esempio **EnableAnonymous** per un criterio utente che consente la comunicazione con utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="3a845-116">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="3a845-117">Per configurare un criterio utente esistente, fare clic sul criterio appropriato elencato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="3a845-117">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="3a845-118">Nella finestra di dialogo **criteri di conferenza** selezionare la casella **di controllo Consenti ai partecipanti di invitare utenti anonimi** .</span><span class="sxs-lookup"><span data-stu-id="3a845-118">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="3a845-119">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="3a845-119">Click **Commit**.</span></span>

6.  <span data-ttu-id="3a845-120">Nella barra di spostamento sinistra fare clic su **utenti**, cercare nell'account utente che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="3a845-120">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="3a845-121">Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="3a845-121">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="3a845-122">In **modifica utenti di Lync Server** in **criteri di conferenza**Selezionare il criterio utente con la configurazione di accesso utente anonima che si vuole applicare a questo utente.</span><span class="sxs-lookup"><span data-stu-id="3a845-122">In **Edit Lync Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a845-123">Le <STRONG> &lt;impostazioni&gt; automatiche</STRONG> applicano le impostazioni di installazione predefinite del server e vengono applicate automaticamente dal server.</span><span class="sxs-lookup"><span data-stu-id="3a845-123">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>

    
    </div>

<span data-ttu-id="3a845-124">Per consentire agli utenti di invitare utenti anonimi alle conferenze, è anche necessario abilitare il supporto per gli utenti anonimi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3a845-124">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="3a845-125">Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti pubblici in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="3a845-125">For details, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

