---
title: Abilitare o disabilitare l'individuazione dei partner della federazione
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Al momento della distribuzione degli Edge Server e della federazione abilitata per l'organizzazione, è necessario specificare se supportare l'individuazione automatica dei domini partner federati.
ms.openlocfilehash: a5569639cf870d2a5da16ef81aa733724a6701b3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188888"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="fd08e-103">Abilitare o disabilitare l'individuazione dei partner federativi in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fd08e-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="fd08e-104">Al momento della distribuzione degli Edge Server e della federazione abilitata per l'organizzazione, è necessario specificare se supportare l'individuazione automatica dei domini partner federati.</span><span class="sxs-lookup"><span data-stu-id="fd08e-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="fd08e-105">Usare la procedura descritta in questo argomento per modificare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="fd08e-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="fd08e-106">La procedura seguente presuppone che tu abbia già abilitato la Federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fd08e-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="fd08e-107">Per informazioni dettagliate sull'abilitazione della Federazione, vedere [abilitare o disabilitare l'accesso remoto agli utenti](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="fd08e-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="fd08e-108">Per abilitare o disabilitare l'individuazione automatica dei domini federati per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="fd08e-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="fd08e-109">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="fd08e-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fd08e-110">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fd08e-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="fd08e-111">Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**, fare clic su **configurazione bordo di Access**.</span><span class="sxs-lookup"><span data-stu-id="fd08e-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="fd08e-112">Nella pagina **configurazione di Access Edge** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="fd08e-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="fd08e-113">In **modifica configurazione di Access Edge**, in **abilitare le comunicazioni con gli utenti federati**, selezionare o deselezionare la casella di controllo **Abilita individuazione dominio partner** per abilitare o disabilitare l'individuazione automatica dei domini partner.</span><span class="sxs-lookup"><span data-stu-id="fd08e-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="fd08e-114">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="fd08e-114">Click **Commit**.</span></span>

<span data-ttu-id="fd08e-115">Per consentire agli utenti federati di collaborare con gli utenti nella distribuzione di Skype for Business Server, è necessario che siano configurati almeno un criterio di accesso esterno per supportare l'accesso degli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="fd08e-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="fd08e-116">Per informazioni dettagliate, vedere [abilitare o disabilitare la connettività per la messaggistica istantanea pubblica e la Federazione](enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="fd08e-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="fd08e-117">Per informazioni dettagliate su come controllare l'accesso per specifici domini federati, vedere [gestire i domini federati SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) e [gestire i provider federati SIP](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="fd08e-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fd08e-118">Abilitazione o disabilitazione dell'individuazione dei partner federativi tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd08e-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="fd08e-119">L'individuazione dei partner federativi può essere gestita tramite Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="fd08e-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="fd08e-120">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd08e-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="fd08e-121">Per abilitare l'individuazione dei partner federativi</span><span class="sxs-lookup"><span data-stu-id="fd08e-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="fd08e-122">Per abilitare l'individuazione dei partner federativi, imposta il valore della proprietà **EnablePartnerDiscovery** su True ($true).</span><span class="sxs-lookup"><span data-stu-id="fd08e-122">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="fd08e-123">Tieni presente che devi abilitare il routing SRV DNS per cambiare il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="fd08e-123">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="fd08e-124">Per disabilitare l'individuazione dei partner federativi</span><span class="sxs-lookup"><span data-stu-id="fd08e-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="fd08e-125">Per disabilitare l'individuazione dei partner federativi, imposta il valore della proprietà **EnablePartnerDiscovery** su False ($false):</span><span class="sxs-lookup"><span data-stu-id="fd08e-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

