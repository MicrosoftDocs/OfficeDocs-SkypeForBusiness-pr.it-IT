---
title: Abilitare o disabilitare l'individuazione di partner federativi
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Al momento della distribuzione degli Edge Server e dell'abilitazione della federazione per l'organizzazione, dovrebbe essere stato specificato se supportare l'individuazione automatica dei domini partner federati.
ms.openlocfilehash: e1f076b725dff149f024a3fd59f9f7d52da4e6a8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817426"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="56561-103">Abilitare o disabilitare l'individuazione dei partner federativi in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="56561-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="56561-p101">Al momento della distribuzione degli Edge Server e dell'abilitazione della federazione per l'organizzazione, dovrebbe essere stato specificato se supportare l'individuazione automatica dei domini partner federati. Utilizzare la procedura descritta in questo argomento per modificare tale configurazione.</span><span class="sxs-lookup"><span data-stu-id="56561-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains. Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="56561-106">Nella procedura che segue si presuppone che sia stata già abilitata la federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="56561-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="56561-107">Per informazioni dettagliate sull'abilitazione della Federazione, vedere [abilitare o disabilitare l'accesso degli utenti remoti](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="56561-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="56561-108">Per abilitare o disabilitare l'individuazione automatica dei domini federati per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="56561-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="56561-109">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="56561-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="56561-110">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="56561-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="56561-111">Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Configurazione Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="56561-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="56561-112">Nella pagina **Configurazione Access Edge** fare clic su **Globale**, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="56561-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="56561-113">In **Modifica configurazione Access Edge**, in **Abilita comunicazioni con utenti federati** selezionare o deselezionare la casella di controllo **Abilita individuazione dominio partner** per abilitare o disabilitare l'individuazione automatica dei domini partner.</span><span class="sxs-lookup"><span data-stu-id="56561-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="56561-114">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="56561-114">Click **Commit**.</span></span>

<span data-ttu-id="56561-115">Per consentire agli utenti federati di collaborare con gli utenti nella distribuzione di Skype for Business Server, è necessario aver configurato almeno un criterio di accesso esterno per supportare l'accesso degli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="56561-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="56561-116">Per ulteriori informazioni, vedere [abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica](enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="56561-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="56561-117">Per informazioni dettagliate sul controllo dell'accesso per specifici domini federati, vedere [gestire i domini federati SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) e [gestire i provider federati SIP](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="56561-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="56561-118">Abilitazione o disabilitazione dell'individuazione dei partner federativi tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="56561-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="56561-119">L'individuazione dei partner federativi può essere gestita utilizzando Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="56561-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="56561-120">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56561-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="56561-121">Per abilitare l'individuazione dei partner federativi</span><span class="sxs-lookup"><span data-stu-id="56561-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="56561-p105">Per abilitare l'individuazione dei partner federati, impostare il valore della proprietà **EnablePartnerDiscovery** su True ($True). Tenere presente che è necessario abilitare l'instradamento DNS SRV per modificare il valore di questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="56561-p105">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True). Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="56561-124">Per disabilitare l'individuazione dei partner federativi</span><span class="sxs-lookup"><span data-stu-id="56561-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="56561-125">Per disabilitare l'individuazione dei partner federati, impostare il valore della proprietà **EnablePartnerDiscovery** su False ($False).</span><span class="sxs-lookup"><span data-stu-id="56561-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

