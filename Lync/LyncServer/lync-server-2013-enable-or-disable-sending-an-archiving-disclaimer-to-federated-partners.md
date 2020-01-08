---
title: Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità relativa all'archiviazione ai partner federati
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable sending an Archiving disclaimer to federated partners
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9364f3562c837b949ef589fc7c5cbd2bc4a2b4cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a><span data-ttu-id="44008-102">Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità relativa all'archiviazione ai partner federati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44008-102">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44008-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="44008-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="44008-104">Al momento della distribuzione degli Edge Server e della federazione abilitata per l'organizzazione, è necessario specificare se inviare automaticamente la dichiarazione di non responsabilità per l'archiviazione a partner federati.</span><span class="sxs-lookup"><span data-stu-id="44008-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="44008-105">Se si archiviano comunicazioni esterne, è necessario abilitare l'invio di una dichiarazione di non responsabilità per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="44008-105">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="44008-106">Usare la procedura descritta in questo argomento per modificare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="44008-106">Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="44008-107">La procedura seguente presuppone che tu abbia già abilitato la Federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="44008-107">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="44008-108">Per informazioni dettagliate sull'abilitazione della Federazione, vedere <A href="lync-server-2013-enable-or-disable-remote-user-access.md">abilitare o disabilitare l'accesso remoto agli utenti in Lync Server 2013</A> nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="44008-108">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="44008-109">Per abilitare o disabilitare l'invio di una dichiarazione di non responsabilità per l'archiviazione a partner federati</span><span class="sxs-lookup"><span data-stu-id="44008-109">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="44008-110">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="44008-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="44008-111">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44008-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="44008-112">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="44008-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="44008-113">Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**, fare clic su **configurazione bordo di Access**.</span><span class="sxs-lookup"><span data-stu-id="44008-113">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="44008-114">Nella scheda **configurazione di Access Edge** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="44008-114">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="44008-115">In **modifica configurazione di Access Edge**, in **abilitare le comunicazioni con gli utenti federati**, selezionare o deselezionare la casella di controllo **Invia dichiarazione di non responsabilità per i partner federati** per abilitare o disabilitare l'invio automatico della dichiarazione di non responsabilità per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="44008-115">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="44008-116">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="44008-116">Click **Commit**.</span></span>

<span data-ttu-id="44008-117">Per consentire agli utenti federati di collaborare con gli utenti nella distribuzione di Lync Server 2013, è necessario avere anche configurato almeno un criterio di accesso esterno per supportare l'accesso degli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="44008-117">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="44008-118">Per informazioni dettagliate, vedere [gestire i partner federati XMPP in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="44008-118">For details, see [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="44008-119">Per informazioni dettagliate sul controllo dell'accesso per specifici domini federati, vedere [configurare il supporto per i domini esterni consentiti in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) nella documentazione relativa alle operazioni o alla documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="44008-119">For details about controlling access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="44008-120">Abilitazione o disabilitazione della dichiarazione di non responsabilità per l'archiviazione tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="44008-120">Enabling or Disabling the Archiving Disclaimer by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="44008-121">L'uso della dichiarazione di non responsabilità per l'archiviazione può essere gestito tramite Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="44008-121">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="44008-122">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44008-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="44008-123">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="44008-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="44008-124">Per abilitare la dichiarazione di non responsabilità per l'archiviazione</span><span class="sxs-lookup"><span data-stu-id="44008-124">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="44008-125">Per abilitare la dichiarazione di non responsabilità per l'archiviazione, imposta il valore della proprietà **EnableArchivingDisclaimer** su True ($true):</span><span class="sxs-lookup"><span data-stu-id="44008-125">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="44008-126">Per disabilitare la dichiarazione di non responsabilità per l'archiviazione</span><span class="sxs-lookup"><span data-stu-id="44008-126">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="44008-127">Per disabilitare la dichiarazione di non responsabilità per l'archiviazione, imposta il valore della proprietà **EnableArchivingDisclaimer** su False ($false):</span><span class="sxs-lookup"><span data-stu-id="44008-127">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

